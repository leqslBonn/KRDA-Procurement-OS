---
id: cmd-new-rfq
title: /new_rfq
type: command
trigger: "/new_rfq <part> <qty/EAU> [target]"
dispatches_to: [../workflows/supplier_selection.md, ../workflows/rfq.md]
owner: Chief of Staff
status: active
updated: 2026-06-25
---

# /new_rfq

> Start an RFQ: ensure a shortlist exists, build and issue the quote package, and
> drive it to an award recommendation.

## Purpose
Convert a sourcing need into competitive, comparable quotes — traceable end to end.

## Invocation

```
/new_rfq <part> <qty/EAU> [target] [suppliers]
```

| Argument | Required | Meaning |
|----------|----------|---------|
| part | yes | Part / scope to quote (spec ref) |
| qty/EAU | yes | Quantity / estimated annual usage |
| target | no | Should-cost / target price |
| suppliers | no | Pre-named shortlist; else selection runs |

## Preconditions
- Validated spec & acceptance criteria exist ([technical_review](../skills/technical_review.md)).
- Shortlist suppliers are `qualified`/`conditional`, or selection will run.

## What It Does (dispatch)
1. [Chief of Staff] Validate; assign `RFQ-YYYY-NNN`; dedup-check `rfq_database`.
2. [Strategic Sourcing] If no shortlist → run [supplier_selection.md](../workflows/supplier_selection.md).
3. [RFQ Management] Run [rfq.md](../workflows/rfq.md) — package, issue, collect, compare.
4. [Cost/Tech/Supplier Dev] Cost, technical, and risk checks on quotes.
5. [RFQ Management] Produce award recommendation → escalate to Human Owner.

## Memory Routing
Per [architecture.md](../memory/architecture.md).
- Canonical record: `/rfq/RFQ-YYYY-NNN-<slug>/`
- Stable ID: `RFQ-YYYY-NNN`
- Index register row: `../memory/rfq_database.md`

## Outputs

| Output | Destination |
|--------|-------------|
| RFQ package, bid tab, award rec | `/rfq/RFQ-YYYY-NNN-<slug>/` |
| Index row | `../memory/rfq_database.md` |

## Approval Gates
- **Award (D3):** Human Owner. **Single-source (D3):** Human Owner.

## Example
```
/new_rfq "bracket PN-12345" 50000/yr target=42THB
```

## Links
- Workflows: [supplier_selection.md](../workflows/supplier_selection.md), [rfq.md](../workflows/rfq.md)
- Skills: [compare_quotation.md](../skills/compare_quotation.md), [rfq_summary.md](../skills/rfq_summary.md)
- Register: [rfq_database.md](../memory/rfq_database.md)
