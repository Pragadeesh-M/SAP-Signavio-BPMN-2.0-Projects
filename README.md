# 📊 Business Process Management (BPM) Projects

> Academic projects from **BISM 7216 – Business Process Improvement**, Master of Business (Information Systems), University of Queensland (2025).
> Covers end-to-end BPM lifecycle: process discovery, waste analysis, issue identification, and to-be redesign using **BPMN 2.0** in **SAP Signavio**.

---

## 📁 Projects

### 1. Urban Construction Projects (UCP) – Tender Bid Management Process
**Course:** BISM 7216 · Assignment 1 · UQ (2025)

Process modelling of the end-to-end government tender bidding lifecycle for **Urban Construction Projects (UCP)**, a construction firm responding to government procurement opportunities.

#### Process Overview
Triggered by a **tender notification from a Government Agency**, the process spans initial screening through to bid submission and post-submission retrospective. The model captures a multi-party, deadline-driven workflow involving 8 internal roles and 2 external participants.

**Pools & Participants:**
- **Government Agency** (black-box) — issues tender notification, receives bid
- **Urban Construction Projects (UCP)** — white-box, 8 lanes:
  - Director of Strategic Development (DSD)
  - Chief Executive Officer (CEO)
  - Operation Support Manager
  - Costing Lead
  - Legal Advisor
  - Tender Coordinator
  - Team Member
  - Project Scheduler / Procurement Officer
- **External Consultant** (black-box) — produces independent expert assessment report

**Main Process Flow:**
1. DSD logs the opportunity, conducts initial complexity assessment
2. High-complexity bids trigger the **Feasibility Assessment subprocess** (parallel: strategic fit evaluation by DSD & CEO, capacity checks by Ops Manager, cost estimation by Costing Lead, risk scan by Legal Advisor)
3. CEO approves/declines the bid; approved bids proceed to team nomination and workspace creation
4. Team members are onboarded; tender documents are awaited from the Government Agency with daily delivery tracking
5. **Verify Package Completeness subprocess** — Tender Coordinator sorts, tags, checks and records all documents; missing files trigger correction requests
6. For high-complexity bids: External Consultant delivers expert assessment; **Convene Workshop subprocess** brings CEO, Head of Design, Finance Controller and Legal Advisor together
7. **Review PEP subprocess** — DSD and CEO jointly review assessment, validate technical strategies, refine approach; CEO approves or declines
8. **Compile Tender Submission Pack subprocess** — parallel execution: Costing Lead (2-phase cost estimation with deviation threshold check), Procurement Officer (supplier identification and quotes), Legal Advisor (contractual risk analysis), Project Scheduler (Gantt chart)
9. **Schedule TCW subprocess** — Tender Coordinator compiles final pack, handles late-breaking documents, freezes changes at deadline
10. Tender Coordinator conducts TCW, review final bid
11. **Review Final Bid subprocess** — CEO and Key Leaders review; outcomes: approve, minor revision, or emergency CEO review (deadline-sensitive rework path)
12. Bid is submitted to Government Agency; submission folder archived to Google Vault
13. **Initiate Post-Submission Retrospective subprocess** — Tender Coordinator captures lessons learned and updates future bidding strategies; DSD triggers bid outcome prediction tool and assesses success likelihood

**Key BPMN Features Demonstrated:**
- Multi-pool collaboration with black-box and white-box modelling
- 8 named sub-processes with full internal modelling
- Parallel gateways for concurrent workstreams (cost, procurement, legal, scheduling)
- Exclusive gateways with rework loops (bid decline, revision, emergency review)
- Timer and message intermediate events (daily delivery checks, reminders, timestamped confirmations)
- Data objects and artefacts (Strategy Bids Tracker, Feasibility Assessment Report, Team Nomination Brief, Tender Control Log, Google Vault archive)
- Deadline-aware flow logic (2-day prior, 4-day prior, freeze deadlines)

**Positive outcome:** Tender submission approved, submitted on schedule, meeting all client requirements — client acknowledges successful receipt for evaluation.

**Negative outcome:** Bid process terminated due to strategic misalignment, or submission rejected for incompleteness or missed deadline.

**Tools & Methods:** SAP Signavio · BPMN 2.0 · BPM Lifecycle · Process Discovery · Subprocess Modelling

---

### 2. STBN Legal Advice Service – Full Process Improvement
**Course:** BISM 7216 · Assignment 2 (Team, Group 6) · UQ (2025)
**Team:** Devanshi Shambhwani, Pragadeesh Manickavasagam, Isha Bhatia, Kushagra Sahai, Manmeet Kaur Chanana

End-to-end process improvement engagement for **Stronger Together Business Network (STBN)**, a member services organisation whose free legal advisory service had outgrown its capacity. The task mirrored a real consulting brief: discover the current process, identify bottlenecks, quantify impact, and design an improved future state.

