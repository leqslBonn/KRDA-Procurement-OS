---
id: wf-nda
title: NDA (Non-Disclosure Agreement)
type: workflow
owner: Procurement Lead (OPL)
status: active
updated: 2026-06-25
---

# NDA (Non-Disclosure Agreement)

> Put confidentiality protection in place **before** sharing KRDA confidential
> information with a supplier. A legal commitment — Human Owner signs.

## Flow (BPMN-like)

Legend (canonical: [README](README.md#bpmn-notation)):
`●` start · `[task — Role]` · `◇Gn` gateway · `⚑` escalate · `⇒` calls workflow · `◉` end

```
● need to share confidential info (from selection/rfq)
  └─► ◇G1 <valid NDA already on file & covers scope?>
        ├─ yes ─► [Reuse — Procurement Lead] ──► ◉ coverage confirmed
        └─ no ──► [Define disclosure scope — requesting employee]
                    └─► [Prepare NDA draft — Procurement Lead]
                    └─► ⚑ L3 Human Owner (legal review + sign)
                          └─► ◇G2 <signed?>
                                ├─ no ──► ⚑ hold; no info shared
                                └─ yes ─► [Record in /contracts + expiry to /schedule — Procurement Lead]
                                            └─► [Release to requester] ──► ◉ coverage confirmed
```

## 1. Purpose
Protect KRDA's confidential information before any supplier disclosure.

## 2. Inputs

| Input | Source |
|-------|--------|
| Supplier identity | `/suppliers/<supplier>/` |
| Information to share (scope) | requesting workflow |
| NDA template / standard terms | `/contracts`, `../knowledge/` *(TBD)* |
| Existing NDA status | `/contracts` |

## 3. Required AI Employees

| Employee | Dept | Role in this flow |
|----------|------|-------------------|
| Procurement Lead | OPL | Owner — coordinate, draft, record |
| Requesting employee | any | Define disclosure scope/purpose |
| (Human Owner) | — | Legal review & signature (not an AI role) |

## 4. Decision Gates

| Gate | Condition | Yes → | No → |
|------|-----------|-------|------|
| G1 | Valid NDA already covers scope? | Reuse, done | Draft new NDA |
| G2 | Signed by Human Owner? | Record & release | Hold — no info shared |

## 5. Outputs

| Output | Destination |
|--------|-------------|
| NDA record & key terms | `/contracts/CTR-<id>-<supplier>/README.md` |
| Signed document reference | `/contracts/CTR-<id>-<supplier>/documents/` |
| Expiry / review entry | `../schedule/` |

## 6. Escalation Rules
- **L1/L2 (Procurement Lead):** scope definition, supplier term pushback.
- **L3 (Human Owner):** NDA is a legal commitment (D3) — review and signature only by Human Owner.

## 7. KPI

| KPI | Target |
|-----|--------|
| Disclosures with NDA in place | 100% |
| NDA turnaround time | TBD |
| Expired-NDA disclosures | 0 |

## 8. Checklist

- [ ] Genuine, scoped need to disclose (what/why/duration).
- [ ] Existing NDA checked before drafting a new one.
- [ ] Draft states scope, term, permitted use, governing law.
- [ ] Human Owner reviewed & signed (AI did not sign).
- [ ] Recorded in `/contracts`; expiry tracked in `/schedule`.
- [ ] No info shared until coverage is `active`.

## 9. Common Mistakes

- ❌ Sharing drawings/specs before the NDA is active.
- ❌ Duplicating an NDA that already exists.
- ❌ AI "agreeing"/signing — only the Human Owner signs.
- ❌ Over-broad disclosure scope.
- ❌ Losing track of NDA expiry.

## 10. Automation Opportunities

- ⚙ Auto-check `/contracts` for existing valid NDA by supplier.
- ⚙ NDA draft generated from standard terms + scope.
- ⚙ Expiry reminders via `/schedule`.
- ⚙ Block confidential hand-offs until NDA status = `active`.
