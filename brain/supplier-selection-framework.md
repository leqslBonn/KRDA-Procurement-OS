---
id: framework-supplier-selection
title: Supplier Selection Framework
type: framework
used_by: [../workflows/supplier_selection.md, ../skills/supplier_risk.md]
status: active
updated: 2026-06-25
---

# Supplier Selection Framework

> The criteria and weighting by which a supplier is shortlisted or chosen — total
> value, not lowest price.

## Purpose
Standardize how KRDA picks suppliers so decisions are consistent, risk-aware, and defensible.

## When to Use
Inside [supplier_selection.md](../workflows/supplier_selection.md) (score & rank step).

## Decision Inputs

| Input | Source |
|-------|--------|
| Candidate suppliers | `/suppliers`, market scan |
| Technical fit | technical_review (SE) |
| Capability / quality | supplier_scorecard (SM) |
| Risk | [supplier-risk-framework](supplier-risk-framework.md) |

## Framework (criteria & logic)

| Criterion | Default weight | How scored (1–5) |
|-----------|:---:|------------------|
| Technical capability / fit | 25% | Meets spec & process capability |
| Quality (PPM, certs, system) | 20% | Track record + system maturity |
| Total cost (TCO) | 20% | Price + logistics + tooling + risk cost |
| Delivery / lead time | 15% | Reliability & responsiveness |
| Supply risk | 15% | Inverse of [risk severity](supplier-risk-framework.md) |
| Financial / continuity | 5% | Stability, capacity headroom |

Weights are the default; a category strategy may re-weight (record the change).

## Decision Rule
- Weighted score = Σ(weight × criterion score). Rank descending.
- **Gate:** any candidate failing technical or quality minimums is excluded regardless of price.
- Shortlist top candidates with ≥2 viable; if only 1 → single-source path.

## Escalation / Commitment Gate
- Selection is **D2** (recommendation). Single/sole-source = **D3 → Human Owner**.

## Pitfalls
- ❌ Letting price dominate the weighted score.
- ❌ Scoring after seeing prices (set weights first).
- ❌ Ignoring continuity/single-source risk.

## Links
- Workflow: [supplier_selection.md](../workflows/supplier_selection.md)
- Frameworks: [supplier-risk-framework](supplier-risk-framework.md), [decision-matrix](decision-matrix.md)
- Knowledge: `../knowledge/strategic-sourcing/`, `../knowledge/supplier-management/`
