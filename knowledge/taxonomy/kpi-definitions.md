---
id: kpi-definitions
title: KPI Definitions — KRDA Procurement
owner: Procurement Analytics (IP)
status: active
updated: 2026-06-26
links: [../../dashboard/kpis.md, spend-categories.md]
---

# KPI Definitions — KRDA Procurement

> Canonical definitions and formulas for all 10 tracked KPIs.
> **Values** live in [/dashboard/kpis.md](../../dashboard/kpis.md).
> Change a definition here → update the dashboard template on the same day.

---

## KPI 1 — Cost Down (Savings)

**Measures:** Validated cost savings achieved vs. baseline spend.

| Field | Definition |
|---|---|
| **Baseline** | Last confirmed purchase price (PO price) × annual volume |
| **Validated saving** | (Baseline price − New price) × annual volume; confirmed by Cost Reduction + Human Owner |
| **Realized saving** | Saving confirmed in a posted PO at the new price |
| **Formula (THB)** | Σ (Baseline_price_i − New_price_i) × Volume_i for all validated CD-YYYY-NNN |
| **Formula (%)** | Total saving THB ÷ Total addressable spend THB × 100 |
| **Addressable spend** | Spend on items where a cost-down was attempted or possible (not fixed-fee services) |
| **Source** | `/cost_down/` records + `cost_database.md` |
| **Cadence** | Monthly cumulative; quarterly target review |
| **Target** | TBD (set by Human Owner annually) |
| **Notes** | Count validated separately from realized. Do not include projected or in-progress savings. |

---

## KPI 2 — Supplier Quality (PPM)

**Measures:** Defect rate from active suppliers.

| Field | Definition |
|---|---|
| **PPM** | (Defective units received ÷ Total units received) × 1,000,000 |
| **Defective unit** | Any unit rejected at incoming inspection or returned from production |
| **Measurement window** | Rolling 3-month and YTD |
| **Formula** | PPM = (Σ rejects_i ÷ Σ total_received_i) × 1,000,000 |
| **Per-supplier PPM** | Same formula scoped to one supplier |
| **Trend** | Month-over-month direction (↑ worsening, ↓ improving) |
| **Source** | `/suppliers/<slug>/scorecard`, quality records in `/projects` |
| **Cadence** | Monthly |
| **Target** | TBD |
| **Notes** | Prototype parts tracked separately from production/production-intent parts. |

---

## KPI 3 — On-Time Delivery (OTD)

**Measures:** Supplier delivery performance against committed date.

| Field | Definition |
|---|---|
| **On-time** | Delivered on or before the PO confirmed delivery date |
| **Late** | Delivered after PO confirmed delivery date (even 1 day) |
| **Formula** | OTD % = (On-time deliveries ÷ Total deliveries) × 100 |
| **Scope** | All PO line items with a confirmed delivery date in the period |
| **Per-supplier OTD** | Same formula scoped to one supplier |
| **Source** | `/suppliers/<slug>/scorecard`, `project_history.md` |
| **Cadence** | Monthly |
| **Target** | TBD (e.g., ≥ 90%) |
| **Notes** | Partial deliveries count as late unless PO explicitly split. Exclude force-majeure events (documented). |

---

## KPI 4 — Response Time (Cycle Time)

**Sub-KPI A: Request → Assignment**

| Field | Definition |
|---|---|
| **Formula** | Days from request received by Procurement Lead to task assigned to owning dept |
| **Source** | `meeting_history.md` (intake date), `current-context.md` (assignment date) |
| **Target** | TBD (e.g., ≤ 1 business day) |

**Sub-KPI B: RFQ Cycle Time**

| Field | Definition |
|---|---|
| **Formula** | Days from RFQ issued to all quotes received (last response date) |
| **Source** | `rfq_database.md` (issue date, close date) |
| **Target** | TBD (e.g., ≤ 14 calendar days for Price Comparison) |

**Sub-KPI C: RFQ → Award**

| Field | Definition |
|---|---|
| **Formula** | Days from last quote received to Human Owner award approval |
| **Source** | `rfq_database.md` |
| **Target** | TBD |

**Cadence:** Weekly average; monthly trend.

---

## KPI 5 — Negotiation Success

**Measures:** How much of the negotiation target was achieved.

