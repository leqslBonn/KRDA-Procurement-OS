---
id: wf-sap
title: SAP PR/PO Preparation & Posting
type: workflow
owner: SAP Purchasing (TS)
status: active
updated: 2026-06-25
---

# SAP PR/PO Preparation & Posting

> Turn an approved decision into a clean, SAP-ready PR/PO and post it only after
> Human Owner authorization.

## Flow (BPMN-like)

Legend (canonical: [README](README.md#bpmn-notation)):
`●` start · `[task — Role]` · `◇Gn` gateway · `⚑` escalate · `⇒` calls workflow · `◉` end

```
● approved award / price / requisition
  └─► ◇G1 <valid D3 approval exists & matches scope?>
        ├─ no ──► ⚑ STOP; escalate (L2/L3) — never post unauthorized
        └─ yes ─► [Check master data (vendor/material/info/source) — SAP Purch]
                    └─► ◇G2 <master data complete?>
                          ├─ no ──► [Create/clean master data — SAP Purch]
                          └─ yes ─► [Prepare PR — SAP Purch]
                                      └─► [Prepare PO content — SAP Purch]
                                      └─► [Pre-post review — SAP Purch]
                                      └─► ⚑ L3 Human Owner (authorize posting)
                                            └─► [Record txn + audit trail — SAP Purch]
                                            └─► [Notify Analytics — SAP Purch] ──► ◉ posted
```

## 1. Purpose
Produce accurate, audit-clean SAP transactions; never post without authorization.

## 2. Inputs

| Input | Source |
|-------|--------|
| Approved award / price / requisition | RFQ Management (CC) / Lead |
| Supplier & material master data | `/suppliers`, `../company/` |
| SAP field map & master-data rules | `../knowledge/sap/` *(TBD)* |

## 3. Required AI Employees

| Employee | Dept | Role in this flow |
|----------|------|-------------------|
| SAP Purchasing | TS | Owner — PR/PO prep, master data, record |
| Procurement Automation | TS | Templatize/auto repetitive entries |
| RFQ Management | CC | Source of approved award |
| Procurement Analytics | IP | Receives posted spend |
| Procurement Lead | OPL | Route posting authorization |

## 4. Decision Gates

| Gate | Condition | Yes → | No → |
|------|-----------|-------|------|
| G1 | Valid D3 approval matches scope? | Continue | ⚑ STOP, escalate |
| G2 | Master data complete? | Prepare PR/PO | Create/clean first |

## 5. Outputs

| Output | Destination |
|--------|-------------|
| SAP-ready PR/PO record | `/projects/<id>/`, `/contracts` if applicable |
| Master-data update note | `/suppliers/<supplier>/` |
| Posted transaction reference | `/projects/<id>/` |

## 6. Escalation Rules
- **L1 (TS head / SAP Purch):** master-data gaps, field-mapping questions.
- **L2 (Procurement Lead):** missing/mismatched approval.
- **L3 (Human Owner):** posting/releasing a transaction (D3); master-data change affecting commitments.

## 7. KPI

| KPI | Target |
|-----|--------|
| PR/PO data accuracy (first-pass) | TBD |
| Master-data defect rate | TBD |
| Prep cycle time | TBD |
| Unauthorized postings | 0 |

## 8. Checklist

- [ ] D3 approval record verified against scope/price.
- [ ] Vendor code, material, info record, source list present.
- [ ] PR/PO fields validated (price, terms, delivery, Incoterms).
- [ ] Pre-post review done.
- [ ] Human Owner authorized posting.
- [ ] Audit trail recorded; Analytics notified.

## 9. Common Mistakes

- ❌ Posting (or implying posting) without authorization.
- ❌ Assuming SAP field values instead of using `TBD`.
- ❌ Duplicating master data instead of reconciling.
- ❌ Mismatched PO vs approved award terms.
- ❌ No audit trail for the transaction.

## 10. Automation Opportunities

- ⚙ Auto-map approved award → PO fields.
- ⚙ Master-data completeness pre-check before prep.
- ⚙ Detect repetitive PR patterns → templated entry (Automation).
- ⚙ Auto-push posted spend to `/dashboard`.
