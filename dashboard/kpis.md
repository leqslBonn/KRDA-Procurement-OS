---
id: kpi-system
title: KPI System
owner: Procurement Analytics (IP)
status: active
updated: 2026-06-25
---

# KPI System

The organization's performance scoreboard. **Definitions** are canonical in
[knowledge/taxonomy/kpi-definitions](../knowledge/taxonomy/README.md); **values** live
here, each traced to a source register. No unsourced numbers.

> ระบบ KPI — นิยามอยู่ที่ taxonomy, ค่าอยู่ที่นี่ ทุกตัวอ้างที่มา

## Tracked KPIs

| # | KPI | Measures | Source | Target |
|---|-----|----------|--------|:------:|
| 1 | Cost Down | Validated savings (THB & %) | `/cost_down/savings-register.md`, `cost_database` | TBD |
| 2 | Supplier Quality | PPM / defect rate, trend | `/suppliers`, scorecards | TBD |
| 3 | Delivery | On-time delivery % | `/suppliers`, `project_history` | TBD |
| 4 | Response Time | Request → assignment / quote cycle | `meeting_history`, `rfq_database` | TBD |
| 5 | Negotiation Success | Δ achieved vs target | `negotiation_history` | TBD |
| 6 | Project Completion | On-time, on-spec project closure | `project_history` | TBD |
| 7 | Engineering Support | ECNs supported, qualification cycle | `project_history` | TBD |
| 8 | Automation Coverage | % repetitive tasks automated | `/workflows` automation log | TBD |
| 9 | AI Accuracy | Simulation rubric score; recs accepted | `/simulation`, `lessons_learned` | TBD |
| 10 | Knowledge Growth | Articles added; `TBD`s cleared | `knowledge/index.md` | TBD |

## Rules
- Every value links to its source record; unknowns are `TBD`, never invented.
- KPI **definitions/formulas** are single-source in `knowledge/taxonomy/kpi-definitions.md`
  (to be authored) — this scoreboard shows values only.
- Snapshots are dated and archived under `reports/` (weekly/monthly).
- KPIs feed the [weekly improvement review](../improvement/README.md).

## Reporting
- Weekly: [/weekly_report](../commands/weekly_report.md) → `reports/<YYYY-Www>-weekly.md`
- Monthly: [/monthly_report](../commands/monthly_report.md) → `reports/<YYYY-MM>-monthly.md`
- Layout: [kpi-dashboard template](../templates/kpi-dashboard.md).
