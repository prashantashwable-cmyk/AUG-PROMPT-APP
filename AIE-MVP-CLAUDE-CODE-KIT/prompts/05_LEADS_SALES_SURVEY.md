<!-- HOW TO RUN: merge the Step 04 PR → NEW session → paste below the line. -->
---
# MVP STEP 05: Leads (Sales/Rider), qualification into an Order, and Survey

Follow the **Step protocol in CLAUDE.md**. Confirm Step 04 is DONE.

Read:
- **Step 05** in `docs/mvp/MVP_REFACTOR_PLAN.md`
- MVP_SPEC §13, §15 and §23
- DECISIONS D-04, D-08, D-16 and D-18

## Goal
A sales rider captures a lead on a phone in under a minute. Qualifying the lead creates the Order. The Admin assigns a surveyor, and the surveyor completes the survey on a phone with photos. The survey result drives the next task automatically.

## Build
Reuse or simplify first: `LeadInbox`, `LeadDetail`, `LeadFollowUpScheduler`, `SiteVisitVerification`, `CameraCapture`, and `src/lib/firestoreLeads.ts` if it is canonical. **Rewire every one of them to the canonical store.**

1. **Sales/Rider screens** (mobile-first; large buttons; English, Marathi and Hindi):
   - **New Lead**, with these fields:
     - customer name and phone (validated as an Indian mobile number)
     - location (GPS if permitted, otherwise typed)
     - site photo
     - site type, floors, lift requirement, construction stage
     - notes
     - **consent checkbox** (required) ⚖ VERIFY the wording
     - source
   - **My Leads**, **Follow-ups** (sorted by `next_followup`), **Won** and **Lost** (with a reason).
   - **Duplicate warning:** if the same phone number already exists, show it and link to the existing lead. Keep it simple; no fuzzy matching.
   - **Qualify** → `orderService.qualifyLead` (Step 03). This creates Customer, Site and Order, plus the ASSIGN_SURVEYOR task.
2. **Admin: assign surveyor.** Pick a surveyor and a date. This creates the SURVEY task (D-08), sends the "survey scheduled" notification, and moves the stage to SURVEY.
3. **Surveyor screens:**
   - **My Surveys:** today, then upcoming.
   - **Survey form**, with every spec §15 field:
     - floors, stops, capacity
     - shaft width, depth, pit and headroom in mm, validated as numbers
     - power, access, site readiness
     - remarks
     - **at least 2 photos**
     - feasibility
   - **Result** FEASIBLE, REQUIRES_CORRECTION or NOT_FEASIBLE. Each triggers its D-08 row.
   - **Offline tolerance:** if the existing `src/offline/outbox.ts` works with canonical writes, queue survey submissions and photos. If not, show a clear "no network — not saved" message. **Never fail silently.**
4. **Lead status mirroring** after conversion (D-04).

## Checks
- S1 steps 1–4 via the service layer, and via the UI if Playwright is available.
- Validation catches a bad phone number, missing consent, missing photos and non-numeric shaft sizes.
- NOT_FEASIBLE and REQUIRES_CORRECTION create the right tasks.
- A surveyor can't open another surveyor's survey (rules or emulator test if available).

## Report back (exactly this, then STOP)
```
## Step 05 report
1. Done  2. Files changed  3. Data changes  4. Checks  5. Scope guard
6. How to see it (Sales, Admin, Surveyor paths; phone screenshots)
7. Deviations  8. Questions
PR: <link>
Next: prompts/06_QUOTE_BOOKING_PAYMENTS.md
```
