---
id: skill-compare-quotation
title: Compare Quotation
type: skill
owner: RFQ Management (CC)
used_by: [rfq.md, price_negotiation.md]
uses: [../templates/bid-tab.md, ../knowledge/sourcing/]
status: active
updated: 2026-06-25
---

# Compare Quotation

> Normalize multiple supplier quotes to a like-for-like basis and rank them on
> agreed criteria.

## Purpose
Produce a defensible, apples-to-apples comparison that supports an award
recommendation — not a raw price list.

## When to Use
Inside [rfq.md](../workflows/rfq.md) (bid-tab step) and
[price_negotiation.md](../workflows/price_negotiation.md) (re-evaluation).

## Inputs

| Input | Source |
|-------|--------|
| Supplier quotes | `/rfq/<id>/quotes/` (confidential) |
| Should-cost / target | Cost Reduction → `/cost_down` |
| Evaluation criteria & weights | `../knowledge/sourcing/` *(TBD)* |

## Method

1. **Normalize commercial basis** — same currency, Incoterms, payment terms;
   amortize tooling/NRE over EAU.
2. **Normalize scope** — ensure each quote covers identical scope/qty; adjust gaps.
3. **Tabulate** — one column per supplier in `../templates/bid-tab.md`.
4. **Score** — apply agreed criteria/weights (price, lead time, MOQ, quality, risk, terms).
5. **Reference should-cost** — show variance of best quote vs target.
6. **Rank & flag** — best total value; flag single-source, over-target, spec-fail.

## Output

| Output | Destination / Template |
|--------|------------------------|
| Bid tabulation | `../templates/bid-tab.md` → `/rfq/<id>/bid-tab.md` |

## Quality Bar
- [ ] Every quote on the same normalized basis (state adjustments).
- [ ] Criteria/weights fixed **before** scoring.
- [ ] Variance vs should-cost shown.
- [ ] No supplier's quote exposed to another.

## Common Errors
- ❌ Comparing raw unit prices across different Incoterms/tooling.
- ❌ Changing weights after seeing the prices.
- ❌ Ignoring lead time / risk because price looks good.

## Limitations / Guardrails
- Produces a recommendation only — award is D3 (Human Owner).
- Quotes are confidential; comparison stays in the RFQ record.

## Links
- Workflows: [rfq.md](../workflows/rfq.md), [price_negotiation.md](../workflows/price_negotiation.md)
- Template: [bid-tab.md](../templates/bid-tab.md)
- Knowledge: `../knowledge/sourcing/`
