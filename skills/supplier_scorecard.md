---
id: skill-supplier-scorecard
title: Supplier Scorecard
type: skill
owner: Supplier Development (SM)
used_by: [supplier_audit.md]
uses: [../templates/supplier-scorecard.md, ../knowledge/quality/, ../knowledge/taxonomy/]
status: active
updated: 2026-06-25
---

# Supplier Scorecard

> Compute and update a supplier's performance score across quality, delivery,
> cost, responsiveness, and capability.

## Purpose
Maintain one authoritative, current performance picture per supplier to drive
development and sourcing decisions.

## When to Use
Inside [supplier_audit.md](../workflows/supplier_audit.md) and on the scheduled
quarterly refresh (`/schedule`).

## Inputs

| Input | Source |
|-------|--------|
| Delivery & quality performance | `../dashboard/`, `/projects` |
| KPI definitions | `../knowledge/taxonomy/` *(TBD)* |
| Prior scorecard | `/suppliers/<supplier>/scorecard.md` |

## Method

1. **Pull metrics** — PPM/defects, OTD %, price competitiveness, responsiveness,
   capability — using the **single agreed KPI definitions**.
2. **Score each dimension** vs target; weight per category policy.
3. **Compute overall** and compare to prior period (trend ↑/↓).
4. **Set status signal** — qualified / conditional / at-risk.
5. **Write** the one authoritative scorecard; mirror status to `supplier_database`.

## Output

| Output | Destination / Template |
|--------|------------------------|
| Updated scorecard | `../templates/supplier-scorecard.md` → `/suppliers/<supplier>/scorecard.md` |

## Quality Bar
- [ ] Uses the single KPI definitions (no ad-hoc metrics).
- [ ] Every number sourced.
- [ ] One scorecard per supplier (no parallel versions).
- [ ] Trend vs prior period shown.

## Common Errors
- ❌ Inventing metrics outside the agreed taxonomy.
- ❌ Multiple conflicting scorecards for one supplier.
- ❌ Scoring without sourced data.

## Limitations / Guardrails
- Measures, does not decide disqualification (that is supplier_audit + Human Owner).

## Links
- Workflow: [supplier_audit.md](../workflows/supplier_audit.md)
- Template: [supplier-scorecard.md](../templates/supplier-scorecard.md)
- Knowledge: `../knowledge/quality/`, `../knowledge/taxonomy/`
- Register: [supplier_database.md](../memory/supplier_database.md)
