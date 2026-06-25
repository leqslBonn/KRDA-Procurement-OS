---
id: cmd-new-supplier
title: /new_supplier
type: command
trigger: "/new_supplier <name> [commodity] [country]"
dispatches_to: [../workflows/supplier_audit.md]
owner: Chief of Staff
status: active
updated: 2026-06-25
---

# /new_supplier

> Onboard a supplier: create its canonical record, index it, and (if needed) start
> qualification.

## Purpose
Stand up a new supplier in the system as a single source of truth, ready to be
qualified and sourced.

## Invocation

```
/new_supplier <name> [commodity] [country]
```

| Argument | Required | Meaning |
|----------|----------|---------|
| name | yes | Supplier legal/short name |
| commodity | no | Commodity/category it supplies (`CMD-`) |
| country | no | Location |

## Preconditions
- Pre-write search done — supplier not already in `supplier_database` (no duplicate).

## What It Does (dispatch)
1. [Chief of Staff] Validate; dedup-check `supplier_database`. Exists → update, stop.
2. [Supplier Development] Create record from `../suppliers/_TEMPLATE/`; set status `prospective`.
3. [Supplier Development] Add index row to `supplier_database`; link `commodity_database`.
4. [Strategic Sourcing] If sourcing intended → assess via [supplier_risk](../skills/supplier_risk.md).
5. [Supplier Development] If qualification needed → run [supplier_audit.md](../workflows/supplier_audit.md).

## Memory Routing
Per [architecture.md](../memory/architecture.md).
- Canonical record: `/suppliers/<slug>/README.md`
- Stable ID: `SUP-<slug>`
- Index register row: `../memory/supplier_database.md` (+ `commodity_database` link)

## Outputs

| Output | Destination |
|--------|-------------|
| Supplier record | `/suppliers/<slug>/` |
| Index row | `../memory/supplier_database.md` |
| Qualification (if run) | `/suppliers/<slug>/audits/` |

## Approval Gates
- Onboarding is D0. Any committed spend/tooling for development → Human Owner (D3).
- Disqualification of a critical supplier → Human Owner (D3).

## Example
```
/new_supplier "Siam Casting Co." casting TH
```

## Links
- Workflow: [supplier_audit.md](../workflows/supplier_audit.md)
- Skills: [supplier_risk.md](../skills/supplier_risk.md), [supplier_scorecard.md](../skills/supplier_scorecard.md)
- Register: [supplier_database.md](../memory/supplier_database.md)
