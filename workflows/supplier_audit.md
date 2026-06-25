---
id: wf-supplier-audit
title: Supplier Audit & Qualification
type: workflow
owner: Supplier Development (SM)
status: active
updated: 2026-06-25
---

# Supplier Audit & Qualification

> Assess a supplier's capability and quality, decide qualification status, set
> corrective actions.

## Flow (BPMN-like)

Legend (canonical: [README](README.md#bpmn-notation)):
`●` start · `[task — Role]` · `◇Gn` gateway · `⚑` escalate · `⇒` calls workflow · `◉` end

```
● new supplier / re-qual / quality event
  └─► [Plan audit (scope, type) — Supplier Dev]
  └─► [Conduct assessment — Supplier Dev]
  └─► [Record findings (severity) — Supplier Dev]
  └─► ◇G1 <major nonconformity?>
        ├─ yes ─► [Set conditional + mandatory CAPA — Supplier Dev]
        └─ no ──► [Set CAPA (if any) — Supplier Dev]
  └─► [Decide qualification status (D2) — Supplier Dev]
  └─► ◇G2 <disqualify critical/sole supplier?>
        ├─ yes ─► ⚑ L3 Human Owner (continuity risk)
        └─ no ──► [Update status + scorecard — Supplier Dev]
                    └─► [Route outcomes — Strat Sourcing / Analytics] ──► ◉ qualified status set
```

## 1. Purpose
Decide, on evidence, whether a supplier is fit to use, and drive improvement.

## 2. Inputs

| Input | Source |
|-------|--------|
| Supplier record | `/suppliers/<supplier>/` |
| Performance data | `../dashboard/`, `/projects` |
| Audit checklist & standards | `../knowledge/quality/` *(TBD)* |
| Technical capability gaps | Technical Purchasing (SE) |

## 3. Required AI Employees

| Employee | Dept | Role in this flow |
|----------|------|-------------------|
| Supplier Development | SM | Owner — plan, audit, CAPA, status |
| Technical Purchasing | SE | Capability/process input |
| Procurement Analytics | IP | Performance history, scorecard data |
| Procurement Lead | OPL | Disqualification escalation |

## 4. Decision Gates

| Gate | Condition | Yes → | No → |
|------|-----------|-------|------|
| G1 | Major nonconformity? | Conditional + mandatory CAPA | CAPA (if any) |
| G2 | Disqualify critical/sole supplier? | ⚑ Human Owner | Update status & scorecard |

## 5. Outputs

| Output | Destination |
|--------|-------------|
| Audit report | `/suppliers/<supplier>/audits/<date>.md` |
| CAPA plan | `/suppliers/<supplier>/`, `/projects` |
| Qualification status & scorecard | `/suppliers/<supplier>/` |

## 6. Escalation Rules
- **L1 (SM head / Supplier Dev):** CAPA disputes, evidence gaps.
- **L2 (Procurement Lead):** audit affects active sourcing decision.
- **L3 (Human Owner):** disqualify critical/sole supplier; committed development spend (D3).

## 7. KPI

| KPI | Target |
|-----|--------|
| Supplier PPM / defect trend | TBD |
| On-time delivery (OTD) % | TBD |
| CAPA closure rate / aging | TBD |

## 8. Checklist

- [ ] Audit scope & type defined.
- [ ] Assessed against the standard checklist.
- [ ] Findings severity-rated with evidence.
- [ ] CAPA owners & due dates set.
- [ ] Single authoritative status/scorecard updated.
- [ ] Critical-supplier disqualification escalated.

## 9. Common Mistakes

- ❌ Recording findings not actually verified.
- ❌ Parallel/contradictory scorecards for one supplier.
- ❌ Disqualifying a sole supplier without continuity plan / escalation.
- ❌ Closing CAPA without evidence.
- ❌ Passing a supplier under cost pressure despite real nonconformities.

## 10. Automation Opportunities

- ⚙ Audit checklist generated from `/knowledge/quality`.
- ⚙ Auto-refresh scorecards from delivery/quality feeds.
- ⚙ CAPA due-date reminders via `/schedule`.
- ⚙ Auto-flag suppliers due for re-qualification.
