---
id: cmd-prepare-negotiation
title: /prepare_negotiation
type: command
trigger: "/prepare_negotiation <RFQ-id | part> [target]"
dispatches_to: [../workflows/price_negotiation.md]
owner: Chief of Staff
status: active
updated: 2026-06-25
---

# /prepare_negotiation

> Build the evidence pack and plan for a price negotiation: should-cost anchor,
> BATNA, levers, and concession ladder.

## Purpose
Equip RFQ Management to negotiate from facts, not pressure — closing the gap to target.

## Invocation

```
/prepare_negotiation <RFQ-id | part> [target]
```

| Argument | Required | Meaning |
|----------|----------|---------|
| RFQ-id / part | yes | What is being priced (`RFQ-YYYY-NNN` or part) |
| target | no | Target price / should-cost reference |

## Preconditions
- A defensible should-cost/target exists; spec is fixed for the item.

## What It Does (dispatch)
1. [Chief of Staff] Validate; link the RFQ/cost record.
2. [Cost Reduction] Confirm should-cost via [cost_breakdown](../skills/cost_breakdown.md); set target & walk-away.
3. [Strategic Sourcing] Define BATNA (alternative supplier/quote).
4. [RFQ Management] Assemble negotiation brief (levers, concession ladder, evidence).
5. → Hands to [price_negotiation.md](../workflows/price_negotiation.md) to execute.

## Memory Routing
Per [architecture.md](../memory/architecture.md).
- Canonical record: negotiation brief in `/rfq/<id>/` or `/cost_down/<id>/`
- Stable ID: reuses the parent `RFQ-` / `CD-` id
- Index: parent row in `rfq_database` / `cost_database`

## Outputs

| Output | Destination |
|--------|-------------|
| Negotiation brief (target, BATNA, levers) | `/rfq/<id>/` or `/cost_down/<id>/` |

## Approval Gates
- Preparation is D0/D2. **Agreed price / term change (D3):** Human Owner.

## Example
```
/prepare_negotiation RFQ-2026-014 target=42THB
```

## Links
- Workflow: [price_negotiation.md](../workflows/price_negotiation.md)
- Skills: [cost_breakdown.md](../skills/cost_breakdown.md), [compare_quotation.md](../skills/compare_quotation.md)
