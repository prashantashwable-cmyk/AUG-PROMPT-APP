# AUG Prompt App: All India Elevators Company master prompt

| File | What it is |
|---|---|
| [`PROMPT-MASTER-AUG-2026-GEMINI-V4.md`](PROMPT-MASTER-AUG-2026-GEMINI-V4.md) | **Use this one.** V4, "The App Is the Manager" |
| [`archive/PROMPT-MASTER-AUG-2026-GEMINI-V3.md`](archive/PROMPT-MASTER-AUG-2026-GEMINI-V3.md) | The previous version, kept for comparison |
| [`AIE-MVP-CLAUDE-CODE-KIT.zip`](AIE-MVP-CLAUDE-CODE-KIT.zip) and [`AIE-MVP-CLAUDE-CODE-KIT/`](AIE-MVP-CLAUDE-CODE-KIT/) | **Phase 1 MVP build kit**: sequential Claude Code (cloud) prompts that refactor `MVP-V3-200-AS` into an MVP for 10–20 real lift orders. Start with its [README](AIE-MVP-CLAUDE-CODE-KIT/README.md). |

## How to use V4
1. Open Section 17 (Owner Decisions) and change any default you disagree with.
2. Paste the whole file into Gemini (or any AI that can take a long prompt).
3. The AI answers in 9 passes. Reply **CONTINUE** after each one.
4. Save each pass. PASS 9 ends with a top-20 backlog of MVP features that you can hand to developers.

## What changed from V3, and why
V3 described the **happy path**: what should happen when everyone does their job.
To run 95% automatically, the app has to manage what happens **when people don't do their job**: they are late, blocked, absent, cheating or unsure. V4 adds that layer.

### 1. The app now works as a real manager
V3 only did follow-ups and punishments. A real manager does 16 jobs: plan, staff, assign, brief, get commitment, follow up, **remove blockers**, check quality, **decide fairly who is at fault**, reward, correct, develop, report, improve, keep promises to customers, and audit itself. Section 5 designs every one of them.

### 2. "95% automatic" is now a number you can track
- **Touchless Rate:** at least 95%.
- **Admin touches per lift:** 5 or fewer.
- **Admin minutes per lift:** 30 or fewer.
- **Orphan jobs:** always 0.

Automation is also earned step by step (levels A0 to A4), not switched on all at once. Day 1 will not be 95%. Month 12 can be.

### 3. The order of the work was broken, so it has been fixed
V3 had four ordering problems:
- It locked the price **before** measuring the shaft.
- It sent material **before** the site was ready.
- It checked EMI **after** the container arrived.
- It skipped supplier manufacturing, statutory permission and license, container return, and the emergency "passenger trapped" response.

Each of these creates stuck work that only a human can clear. Section 7 re-sequences the process into 21 gated stages (S0 to S20).

### 4. The margin rules as written could lose money
Read literally, "60% margin, bot discount up to 30%" gives ₹16L × 0.70 = ₹11.2L. That is only **12%** above a ₹10L cost, which breaks your own 20% floor. V4 defines the margin as markup on the fully-loaded cost. Coins, surge pay, warranty and royalty now count as costs too.

### 5. Things you didn't ask about but must check with a lawyer or CA
| Area | Risk |
|---|---|
| **Lift licensing** | You probably need a licensed lift contractor of record. You cannot shift every liability to gig technicians. |
| **WhatsApp and AI calls** | Messaging or calling numbers collected on site without consent can get your WhatsApp number banned and break TRAI rules. Capture consent at the lead stage. |
| **In-app wallet** | A wallet that holds money may need an RBI licence. Use an earnings ledger with weekly bank payouts instead. |
| **NBFC and EMI** | Once a lift is installed, it is part of the building, so it is weak collateral. RBI digital lending rules also apply to the platform. |
| **"Daily schedule enforced by the AI"** | Controlling partners' hours makes them look like employees. Control outcomes and commitments instead. |
| **Data protection** | CCTV, biometrics and GPS tracking need consent and retention rules under the DPDP Act. |
| **Gamification** | Rewarding speed in a dangerous trade causes accidents. Reward safety and first-time-right work instead. |

### 6. Hidden business gaps
- **Day-1 deadlock.** Everyone starts at Level 1, so nobody can install motors or control panels, or do QC. V4 adds lateral entry for experienced technicians.
- **Leads may come too late.** When a shaft is visibly ready, the builder has often already chosen a vendor. V4 finds leads earlier from public project registries.
- **Deals moving off the platform.** Technicians and customers may arrange AMC directly. V4 adds number masking and other countermeasures.
- **One Admin is a single point of failure.** V4 adds a Backup Admin, a two-person rule for large payments, and a weekly audit for the Owner.

The full list of 49 gaps is in Section 18 of the V4 prompt.