| Field | Definition |
|---|---|
| **Target** | Should-cost or benchmark price set before negotiation |
| **Achieved** | Final agreed price in the awarded PO |
| **Formula (%)** | (Target − Achieved) ÷ Target × 100 (positive = beat target) |
| **Formula (THB)** | (Target_price − Awarded_price) × Volume |
| **Source** | `negotiation_history.md` (target, outcome), `/rfq` (award price) |
| **Cadence** | Per negotiation event; monthly summary |
| **Target** | TBD (e.g., ≥ 80% of target achieved in ≥ 70% of negotiations) |
| **Notes** | Only count cases where a formal negotiation target was set via Cost Reduction. Ad-hoc price discussions excluded. |

---

## KPI 6 — Project Completion

**Measures:** Procurement delivery on-time and on-spec for assigned R&D projects.

| Field | Definition |
|---|---|
| **On-time** | All procurement milestones (spec ready, RFQ issued, award, PO, delivery) met by project schedule |
| **On-spec** | All parts qualified and accepted by Technical Purchasing criteria |
| **Formula** | % of procurement milestones met on time ÷ total milestones in period |
| **Source** | `project_history.md` (milestone dates, status) |
| **Cadence** | Per project; monthly portfolio view |
| **Target** | TBD |
| **Notes** | Milestone dates set at project kickoff and not changed without Human Owner approval. |

---

## KPI 7 — Engineering Support (ECN & Qualification Cycle)

**Sub-KPI A: ECNs Supported**

| Field | Definition |
|---|---|
| **Formula** | Count of Engineering Change Notices where Technical Purchasing completed spec update + re-qualification within agreed SLA |
| **SLA** | TBD (e.g., spec update ≤ 3 business days after ECN receipt) |
| **Source** | `project_history.md` (ECN records) |

**Sub-KPI B: Qualification Cycle Time**

| Field | Definition |
|---|---|
| **Formula** | Days from first-article sample receipt to PASS/FAIL issued |
| **Source** | `project_history.md` (sample receipt date, result date) |
| **Target** | TBD (e.g., ≤ 10 business days) |

**Cadence:** Per event; monthly count.

---

## KPI 8 — Automation Coverage

**Measures:** Proportion of identified repetitive tasks that are automated.

| Field | Definition |
|---|---|
| **Identified repetitive tasks** | Tasks logged as automation candidates in Procurement Automation backlog |
| **Automated** | Tasks covered by a workflow/template/schedule in `/workflows` or `/schedule` |
| **Formula** | Automated tasks ÷ Total identified repetitive tasks × 100 |
| **Source** | `/workflows/` count, `/schedule/` entries, Procurement Automation backlog |
| **Cadence** | Monthly |
| **Target** | TBD (e.g., ≥ 60% of identified tasks automated by v1.0) |
| **Notes** | "Automated" = documented + reusable, not just done once. |

---

## KPI 9 — AI Accuracy

**Measures:** Quality of AI agent recommendations and decisions.

| Field | Definition |
|---|---|
| **Simulation score** | Average rubric score across all simulation scenarios run this month |
| **Rubric** | Per [simulation/_TEMPLATE.md](../../simulation/_TEMPLATE.md) — scored 0–5 per dimension |
| **Recommendation acceptance rate** | Human Owner accepted recommendation as-is ÷ total recommendations presented |
| **Formula (sim)** | Σ scenario scores ÷ scenarios run |
| **Formula (acceptance)** | Accepted recs ÷ total recs × 100 |
| **Source** | `/simulation/scenarios/`, `lessons_learned.md` |
| **Cadence** | Monthly |
| **Target** | TBD (e.g., sim score ≥ 4.0/5.0; acceptance ≥ 75%) |
| **Notes** | Track rejection reasons in `lessons_learned`; use to improve brain frameworks. |

---

## KPI 10 — Knowledge Growth

**Measures:** Rate at which the knowledge base is built and `TBD`s are resolved.

| Field | Definition |
|---|---|
| **Articles added** | Count of new `.md` files added to `/knowledge/` with status `active` |
| **TBDs cleared** | Count of `TBD` placeholders resolved across all files in the current month |
| **Formula (articles)** | Count new knowledge articles this period |
| **Formula (TBDs)** | TBD count at start of period − TBD count at end of period |
| **Source** | `knowledge/index.md` (article count), git diff (TBD count) |
| **Cadence** | Monthly |
| **Target** | TBD (e.g., ≥ 2 articles/month; TBD count declining) |
| **Notes** | TBD count checked by: `grep -r "TBD" /knowledge /company /agents | wc -l` |

---

## Governance

- Definitions here are **single-source**. Any change requires Human Owner approval + same-day update to `dashboard/kpis.md`.
- New KPIs proposed in `/improvement/ACTIONS.md` first; approved KPIs added here before being tracked.
- All formulas use **sourced data only** — never estimated or interpolated unless marked `EST`.
