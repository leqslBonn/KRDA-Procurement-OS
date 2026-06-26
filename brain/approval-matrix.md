---
id: framework-approval-matrix
title: Approval Matrix
type: framework
used_by: [all employees, all workflows]
status: active
updated: 2026-06-26
links: [../knowledge/procurement/procedure.md, ../company/overview.md]
---

# Approval Matrix

> Who approves what — the single, consolidated authority map for KRDA procurement.
> Source: KB-PROC-001 (TH v2, Jan 2023 — authoritative).

## Purpose
Make it unambiguous which decisions an employee may take alone and which require the
Human Owner. Operationalizes the [decision-framework](../company/decision-framework.md)
commitment gate.

## When to Use
Before any decision that might bind KRDA — every workflow's approval gate points here.

---

## 1. Direct Purchase Authority (Single Quote / Price Agreement ≤5,000 THB)

| Amount (THB) | Approver |
|---|---|
| 0 – 10,000 | Department Manager (DM) |
| 10,001 – 20,000 | Vice President (VP) |
| > 20,000 | **President** |

> **Note:** TH v2 (Jan 2023) authoritative. EN v1 (May 2021) incorrectly states >26,000 → President.
> Cite: [KB-PROC-001 §3](../knowledge/procurement/procedure.md).

---

## 2. Price Comparison Approval Matrix (5,001 – 1,000,000 THB)

| Amount (THB) | Preparer | Level 1 | Level 2 | Level 3 | Level 4 | Final Approver |
|---|---|---|---|---|---|---|
| 0 – 100,000 | CE | Dept.Mgr ✅ | — | — | — | Dept.Mgr |
| 100,001 – 500,000 | CE | Dept.Mgr | Div.Mgr ✅ | — | — | Div.Mgr |
| 500,001 – 1,000,000 | CE | Dept.Mgr | Div.Mgr | Procurement Mgr ✅ | — | Procurement Mgr |
| 1,000,001 – 2,000,000 | CE | Dept.Mgr | Div.Mgr | Procurement Mgr | VP ✅ | VP |
| > 2,000,000 | CE | Dept.Mgr | Div.Mgr | Procurement Mgr | VP | **President** ✅ |

CE = Procurement Engineer (AI preparer role). ✅ = final authority at that band.

---

## 3. Competitive Bidding (> 1,000,000 THB)

Same approval chain as Price Comparison >1M above. Bidding required (sealed, ≥3 suppliers).
See [KB-PROC-001 §5](../knowledge/procurement/procedure.md) for bidding rules.

---

## 4. Commitment-Type Authority (AI Role)

| Decision | AI action | Human Owner action |
|----------|-----------|-------------------|
| Operational work (D0) | ✅ act | informed |
| Recommendation (D2) | propose | informed |
| Award an RFQ | prepare package | ✅ **approve** |
| Agree a price / negotiation result | prepare brief | ✅ **approve** |
| Single / sole-source designation | flag + escalate | ✅ **approve** |
| Post a PR/PO in SAP | prepare draft | ✅ **approve** |
| Sign an NDA / contract / term | draft | ✅ **approve** |
| Committed development / tooling spend | propose | ✅ **approve** |
| Disqualify a critical/sole supplier | propose + risk note | ✅ **approve** |
| Engineering change cut-in | prepare analysis | ✅ **approve** |
| Premium freight / expedite spend | propose | ✅ **approve** |
| New vendor creation in SAP | prepare docs | ✅ **approve** (dual: PU + Accounting) |
| Constitutional / structural change | propose | ✅ **approve** |

---

## Decision Rule
- If a row's Human Owner column is ✅, **no AI may approve it** — prepare and escalate.
- Use **amount bands above** to determine WHICH Human Owner (DM / Div.Mgr / VP / President).
- When unsure → **treat as a commitment and escalate (L3)**.

## Links
- Source: [knowledge/procurement/procedure.md](../knowledge/procurement/procedure.md) (KB-PROC-001)
- Company data: [company/overview.md](../company/overview.md)
- Governance: [decision-framework.md](../company/decision-framework.md), [escalation-rules.md](../company/organization/escalation-rules.md)
