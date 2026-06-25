---
id: wf-supplier-selection
title: Supplier Selection
type: workflow
owner: Strategic Sourcing (SE)
status: active
updated: 2026-06-25
---

# Supplier Selection

> From a need to a justified, risk-aware supplier shortlist ready to quote.

## Flow (BPMN-like)

Legend (canonical: [README](README.md#bpmn-notation)):
`●` start · `[task — Role]` · `◇Gn` gateway · `⚑` escalate · `⇒` calls workflow · `◉` end

```
● sourcing need / risk flag
  └─► [Define category strategy — Strat Sourcing]
  └─► [Build candidate list — Strat Sourcing]
  └─► [Screen technical fit — Tech Purchasing] ∥ [Screen capability/quality — Supplier Dev]
  └─► ◇G1 <candidate qualified?>
        ├─ no ──► ⇒ supplier_audit.md ─┐
        └─ yes ─────────────────────────┤
  └─► [Assess supply risk — Strat Sourcing]
  └─► [Score & rank (criteria/weights) — Strat Sourcing]
  └─► ◇G2 <≥2 viable candidates?>
        ├─ no ──► ⚑ L3 Human Owner (single-source)
        └─ yes ─► [Produce shortlist (D2) — Strat Sourcing] ──► ⇒ rfq.md ──► ◉ shortlist ready
```

## 1. Purpose
Choose the right supplier base for a category — balancing cost, quality, risk, continuity.

## 2. Inputs

| Input | Source |
|-------|--------|
| Category & spend data | `../dashboard/`, `/projects` |
| Supplier master | `/suppliers` |
| Technical spec | Technical Purchasing (SE) |
| Sourcing methods & risk models | `../knowledge/sourcing/` *(TBD)* |

## 3. Required AI Employees

| Employee | Dept | Role in this flow |
|----------|------|-------------------|
| Strategic Sourcing | SE | Owner — strategy, scoring, shortlist |
| Technical Purchasing | SE | Technical-fit screen |
| Supplier Development | SM | Capability/quality screen, audit if needed |
| Procurement Analytics | IP | Spend/category data, risk evidence |
| Procurement Lead | OPL | Single-source escalation |

## 4. Decision Gates

| Gate | Condition | Yes → | No → |
|------|-----------|-------|------|
| G1 | Candidate qualified? | Continue | ⇒ [supplier_audit.md](supplier_audit.md) |
| G2 | ≥2 viable candidates? | Shortlist | ⚑ Human Owner (single-source) |

## 5. Outputs

| Output | Destination |
|--------|-------------|
| Category strategy | `/projects/<id>/` |
| Scored candidate evaluation | `/projects/<id>/` |
| Approved shortlist | `/suppliers` (status) + `/projects/<id>/` |

## 6. Escalation Rules
- **L1 (SE head):** scoring disputes, missing candidate data.
- **L2 (Procurement Lead):** category-strategy conflict, ownership unclear.
- **L3 (Human Owner):** single/sole-source designation (D3).

## 7. KPI

| KPI | Target |
|-----|--------|
| Category coverage (strategies in place) | TBD |
| Single-source % of categories | TBD (↓) |
| Selection lead time | TBD |

## 8. Checklist

- [ ] Category strategy stated (make/buy, single/multi).
- [ ] Criteria & weights agreed before scoring.
- [ ] Technical and capability screens done.
- [ ] Unqualified candidates routed to audit.
- [ ] Supply risk assessed (geo, dependency, capacity).
- [ ] Single-source flagged to Human Owner.

## 9. Common Mistakes

- ❌ Scoring on price alone, ignoring risk/continuity.
- ❌ Shortlisting unqualified suppliers.
- ❌ Letting Strategic Sourcing's view dominate without SM/Tech input.
- ❌ Hiding single-source instead of escalating.
- ❌ Sharing confidential info before an NDA.

## 10. Automation Opportunities

- ⚙ Auto-pull candidate pool from `/suppliers` by category.
- ⚙ Weighted scoring calculator from agreed criteria.
- ⚙ Risk heatmap (geography/dependency) from supplier data.
- ⚙ Auto-trigger supplier_audit for unqualified candidates.