#### Context
STBN's Legal Advice Helpdesk (LAH) — staffed by 10 final-year law students and 5 qualified lawyers — was handling ~210 requests/day across standard contractual queries, FAQ lookups, and complex legal cases. Membership was growing at 20% p.a., demand was exceeding lawyer capacity, and member satisfaction was at risk.

#### Deliverables

**As-Is Model (BPMN 2.0)**
- Modelled the full legal advice lifecycle: request intake (phone/app) → LAH triage → FAQ handling → complex case escalation → lawyer research & drafting → LAH review → advice delivery → member confirmation
- Captured 4 sub-processes: Process Request, Evaluate Assigned Case, Send Advice, Handle Escalated Case
- Identified system defect: LASP portal showed resolved cases as "Open" ~70% of the time

**Waste Analysis (7+1 Framework)**

| Waste Type | Key Finding |
|---|---|
| Waiting | 1hr lawyer queue + 4hr case pickup + 8hr LAH post-lawyer delay per complex case |
| Overprocessing | Manual status updates despite system capability; repeated escalation steps |
| Defects/Errors | LASP status bug causing 70% incorrect "Open" statuses |
| Motion | Multi-party handovers (consultant → lawyer → consultant → member) |
| Overproduction | Redundant status emails and reminders before resolution |
| Underutilisation of Talent | Lawyers spending time on admin and waiting, not legal analysis |
| Extra Processing | 15% case re-escalation repeating full lawyer workflow |

**Issue Register (Top 5 Issues)**

| # | Issue | Quantitative Impact |
|---|---|---|
| 1 | Lawyer capacity overload on complex cases | 8,520 min/day demand vs 2,400 min capacity → 6,120 min/day backlog (~$3.18M p.a. to resolve) |
| 2 | Excessive waiting across process stages (3 stages) | $17.06M p.a. opportunity cost |
| 3 | Manual FAQ search and consultant response | 756 min/day wasted → $147,420 p.a. |
| 4 | Manual documentation tasks (review + cover letter) | 2,268 min/day → $442,260 p.a. |
| 5 | Inaccurate member follow-up handling (LASP bug) | 105 min/day wasted → $20,638 p.a. |

**To-Be Model — Improvements Implemented**

- **A – Paralegal Pool:** Introduced paralegal layer for research/drafting; lawyers focus on assessment (3 min) and sign-off (30–40 min). Projected to eliminate daily backlog.
- **B – Automated LASP Status Logic:** Auto-transitions (Open → Closed-Pending-Member → Closed); 48hr timeout; member push notifications. Eliminates ~7 LAH hrs/day of status call waste.
- **C – Auto-dispatch of Advice:** Template cover letters pre-filled from LASP; advice sent automatically on lawyer sign-off. Cuts 8hr post-advice delay and saves ~26 LAH hrs/day.
- **D – Triage Wizard + Expanded FAQ KB:** Guided keyword-based triage in LASP; self-service FAQ portal. Shifts 10–15% of cases away from lawyers (~21–32 cases/day).
- **E – Member Self-Service Portal:** Real-time case status, responsible lawyer, expected completion date, documents. Projected to cut follow-up calls by >50%.
- **F – Priority-Aware WIP Limits:** Kanban-style limits per lawyer; high-priority cases fast-tracked in parallel with paralegal drafting.

**Devil's Quadrangle Summary**

| Dimension | Change | Driver |
|---|---|---|
| Time | ↓ 40–60% lead time | Remove 8hr LAH delay + reduce lawyer queue |
| Cost | ↓ ~30% operational cost | Paralegal pool + automation |
| Quality | ↑ Higher accuracy | Automated status + lawyer sign-off retained |
| Flexibility | ↑ Scalable | Paralegal pool + knowledge base |

**Tools & Methods:** SAP Signavio · BPMN 2.0 · 7+1 Waste Framework · BPM Lifecycle · Process Design Heuristics (Specialisation, Parallelism, Automation, Task Elimination, Re-sequencing, WIP Control)

---

## 🛠️ Skills Demonstrated

- Business process modelling (BPMN 2.0) in SAP Signavio
- Multi-pool, multi-lane process architecture with black-box and white-box participants
- Sub-process design and decomposition
- As-is process discovery from narrative walkthrough
- Lean waste analysis (7+1 framework)
- Quantitative issue impact analysis (time, cost, capacity)
- To-be process design using process improvement heuristics
- Deadline-aware and event-driven flow logic
- Stakeholder-facing presentation of findings (CEO briefing format)
- Cross-functional team delivery

---

## 📬 Contact

**Pragadeesh Manickavasagam (Prag)**
Brisbane, QLD | [linkedin.com/in/pragadeesh-manick](https://linkedin.com/in/pragadeesh-manick) | pragadeeshm99@gmail.com
