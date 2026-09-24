# AIE MVP: Claude Code build kit (sequential prompts)

This kit turns your master prompt into a set of **sequential, gated prompts for Claude Code on the web** (claude.ai/code).
Together they refactor the existing `MVP-V3-200-AS` app into a simple MVP that can run your first 10–20 real lift orders.

---

## 1. Read this first: what I found in your repo
I did a quick **read-only** look at `MVP-V3-200-AS` (commit `fc505b8`) so the prompts point at real files instead of guessing. Five things change the plan:

| # | Finding | Why it matters | How the kit handles it |
|---|---|---|---|
| 1 | **About 128 of the 194 screens save data only in the user's own browser** (`localStorage`, through `src/lib/db.ts`). | If a technician updates a job on their phone, the Admin never sees it. Real multi-user orders **cannot** run on those screens. | Every MVP screen is moved onto the one shared Firestore database. The other screens are hidden, not migrated. (DECISIONS D-01, D-22) |
| 2 | The previous 62-phase build ended with **"PRODUCTION READINESS BLOCKED"**. The live site may still let people in with **demo bypass logins**. | Real customer data can't go in until that's closed. | Step 11 hardens this, and Step 14 gives you an exact checklist. |
| 3 | **One Firebase project** holds both test and real data. | Any automated test could write junk into real data. | All tests run on the Firebase **emulator** or demo data. Claude never touches production. (D-19) |
| 4 | The data model has **no Task, no Blocker, no survey or site-ready stages, and no Owner, Sales or QC roles**. | These are the core of "current task, owner, due date". | They are built additively in Step 03. Everything else (quote, payments, PO, installation, QC, handover, AMC, audit) already exists and is **reused**. |
| 5 | The previous build kept stalling on "missing credential". | It wasted phases. | The kit tells Claude **not to loop**: use the emulator, and hand anything that needs real credentials to you as a checklist. |

I also resolved **27 gaps and ambiguities** in your master prompt. They're in `repo-files/docs/mvp/DECISIONS.md`, and you can change any of them. Examples:
- when a Lead becomes an Order
- stage vs status (hold and cancel)
- exact progress % and health rules
- the task-by-task automation table
- payment gates with Admin override
- markup vs margin
- never hard-coding GST

---

## 2. What's in the zip
```
AIE-MVP-CLAUDE-CODE-KIT/
├── README.md                      ← this guide (for you)
├── prompts/                       ← paste these into Claude Code, one per session, in order
│   ├── 00_BOOTSTRAP.md            install kit + test setup + baseline (no app changes)
│   ├── 01_AUDIT.md                Phase A — audit (WAITS for your approval)
│   ├── 02_PLAN.md                 Phase B — exact plan (WAITS for your approval)
│   ├── 03_DATA_FOUNDATION.md      shared DB, roles, Task, Blocker, stage rules
│   ├── 04_ORDER_VIEW_ADMIN_DASHBOARD.md   Universal Order View + one Admin dashboard + MVP_MODE
│   ├── 05_LEADS_SALES_SURVEY.md
│   ├── 06_QUOTE_BOOKING_PAYMENTS.md
│   ├── 07_SITE_READY_SUPPLIER_DELIVERY.md
│   ├── 08_TECHNICIAN_INSTALLATION_BLOCKERS.md
│   ├── 09_QC_HANDOVER_AMC.md
│   ├── 10_CUSTOMER_OWNER_NOTIFY_REPORTS_LANG.md
│   ├── 11_SECURITY_COMPLIANCE_HARDENING.md
│   ├── 12_TEST_AND_VERIFY.md      Phases D + E — prove ONE LIFT works
│   ├── 13_REPORT_AND_ROADMAP.md   Phase F — implementation report
│   ├── 14_GO_LIVE_FIRST_REAL_LIFT.md      go-live checklist + first-lift playbook
│   └── utilities/
│       ├── U1_RESUME_OR_CONTINUE.md       session died / lost track
│       ├── U2_FIX_FAILING_CHECKS.md       something is red
│       ├── U3_REVIEW_BEFORE_MERGE.md      independent review before merging
│       ├── U4_CHANGE_REQUEST.md           you want to change something mid-way
│       └── U5_PILOT_FEEDBACK_ROUND.md     weekly, during the real pilot
└── repo-files/                    ← Step 00 copies these INTO MVP-V3-200-AS
    ├── CLAUDE.md                  rules Claude loads automatically in every session
    ├── .claude/agents/mvp-scope-guard.md   reviewer sub-agent (catches scope creep)
    └── docs/mvp/
        ├── MVP_SPEC.md            your master prompt (source of truth)
        ├── DECISIONS.md           27 resolved decisions (edit to override)
        ├── REPO_FACTS.md          what the pre-inspection found
        ├── ACCEPTANCE_SCENARIOS.md exact test data + expected results (S1–S8)
        └── PROGRESS.md            the hand-over log between sessions
```

