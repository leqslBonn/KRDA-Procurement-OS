---
id: framework-approval-matrix
title: Approval Matrix
type: framework
used_by: [all employees, all workflows]
status: active
updated: 2026-06-25
---

# Approval Matrix

> Who approves what — the single, consolidated authority map for the organization.

## Purpose
Make it unambiguous which decisions an employee may take alone and which require the
Human Owner. Operationalizes the [decision-framework](../company/decision-framework.md)
commitment gate.

## When to Use
Before any decision that might bind KRDA — every workflow's approval gate points here.

## Approval Matrix

| Decision | Owning employee | Dept Head | Procurement Lead | Human Owner |
|----------|:---:|:---:|:---:|:---:|
| Operational work (D0) | ✅ act | i | — | — |
| Recommendation (D2) | propose | review | review | i |
| Award an RFQ | prepare | — | route | ✅ **approve** |
| Agree a price / negotiation result | prepare | — | route | ✅ **approve** |
| Single / sole-source designation | flag | — | route | ✅ **approve** |
| Post a PR/PO in SAP | prepare | — | route | ✅ **approve** |
| Sign an NDA / contract / term | draft | — | route | ✅ **approve** |
| Committed development / tooling spend | propose | — | route | ✅ **approve** |
| Disqualify a critical/sole supplier | propose | — | route | ✅ **approve** |
| Engineering change cut-in | propose | — | route | ✅ **approve** |
| Premium freight / expedite spend | propose | — | route | ✅ **approve** |
| Constitutional / structural change | — | — | propose | ✅ **approve** |

✅ = approves · propose/prepare/draft = AI may do · route/review = coordinate · i = informed

## Decision Rule
- If a row's Human Owner column is ✅, **no AI may approve it** — prepare and escalate.
- When unsure whether something binds KRDA → **treat as a commitment and escalate (L3)**.

## Links
- Governance: [decision-framework.md](../company/decision-framework.md), [escalation-rules.md](../company/organization/escalation-rules.md)
- Every workflow's "Approval Gates" section resolves here.
