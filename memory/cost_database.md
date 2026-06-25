---
id: cost-database
title: Cost Database (Recall Index)
type: register-index
status: active
updated: 2026-06-25
---

# Cost Database (Recall Index)

> Index of cost-down cases and the cost-knowledge they draw on. **Index only —
> not the source of truth.**

## Source of Truth
- Cost-down cases & should-cost models: canonical in [`/cost_down`](../cost_down/README.md).
- Validated savings total: canonical in `/cost_down/savings-register.md`.
- Cost rates & benchmarks: canonical in `/knowledge/cost/`.

This file indexes cases for recall and points to those sources. It does **not**
restate savings totals (see the register) or rates (see knowledge).

## Schema (newest on top)

| Case ID | Part/Category | Lever | Status | Baseline | Validated Saving | Realized? | Record |
|---------|---------------|-------|--------|----------|------------------|-----------|--------|
| _CD-2026-001_ | _example_ | _negotiation_ | _idea_ | _TBD_ | _TBD_ | _no_ | _`../cost_down/CD-2026-001-.../`_ |

> No cost-down cases yet.

## Conventions
- One row per case; `Record` links to `../cost_down/<id>/`.
- `Status`: idea → in-progress → validated → realized.
- Totals are **not** summed here — link `/cost_down/savings-register.md`.

## Links
- Cases: [`/cost_down`](../cost_down/README.md) · Register: `../cost_down/savings-register.md`
- Cost rates: [`/knowledge/cost`](../knowledge/index.md)
- Workflows: [`cost_down.md`](../workflows/cost_down.md), [`price_negotiation.md`](../workflows/price_negotiation.md)