**Why files in the repo, rather than one giant prompt:** every Claude Code cloud session starts on a fresh machine with no memory of earlier sessions. `CLAUDE.md` is loaded automatically, and `PROGRESS.md` carries the state from one session to the next. That keeps each prompt short and each session focused.

---

## 3. One-time setup (about 10 minutes)
1. **Environment setup script** (recommended, so tests can use the Firebase emulator).
   - Where: in Claude Code on the web, open the session's environment menu (title bar) → **Edit** → **Setup script**.
   - Add these lines:
     ```bash
     #!/bin/bash
     # Java + Firebase CLI for the Firebase Emulator Suite (tests never touch real data)
     apt-get update -y && apt-get install -y --no-install-recommends openjdk-17-jre-headless
     npm install -g firebase-tools
     ```
   - If your environment's network access is limited, Step 00 will tell you exactly which host to allow.
   - If the emulator still can't run, the kit falls back to demo-data checks and records the gap. It won't stall.
2. **Get the kit into the repo.** Step 00 does this for you. It tries these in order:
   1. the files are already in the repo
   2. the zip is attached to the message
   3. it fetches them from your `AUG-PROMPT-APP` repo

   If all three fail, upload the **contents** of `repo-files/` to `MVP-V3-200-AS` with GitHub's **Add file → Upload files**.

---

## 4. How to run it: the loop
```
┌─► New Claude Code session on MVP-V3-200-AS (default branch)
│     paste the next prompt file (everything below the line)
│   Claude works → pushes a branch → opens a DRAFT PR → posts a fixed-format report → STOPS
│   You read the report (answer its questions if any)
│   (optional, recommended for 03/06/08/09/11) paste U3_REVIEW_BEFORE_MERGE in the same session
│   Merge the PR on GitHub
└── repeat with the next number
```
**Rules that keep this safe:**
- **One step per session, in order.** Never run two steps at the same time: they edit the same files.
- **Always merge the PR before starting the next step.** Each prompt checks that the previous step is DONE, and stops if it isn't.
- **Steps 01 and 02 wait for you.** Reply `APPROVED`, or `APPROVED with changes: …`, in the same session.
- If Claude says **"stop and ask"**, answer it. It means a destructive or scope-changing decision.
- **Lost?** Use `U1`. **Something red?** Use `U2`. **Want a change?** Use `U4`. Don't just type ad-hoc requests; U4 keeps the plan and DECISIONS in sync.

| Step | You get | Your job |
|---|---|---|
| 00 | Kit installed, tests runnable, baseline recorded | Add the setup script if asked; merge |
| 01 | `MVP_SIMPLIFICATION_AUDIT.md`, plus about 10 questions for you | **Answer and approve** |
| 02 | `MVP_REFACTOR_PLAN.md` with exact files for every step | **Approve** |
| 03–11 | One working slice per step, each with checks and a draft PR | Skim the report and screenshots; merge |
| 12 | Scenarios S1–S8 proven, a verification report, a 30-minute UAT script | Do the UAT on real phones |
| 13 | `MVP_IMPLEMENTATION_REPORT.md` and roadmap | Read the "remains manual" list |
| 14 | Go-live checklist and first-lift playbook | **Do the Owner actions** (Firebase access, deploy settings, backups, CA and legal checks) |
| U5 | Weekly improvements from real use | Paste the week's notes |

---

## 5. What Claude will never do in these sessions
- Touch your real Firebase data or production deployment. **Live checks are yours**, and Step 14 lists them.
- Delete screens or data without your explicit approval. Non-MVP features are **hidden** behind `MVP_MODE` and can be switched back.
- Build anything from the "Do NOT build" list: AI manager, CV, IoT, gamification, NBFC, franchise, and so on. The `mvp-scope-guard` agent checks every step for this.
- Hard-code legal or tax facts. Anything like that is marked **⚖ VERIFY** for your CA or lawyer.

---

## 6. Changing the defaults
Edit `docs/mvp/DECISIONS.md` in the repo **before Step 02**, or use `U4_CHANGE_REQUEST` afterwards. The decisions you're most likely to want to change:
- **D-13:** how staff and customers log in
- **D-14:** payment milestone amounts and gates
- **D-15:** minimum markup (default 20%) and the GST rate, which your CA sets
- **D-21:** the pilot deployment (Vercel or AI Studio)
- **D-26:** warranty length
