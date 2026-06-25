---
id: skill-rfq-summary
title: RFQ Summary
type: skill
owner: RFQ Management (CC)
used_by: [rfq.md]
uses: [../templates/bid-tab.md]
status: active
updated: 2026-06-25
---

# RFQ Summary

> Condense an RFQ and its bid tabulation into a one-page decision digest for the
> Chief of Staff / Human Owner.

## Purpose
Give the approver everything needed to decide an award fast — without reading the
full RFQ pack — while keeping quotes confidential.

## When to Use
End of [rfq.md](../workflows/rfq.md), before the award approval gate; feeds
[executive_report.md](executive_report.md).

## Inputs

| Input | Source |
|-------|--------|
| RFQ package | `/rfq/<id>/rfq.md` |
| Bid tabulation | `/rfq/<id>/bid-tab.md` |
| Should-cost / target | `/cost_down` |

## Method

1. **State the ask** — part/scope, qty/EAU, why sourcing now.
2. **Summarize the field** — #suppliers invited/quoted; normalization notes.
3. **Show the comparison** — top options on normalized total value (not raw price).
4. **Variance vs target** — best quote vs should-cost.
5. **Flags** — single-source, over-target, spec/risk concerns.
6. **Recommendation + decision required** — the award to approve (D3).

## Output

| Output | Destination / Template |
|--------|------------------------|
| One-page RFQ digest | `/rfq/<id>/award.md` (summary section) |

## Quality Bar
- [ ] Fits one page; decision is obvious.
- [ ] Numbers trace to the bid tab.
- [ ] Confidentiality preserved (no cross-supplier price exposure beyond the digest's controlled audience).

## Common Errors
- ❌ Dumping raw quotes instead of a normalized summary.
- ❌ Omitting the variance-vs-target.
- ❌ Burying the single decision required.

## Limitations / Guardrails
- Summarizes; the award decision is D3 (Human Owner).

## Links
- Workflow: [rfq.md](../workflows/rfq.md)
- Feeds: [executive_report.md](executive_report.md)
- Template: [bid-tab.md](../templates/bid-tab.md)
