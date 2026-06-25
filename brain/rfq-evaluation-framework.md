---
id: framework-rfq-evaluation
title: RFQ Evaluation Framework
type: framework
used_by: [../workflows/rfq.md, ../skills/compare_quotation.md]
status: active
updated: 2026-06-25
---

# RFQ Evaluation Framework

> The criteria for normalizing and scoring quotes to a fair award recommendation.

## Purpose
Award on best total value on a like-for-like basis — transparent and defensible.

## When to Use
Inside [rfq.md](../workflows/rfq.md) and [compare_quotation](../skills/compare_quotation.md).

## Decision Inputs

| Input | Source |
|-------|--------|
| Normalized quotes | compare_quotation → `/rfq/<id>/bid-tab.md` |
| Should-cost / target | Cost Reduction |
| Technical pass/fail | [technical-purchasing-framework](technical-purchasing-framework.md) |
| Supplier risk | [supplier-risk-framework](supplier-risk-framework.md) |

## Framework (criteria & logic)

| Criterion | Default weight | Notes |
|-----------|:---:|-------|
| Total cost (normalized TCO) | 35% | Incl. tooling, logistics, terms |
| Technical conformance | 20% | Pass/fail gate + degree |
| Quality / capability | 15% | Scorecard, certs |
| Lead time / delivery | 15% | Reliability |
| Supply risk | 10% | Single-source, capacity |
| Commercial terms | 5% | Payment, warranty, flexibility |

## Decision Rule
- **Gate first:** technical fail or unqualified supplier = ineligible.
- Weighted score on eligible quotes; recommend highest total value.
- Show variance vs should-cost; require ≥3 competitive quotes or document why not.

## Escalation / Commitment Gate
- Award = **D3 → Human Owner**. Single-source or over-target with no alternative = **D3**.

## Pitfalls
- ❌ Picking lowest unit price over best total value.
- ❌ Un-normalized comparison (different Incoterms/tooling).
- ❌ Weights set after seeing prices.

## Links
- Workflow: [rfq.md](../workflows/rfq.md) · Skill: [compare_quotation.md](../skills/compare_quotation.md)
- Template: [bid-tab.md](../templates/bid-tab.md) · Framework: [decision-matrix](decision-matrix.md)
- Knowledge: `../knowledge/procurement/`
