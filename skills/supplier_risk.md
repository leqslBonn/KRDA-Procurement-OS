---
id: skill-supplier-risk
title: Supplier Risk Assessment
type: skill
owner: Strategic Sourcing (SE)
used_by: [supplier_selection.md, engineering_change.md]
uses: [../knowledge/sourcing/, ../memory/risk_database.md]
status: active
updated: 2026-06-25
---

# Supplier Risk Assessment

> Assess and score a supplier's/category's risk — supply, single-source, quality,
> compliance, financial, continuity.

## Purpose
Make supply risk explicit and tracked so decisions weigh continuity, not just cost.

## When to Use
Inside [supplier_selection.md](../workflows/supplier_selection.md) and when an
[engineering_change.md](../workflows/engineering_change.md) shifts the supply base.

## Inputs

| Input | Source |
|-------|--------|
| Supplier profile & capability | `/suppliers/<supplier>/` |
| Performance & scorecard | `/suppliers`, `../dashboard/` |
| Risk models | `../knowledge/sourcing/` *(TBD)* |

## Method

1. **Identify risk types** — supply, single/sole-source, quality, compliance,
   financial, geographic/continuity.
2. **Rate likelihood × impact** (L/M/H each) per risk.
3. **Compute severity** = likelihood × impact; sort highest first.
4. **Define mitigation** and owner for each material risk.
5. **Register** — log/update entry in `../memory/risk_database.md` (`RSK-YYYY-NNN`),
   linking the affected supplier/part.
6. **Escalate** material risks to the Human Owner (L3) via meeting_history.

## Output

| Output | Destination / Template |
|--------|------------------------|
| Risk entry | `../memory/risk_database.md` (native register) |

## Quality Bar
- [ ] All relevant risk types considered (not just price/quality).
- [ ] Severity scored consistently; sorted.
- [ ] Single-source exposure explicit.
- [ ] Material risks escalated and logged.

## Common Errors
- ❌ Treating single-source as routine.
- ❌ Logging a risk with no owner or mitigation.
- ❌ Duplicating supplier facts instead of linking the record.

## Limitations / Guardrails
- Assesses risk; mitigation actions that commit spend are D3 (Human Owner).
- Risk register is the canonical home — link, don't copy supplier data.

## Links
- Workflows: [supplier_selection.md](../workflows/supplier_selection.md), [engineering_change.md](../workflows/engineering_change.md)
- Register: [risk_database.md](../memory/risk_database.md)
- Escalation: [escalation-rules](../company/organization/escalation-rules.md)
