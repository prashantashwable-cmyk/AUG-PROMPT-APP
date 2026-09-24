# MASTER PROMPT — ALL INDIA ELEVATORS COMPANY
## Elevator Business Management Platform · Version 3 (Improved)

---

## 1. YOUR ROLE & MISSION

Act as a combined expert team: **enterprise product architect + elevator-industry operations expert + UX designer + automation engineer + fraud-prevention specialist**.

Your mission: design the complete, enterprise-grade, production-ready blueprint for a mobile-first platform that runs a traditional elevator business **almost fully automatically** — like a production line — monitored by only ONE admin.

**Depth rule (apply to everything):** For every requirement below, go THREE layers deep:
- **Layer 1 — Feature:** what is stated.
- **Layer 2 — Process:** the workflow behind it (steps, actors, data, triggers, timers, exceptions, failure paths).
- **Layer 3 — Business outcome:** the money, safety, liability, or efficiency it protects.

At every layer, proactively suggest **structural, process, workflow, and functional improvements** beyond what is written here.

---

## 2. BUSINESS IDENTITY

| Item | Value |
|---|---|
| Brand | **ALL INDIA ELEVATORS COMPANY** |
| Owner | **Mr. Prashant Vasant Wable** |
| Home region | Pune, Maharashtra, India |
| Compliance base | All SOPs must follow lift rules & regulations of Pune / Maharashtra (Maharashtra Lifts Act, licensing, and inspection requirements) |

---

## 3. NON-NEGOTIABLE BUSINESS MODEL PRINCIPLES

The platform must be:

1. **Enterprise-grade & production-ready** — not a demo.
2. **Highly scalable** — Pune → Maharashtra → all India.
3. **Asset-light** — the company owns no inventory, vehicles, or workforce.
4. **Aggregator model** — suppliers, technicians, riders, QC inspectors, and NBFC finance partners are all aggregated partners on the platform.
5. **Zero-liability model** — liability is contractually shifted to suppliers, technicians, and customers via digital agreements, geo-verified handovers, and evidence logs.
6. **Zero-risk on money** — milestone-based customer payments; evidence-gated worker payouts.
7. **Fully automated** — the business is run by the SYSTEM, not by people; work flows in a streamlined production line.
8. **One-person monitoring** — a single Admin supervises by exception; the Owner focuses only on business development.

---

## 4. GLOBAL PLATFORM REQUIREMENTS (apply to every role & screen)

### 4.1 Unique Location-Based ID System
Every entity — lead, lift order, customer, employee/worker, partner, supplier, payment, complaint, chat, container, document — gets a **unique location-aware ID** (example: `MH-PUN-KOT-LIFT-089`). Every photo, video, GPS log, chat message, payment, signature, and SOP step is auto-tagged to its ID. Design the full ID scheme and how everything is tracked around it.

### 4.2 Map-First Interface
The **MAP is the main interface** for every role. All business is seen, handled, and controlled from live map nodes: leads, sites, riders, technicians, containers, complaints, payments. Every list view must also exist as a map view.

### 4.3 AI Master Controller
The AI + app acts as a **strict master controller**: it enforces each role's daily time schedule and SOP automatically, follows up on every pending task, escalates delays, and never lets work sit idle. Humans respond to the system; the system drives the business.

### 4.4 Daily Routine Schedule (every role)
Every role — Rider, Sales, Technician, QC, Admin, Owner — has an AI-enforced **daily routine schedule** with auto follow-ups, reminders, and escalation on misses.

### 4.5 Micro-Gamification
After completing **each and every task**, small virtual coins/money are credited instantly in-app — game-style motivation. Include leaderboards, streaks, badges, live "money meters," and city-wide "Hero of the Week."

### 4.6 Role Clarity = Automatic Motivation
Every role must see, at all times: **exactly what work to do next (per SOP) + exactly what benefit/earning follows completion.** Work → proof → reward must be visible on one screen. This clarity is the motivation engine.

### 4.7 Structured Output per Role
The most important design goal: each role's **structured output must directly generate real money** for the business. For every role, define its measurable output and how the system converts it to revenue.

### 4.8 Languages
Instant in-app switching between **English, Marathi, and Hindi** — all screens, bots, notifications, and voice prompts.

### 4.9 Themes & Role-Based UI
Very beautiful, **switchable themes**, with UI adapted per role:
- **Rider/Helper:** outdoor high-contrast, large buttons, voice input (usable on a bike).
- **Technician/QC:** dark-slate, step-by-step checklists, camera-first verification.
- **Customer:** premium gold-and-white portal — payments, live progress, transparency.
- **Admin/Owner:** dark-mode analytics dashboard, multi-monitor friendly, alert-driven.

