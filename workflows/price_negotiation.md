---
id: wf-price-negotiation
title: Price Negotiation
type: workflow
owner: RFQ Management (CC)
status: active
updated: 2026-06-25
---

# Price Negotiation

> Prepare and run a fact-based negotiation to close the gap to target, then secure
> approval.

## Flow (BPMN-like)

Legend (canonical: [README](README.md#bpmn-notation)):
`●` start · `[task — Role]` · `◇Gn` gateway · `⚑` escalate · `⇒` calls workflow · `◉` end

```
● quote/price > target (from rfq.md or cost_down.md)
  └─► [Set target + walk-away/BATNA — Cost Reduction + RFQ Mgmt]
  └─► [Identify levers — RFQ Mgmt]
  └─► [Prepare brief (evidence, concession ladder) — RFQ Mgmt]
  └─► [Negotiate, log rounds — RFQ Mgmt]
  └─► [Re-evaluate vs target — Cost Reduction]
  └─► ◇G1 <target reached?>
        ├─ yes ─► [Recommend accept (D2) — RFQ Mgmt]
        └─ no ──► ◇G2 <alternative exists (BATNA)?>
                    ├─ yes ─► ⇒ rfq.md (re-source)
                    └─ no ──► ⚑ L3 Human Owner (single-source gap)
  └─► ◇G3 <supplier ties price to spec/term change?>
        ├─ spec ─► ⇒ engineering_change.md
        └─ term ─► ⚑ Human Owner via /contracts
  └─► ⚑ L3 Human Owner (approve agreed price)
        └─► [Realize ⇒ sap.md + ⇒ cost_down.md] ──► ◉ priced
```

## 1. Purpose
Secure the best defensible price using should-cost, benchmarks, and BATNA — not pressure.

## 2. Inputs

| Input | Source |
|-------|--------|
| Quotes / current price | `/rfq`, `/cost_down` |
| Should-cost & target | Cost Reduction (CC) |
| Supplier position / leverage | `/suppliers`, Strategic Sourcing (SE) |
| Benchmarks | `../knowledge/cost/` *(TBD)* |

## 3. Required AI Employees

| Employee | Dept | Role in this flow |
|----------|------|-------------------|
| RFQ Management | CC | Owner — commercial negotiation |
| Cost Reduction | CC | Should-cost, target, re-evaluation |
| Strategic Sourcing | SE | BATNA / alternative supplier |
| Procurement Lead | OPL | Route to Human Owner / contracts |

## 4. Decision Gates

| Gate | Condition | Yes → | No → |
|------|-----------|-------|------|
| G1 | Target reached? | Recommend accept | Check BATNA (G2) |
| G2 | Alternative (BATNA) exists? | ⇒ [rfq.md](rfq.md) re-source | ⚑ Human Owner (gap) |
| G3 | Price tied to spec/term change? | spec ⇒ [engineering_change.md](engineering_change.md) | term ⚑ Human Owner /contracts |

## 5. Outputs

| Output | Destination |
|--------|-------------|
| Negotiation brief & round log | `/cost_down/<id>/` or `/rfq/<id>/` |
| Agreed price recommendation | `/rfq/<id>/award.md` or `/cost_down/<id>/` |
| Approval record | same record (approver + date) |

## 6. Escalation Rules
- **L1 (CC head):** target/concession disputes.
- **L2 (Procurement Lead):** re-source decision, term routing.
- **L3 (Human Owner):** agreed price (D3); single-source leverage gap; term change.

## 7. KPI

| KPI | Target |
|-----|--------|
| Price gap closed vs target | TBD |
| Negotiation cycle time | TBD |
| Realized vs negotiated price | =100% |

## 8. Checklist

- [ ] Should-cost/target defensible (not a guess).
- [ ] BATNA defined before negotiating.
- [ ] Every round logged with outcome.
- [ ] No competing quote disclosed for leverage.
- [ ] Spec/term-linked asks routed correctly.
- [ ] Human Owner approval before commitment; realized in SAP.

## 9. Common Mistakes

- ❌ Negotiating without a should-cost anchor or BATNA.
- ❌ Disclosing a rival's quote (confidentiality breach).
- ❌ Agreeing a price/term without Human Owner approval.
- ❌ Accepting a spec change implicitly to hit price.
- ❌ Claiming the saving before it is realized in SAP.

## 10. Automation Opportunities

- ⚙ Auto-build negotiation brief from should-cost + quotes.
- ⚙ Concession-ladder calculator vs target/walk-away.
- ⚙ Track price gap closed across rounds.
- ⚙ Auto-route spec/term-linked asks to the right workflow.
