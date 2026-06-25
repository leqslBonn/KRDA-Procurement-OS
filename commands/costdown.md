---
id: cmd-costdown
title: /costdown
type: command
trigger: "/costdown <part/category> [target%]"
dispatches_to: [../workflows/cost_down.md]
owner: Chief of Staff
status: active
updated: 2026-06-25
---

# /costdown

> Open a cost-down case: build should-cost, pick a lever, and drive to a validated,
> realized saving.

## Purpose
Pursue measurable, evidence-based savings on a part/category without compromising spec.

## Invocation

```
/costdown <part/category> [target%] [lever]
```

| Argument | Required | Meaning |
|----------|----------|---------|
| part/category | yes | Target of the cost-down |
| target% | no | Savings goal (e.g. 15%) |
| lever | no | negotiation / VA-VE / resource / volume / terms |

## Preconditions
- Baseline price × volume known and sourced (not `TBD`).

## What It Does (dispatch)
1. [Chief of Staff] Validate; assign `CD-YYYY-NNN`; dedup-check `cost_database`.
2. [Cost Reduction] Set baseline; build should-cost via [cost_breakdown](../skills/cost_breakdown.md).
3. [Cost Reduction] Identify levers; run [cost_down.md](../workflows/cost_down.md).
4. [Tech/RFQ] Spec-change → engineering_change; negotiation → prepare_negotiation/rfq.
5. [Cost Reduction] Validate saving vs baseline → escalate realization to Human Owner.

## Memory Routing
Per [architecture.md](../memory/architecture.md).
- Canonical record: `/cost_down/CD-YYYY-NNN-<slug>/`
- Stable ID: `CD-YYYY-NNN`
- Index register row: `../memory/cost_database.md`; totals in `/cost_down/savings-register.md`

## Outputs

| Output | Destination |
|--------|-------------|
| Should-cost, savings case | `/cost_down/CD-YYYY-NNN-<slug>/` |
| Index row | `../memory/cost_database.md` |

## Approval Gates
- **Price change / realization (D3):** Human Owner. **Spec change (D3):** Human Owner.

## Example
```
/costdown "shaft PN-77890" 12% lever=negotiation
```

## Links
- Workflow: [cost_down.md](../workflows/cost_down.md)
- Skills: [cost_breakdown.md](../skills/cost_breakdown.md)
- Register: [cost_database.md](../memory/cost_database.md)