### 4.10 Adaptive Screens (VIMP)
Fully responsive/adaptive layout on every screen size — phone, tablet, desktop.

### 4.11 Evidence-First Money Rule (MOST IMPORTANT — money & safety)
**No payment moves without evidence.** Every payout requires exact photo/video/GPS proof of the SOP step, verified automatically by AI (computer vision), with Admin review only for critical/flagged cases.

---

## 5. ROLES ON THE PLATFORM

Field Rider (lead generator) · Sales Bot + Manual Negotiator · Technician (Levels 1–5) · QC Inspector · Customer · Supplier · NBFC/EMI Partner · New Worker (onboarding) · Admin · Owner.

---

## 6. END-TO-END OPERATIONAL LIFECYCLE (the production line)

### PHASE 1 — Lead Generation (Field Rider)
- Rider travels the city by bike finding construction sites where the **lift shaft is ready** for installation.
- Captures **photos with GPS location** of the site, lift shaft, and a contact number. App **auto-detects the site address**. Everything is one-tap/automatic for easy use on a bike.
- Rider's map shows: all captured lead photos pinned by location, full route traveled today, total area covered so far, and **AI-suggested high-potential zones** for more leads.
- Tapping any photo on the map opens full site details.
- Rider sees commission earned per lead + gamified leaderboard.

### PHASE 2 — Automated Sales & Negotiation
- All leads auto-forward to the Sales module and are organized **on the map**.
- System sends **WhatsApp marketing messages with the site's own photos** to each lead.
- Based on response, an **automated multilingual marketing call** (AI voice bot) collects lift requirements.
- **Auto-quotation engine** builds the quote from pre-configured settings: number of floors, lift type (automatic/manual doors), finish (stainless steel SS / powder-coated MS).
- **Margin logic (exact rules):** quote at **60% extra margin** → negotiation bot may discount **up to 30%** → beyond that, transfer to **manual negotiation** → hard margin floor locked at **minimum 20%**. The system must make it impossible to close below 20% margin.

### PHASE 3 — Digital Agreement & Token
- On deal-won, a **digital agreement** is executed online automatically.
- Customer pays a **₹10,000 token online** to lock the order.

### PHASE 4 — Technical Clearance
- Nearest technician visits the site for **clearance approval**.
- Customer automatically receives **all drawings and technical details** on their app page.

### PHASE 5 — Smart Container Logistics
- Per the agreement, material dispatches from the Supplier in a **Smart IoT Container**: GPS tracking, inbuilt secure motion-detection CCTV, and a digital lock.
- Container location is live on all relevant maps.

### PHASE 6 — Payments & EMI
- When the full material container reaches the site: customer pays **90% online**; remaining **10% at final handover**.
- **EMI facility via NBFC bank partners**, secured against the lift material in the container on site (protected by GPS + CCTV + digital lock). Customer sees the full EMI schedule in-app.

### PHASE 7 — Secure Material Handover (Triple-Key)
- At material handover, **Customer AND Installation Technician must both be present**; **digital signatures** taken from both for safety and liability transfer.
- The **digital lock opens ONLY with simultaneous Customer approval + Technician approval + Admin approval in the app, under live CCTV evidence** (e.g., Customer OTP + Technician biometric + Admin system approval).

### PHASE 8 — Installation under Strict SOP
- **2-Week Rule:** the technician is authorized to start ONLY when the customer makes the site ready within 2 weeks — keeping the workflow production-line efficient.
- Technician executes work **strictly per SOP** (SOP defined by Pune/Maharashtra rules & regulations).
- **Every SOP step requires exact photo/video evidence** (e.g., laser-aligned shots); **AI computer vision validates** alignment, torque markings, and fitting accuracy; Admin reviews only critical/flagged cases.
- In-app wallet credits happen ONLY when SOP + evidence pass. This is the core money & safety control.

### PHASE 9 — Surprise QC & Final Handover
- After installation, a **QC Inspector performs a SURPRISE quality inspection** with strong evidence.
- Final handover requires **Customer + Technician + QC Inspector present together**, with a trial-run test (e.g., 10 runs), customer star rating, and **digital signatures from all three**.
- Only then: customer releases final 10%; technician's verified earnings pay out **weekly to their bank account**, approved by Admin + customer satisfaction.

### PHASE 10 — Post-Sale (AMC & Complaints)
- Customer app includes **complaint bot chat** and **AMC progress tracking** on the map.
- Design the full AMC lifecycle: reminders, renewals, scheduled maintenance visits with the same SOP + evidence + payout rules.

---

## 7. ROLE-WISE APP PAGES (minimum screens)

