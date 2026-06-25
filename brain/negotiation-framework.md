---
id: framework-negotiation
title: Negotiation Framework
type: framework
used_by: [../workflows/price_negotiation.md, ../commands/prepare_negotiation.md]
status: active
updated: 2026-06-25
---

# Negotiation Framework

> The structure for planning a negotiation: anchor, target, BATNA, levers, and concessions.

## Purpose
Negotiate from evidence and leverage — not pressure — to reach target without breaking trust.

## When to Use
Inside [prepare_negotiation](../commands/prepare_negotiation.md) and
[price_negotiation.md](../workflows/price_negotiation.md).

## Decision Inputs

| Input | Source |
|-------|--------|
| Should-cost / target | [cost_breakdown](../skills/cost_breakdown.md) |
| Current price / quotes | `/rfq`, `/cost_down` |
| BATNA (alternative) | [supplier-selection-framework](supplier-selection-framework.md) |
| Supplier leverage / dependency | `/suppliers`, risk register |

## Framework (plan structure)

| Element | Define |
|---------|--------|
| Anchor | Opening position (near should-cost) |
| Target | Realistic goal (should-cost + fair margin) |
| Walk-away | Worst acceptable; tied to BATNA |
| BATNA | Best alternative if no deal |
| Levers | Volume, term, multi-year, tooling, payment, mix |
| Concession ladder | Ordered give/get; never give free |
| ZOPA | Overlap between our walk-away and theirs |

## Decision Rule
- Open at anchor; trade down the concession ladder toward target.
- Accept if ≤ target; if between target and walk-away, weigh BATNA & relationship.
- Below walk-away with no BATNA → **single-source leverage gap → escalate**.

## Escalation / Commitment Gate
- Agreed price / term = **D3 → Human Owner**. Never disclose a rival's quote.

## Pitfalls
- ❌ Negotiating without should-cost or BATNA.
- ❌ Leaking a competing quote for leverage (confidentiality).
- ❌ Giving concessions without getting value back.

## Links
- Workflow: [price_negotiation.md](../workflows/price_negotiation.md)
- Frameworks: [cost-down-framework](cost-down-framework.md), [decision-matrix](decision-matrix.md)
- Knowledge: `../knowledge/negotiation/`
