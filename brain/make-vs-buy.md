---
id: framework-make-vs-buy
title: Make vs Buy Framework
type: framework
used_by: [../workflows/supplier_selection.md]
status: active
updated: 2026-06-25
---

# Make vs Buy Framework

> The logic for deciding whether KRDA makes a part/process internally or buys it.

## Purpose
Make a defensible make/buy (and insource/outsource) decision balancing cost,
capability, capacity, risk, and strategy.

## When to Use
At category strategy and major sourcing decisions (in
[supplier_selection.md](../workflows/supplier_selection.md)).

## Decision Inputs

| Input | Source |
|-------|--------|
| Internal cost & capacity | `../company/`, Manufacturing knowledge |
| External should-cost / quotes | [cost_breakdown](../skills/cost_breakdown.md), `/rfq` |
| Strategic importance / IP | category strategy |
| Risk | [supplier-risk-framework](supplier-risk-framework.md) |

## Framework (criteria & logic)

| Factor | Favors MAKE | Favors BUY |
|--------|-------------|-----------|
| Cost (TCO) | Internal lower at volume | External lower |
| Core competence / IP | Strategic, proprietary | Commodity |
| Capacity | Spare capacity | Capacity constrained |
| Capability | Have process & quality | Supplier superior |
| Volume / volatility | Stable, high volume | Low/volatile |
| Risk & control | Need tight control | Acceptable to outsource |
| Speed | Internal faster | Supplier faster |

## Decision Rule
- Score each factor; weight by category strategy.
- **Strategic/IP-critical** items bias to MAKE even at cost premium (record rationale).
- Pure cost/commodity with qualified suppliers bias to BUY.

## Escalation / Commitment Gate
- Make/buy shifts capex, headcount, or strategy → **D3/D4 → Human Owner**.

## Pitfalls
- ❌ Deciding on unit price alone (ignore TCO, capacity, IP).
- ❌ Outsourcing a core competence for short-term saving.

## Links
- Workflow: [supplier_selection.md](../workflows/supplier_selection.md)
- Frameworks: [cost-down-framework](cost-down-framework.md), [decision-matrix](decision-matrix.md)
- Knowledge: `../knowledge/manufacturing/`, `../knowledge/strategic-sourcing/`