- **Rider:** capture screen (photo+GPS, one-tap), map (leads/route/coverage/hot zones), commission & leaderboard.
- **Sales/Negotiation:** lead map, WhatsApp/call automation console, quotation builder, bot-negotiation monitor, manual negotiation queue (margin floor enforced).
- **Technician:** map with site details & progress, SOP step checklist with camera, payments page, leaderboard, level/rank progress.
- **Customer:** quotation, negotiation bot chat, payment history & schedule, installation progress on map, EMI schedule, complaint bot chat, AMC progress, live container CCTV/GPS view, all documents & drawings.
- **New Worker (Aggregator Onboarding):** one page for discovery, filters, onboarding, KYC/verification, **earning possibilities**, and **SOP training by AI + training videos** with tests before activation.
- **Supplier:** order queue, dispatch confirmation with container assignment, payment status.
- **Admin (MOST IMPORTANT):** see and control ALL progress and every individual's activity **on the map** with full filters; complete business statistics & analytics; exception/alert inbox; approval queues; daily routine schedule.
- **Owner (Mr. Prashant Vasant Wable):** strategic page only — no daily operations. Live cash-flow metrics (₹10k tokens, 90% clearances, net margins), regional growth heatmaps, **System Efficiency Index** (target: 95%+ fully automated execution), expansion levers (franchise/city-partner royalty model), daily routine schedule.

---

## 8. SECURITY, ANTI-THEFT & MATERIAL GOVERNANCE

- **Container protection:** off-hours motion triggers loud local siren + instant red alerts to Admin and Customer.
- **Pre-packed barcoded kits:** minor materials (cables, bolts, brackets) arrive in phase-sealed pouches; a pouch unlocks only at its verified SOP stage.
- **BOM rules:** Bill-of-Materials algorithms compute exact cable/material quantities; abnormal requests are auto-flagged.
- **Scrap return:** unused material/scrap must be bagged and photo-verified; missing items auto-deducted from the technician wallet at **market price + 20% penalty**; zero-wastage earns a bonus.
- **Fallback & instant re-assignment:** if a technician misses GPS check-in, fails AI photo validation twice, or is QC-flagged — access is revoked instantly and an urgent job with surge bonus broadcasts to certified technicians within **5–10 km**, first-accept wins.

---

## 9. WORKER CAREER LADDER (promotion gamification)

Direct entry to senior roles is locked. Everyone starts at Level 1.

| Level | Role | Scope | Promotion requirement |
|---|---|---|---|
| 1 | Trainee Helper | Material handling, site cleanup | Entry after AI training + test |
| 2 | Junior Technician | Brackets, shaft alignment, wiring | 20 sites, 4.2+ rating |
| 3 | Senior Technician | Motor, control panel, ARD testing | 50 sites, 4.5+ rating |
| 4 | Master Technician | Full assembly, diagnostics | 100+ sites, 98% SOP accuracy |
| 5 | QC Inspector / Site Lead | Independent site auditing | Invitation + track record |

Add: daily morning audio motivation prompts, live money meters, progress bars to next rank, city leaderboards.

---

## 10. GAPS YOU MUST ALSO DESIGN (not fully specified above — fill them)

1. Cancellation, refund, and dispute policies at each payment milestone.
2. Warranty terms and how liability stays off the company.
3. Supplier onboarding, quality rating, and penalty system.
4. Worker KYC, police verification, insurance, and safety-gear compliance.
5. Statutory lift licensing/inspection workflow for Maharashtra (government approvals) inside the app.
6. Complaint SLA engine and AMC pricing/renewal engine.
7. Fraud scenarios (fake leads, staged photos, collusion) and countermeasures.
8. Offline mode for riders/technicians in low-network sites.

---

## 11. REQUIRED DELIVERABLES (produce ALL, in this order)

1. **Improvement suggestions** — structural, process, workflow, functional (three layers deep).
2. **Complete data model** — entities, relationships, and the location-based unique ID scheme.
3. **Workflow state machines** for Phases 1–10: states, triggers, timers, evidence gates, exception paths.
4. **Screen-by-screen UI spec per role** — map-first, 3 languages, role themes, adaptive layouts.
5. **SOP checklists** mapped one-to-one to evidence requirements and payment gates.
6. **Payment & margin engine logic** — exact rules, formulas, and edge cases.
7. **Security & anti-fraud design** for money, material, and evidence.
8. **Gamification economy design** — coin values, commissions, leaderboards, level ladder.
9. **Phased rollout plan** — MVP (Pune) → Maharashtra → India, with build priorities.
10. **Tech stack & architecture recommendation** for an enterprise-grade, scalable, automated system.
11. **KPI dashboard definition** per role + Admin + Owner.

**Output format:** organized with clear headings, tables, and diagrams (ASCII/flowcharts where useful). Be specific and exhaustive — no generic filler. Where you make an assumption, state it and continue.
