---
id: wf-rfq
title: RFQ-to-Award
type: workflow
owner: RFQ Management (CC)
status: active
updated: 2026-06-25
---

# RFQ-to-Award

> Turn a validated sourcing need into competitive, comparable quotes and an
> approved award.

## Flow (BPMN-like)

Legend (canonical: [README](README.md#bpmn-notation)):
`●` start · `[task — Role]` · `◇Gn` gateway · `⚑` escalate · `⇒` calls workflow · `◉` end

```
● need-to-quote
  └─► [Assemble RFQ package — RFQ Mgmt]
        └─► ◇G1 <confidential info shared?>
              ├─ yes ─► ⇒ nda.md ─┐
              └─ no ──────────────┤
                                  └─► [Issue RFQ + due date — RFQ Mgmt]
        └─► [Collect quotes (sealed) — RFQ Mgmt]
        └─► [Normalize + build bid tab — RFQ Mgmt]
        └─► [Cost check — Cost Reduction] ∥ [Tech check — Tech Purchasing] ∥ [Risk check — Supplier Dev + Strat Sourcing]
        └─► ◇G2 <≥3 competitive & spec-met?>
              ├─ no ──► ⚑ re-broaden (Strat Sourcing) / ⇒ price_negotiation.md
              └─ yes ─► [Award recommendation (D2) — RFQ Mgmt]
                          └─► ◇G3 <single-source OR > target?>
                                ├─ yes ─► ⚑ L3 Human Owner
                                └─ no ──► ⚑ L3 Human Owner (award approval)
                                              └─► [On approval ⇒ sap.md] ──► ◉ awarded
```

## 1. Purpose
Run a fair, traceable quote process and produce a defensible, approved award.

## 2. Inputs

| Input | Source |
|-------|--------|
| Validated spec & acceptance criteria | Technical Purchasing (SE) |
| Supplier shortlist | Strategic Sourcing (SE), `/suppliers` |
| Should-cost / target | Cost Reduction (CC) → `/cost_down` |
| Evaluation & award rules | `../knowledge/sourcing/` *(TBD)* |

## 3. Required AI Employees

| Employee | Dept | Role in this flow |
|----------|------|-------------------|
| RFQ Management | CC | Owner — package, issue, compare, recommend |
| Cost Reduction | CC | Quote vs should-cost/target |
| Technical Purchasing | SE | Confirm quotes meet spec |
| Strategic Sourcing | SE | Shortlist breadth, supply risk |
| Supplier Development | SM | Capacity / continuity check |
| Procurement Lead | OPL | Route award to Human Owner |

## 4. Decision Gates

| Gate | Condition | Yes → | No → |
|------|-----------|-------|------|
| G1 | Confidential info shared with supplier? | ⇒ [nda.md](nda.md) | Issue RFQ |
| G2 | ≥3 competitive quotes & spec met? | Award recommendation | Re-broaden / negotiate |
| G3 | Single-source or over target? | ⚑ Human Owner (explicit) | ⚑ Human Owner (award) |

## 5. Outputs

| Output | Destination |
|--------|-------------|
| RFQ package | `/rfq/<id>/rfq.md` |
| Bid tabulation | `/rfq/<id>/bid-tab.md` |
| Award recommendation + approval | `/rfq/<id>/award.md` |

## 6. Escalation Rules
- **L1 (CC head / RFQ Mgmt):** missing/late quotes, normalization disputes.
- **L2 (Procurement Lead):** shortlist too narrow, cross-dept disagreement on award.
- **L3 (Human Owner):** every award (D3); single-source; award over target with no alternative.

## 7. KPI

| KPI | Target |
|-----|--------|
| RFQ cycle time (issue→award rec) | TBD |
| Competitive quotes per RFQ | ≥3 |
| Award-vs-target variance | ≤0% |
| Confidentiality breaches | 0 |

## 8. Checklist

- [ ] Spec controlled & acceptance criteria defined (not `TBD`).
- [ ] NDA coverage confirmed before sharing confidential info.
- [ ] Invited suppliers `qualified`/`conditional`.
- [ ] Quotes stored sealed; no cross-disclosure.
- [ ] Bid tab normalized like-for-like.
- [ ] Award rationale, criteria, weights recorded.
- [ ] Human Owner approval recorded before any commitment.

## 9. Common Mistakes

- ❌ Awarding before Human Owner approval.
- ❌ Comparing un-normalized quotes (different Incoterms/tooling).
- ❌ Leaking one supplier's price to another for leverage.
- ❌ Accepting <3 quotes without documenting why.
- ❌ Treating single-source as routine instead of escalating.

## 10. Automation Opportunities

- ⚙ Auto-generate RFQ package from spec + shortlist.
- ⚙ Auto-normalize quotes into the bid tab (currency/Incoterms/tooling).
- ⚙ Due-date reminders to suppliers via `/schedule`.
- ⚙ Auto-flag single-source / over-target before award.
