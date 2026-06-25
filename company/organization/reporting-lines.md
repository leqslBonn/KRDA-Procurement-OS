---
id: reporting-lines
title: Reporting Lines
owner: Procurement Lead
status: active
updated: 2026-06-25
---

# Reporting Lines

The **canonical** reporting structure, accountability (RACI), and hand-off map for
the AI organization. The [Organization Chart](../org-chart.md) shows authority at a
glance; this document is the authoritative detail.

> สายบังคับบัญชา + RACI + แผนที่การส่งต่องาน ฉบับ canonical

---

## 1. Reporting Chain

```
Member role ──► Department Head ──► Procurement Lead ──► Human Owner
```

- A **member role** reports to its **Department Head** for coordination, while
  keeping ownership of its own charter and records.
- A **Department Head** reports to the **Procurement Lead**.
- The **Procurement Lead** reports to the **Human Owner**.
- A single-role department's head *is* that role; it reports directly to the Lead.

## 2. Reporting Table

| Role | Department | Reports to | Is head of |
|------|-----------|-----------|------------|
| Procurement Lead | OPL | Human Owner | OPL (organization) |
| Strategic Sourcing | SE | Procurement Lead | SE |
| Technical Purchasing | SE | Strategic Sourcing (SE head) | — |
| Supplier Development | SM | Procurement Lead | SM |
| RFQ Management | CC | Procurement Lead | CC |
| Cost Reduction | CC | RFQ Management (CC head) | — |
| SAP Purchasing | TS | Procurement Lead | TS |
| Procurement Automation | TS | SAP Purchasing (TS head) | — |
| Procurement Analytics | IP | Procurement Lead | IP |

## 3. Accountability (RACI) by Decision Class

Aligned to the [Decision Framework](../decision-framework.md) classes D0–D4.
R = Responsible · A = Accountable · C = Consulted · I = Informed

| Decision | Member role | Dept Head | Procurement Lead | Human Owner |
|----------|:----:|:----:|:----:|:----:|
| D0 Operational (in-charter) | R/A | I | — | — |
| D1 Coordination / routing | C | C | R/A | I |
| D2 Recommendation | R | A | C | I |
| D3 Commitment | R (prepares) | C | C | **A** |
| D4 Constitutional change | — | — | C | **A** |

Department Heads add an accountability layer for D2 recommendations leaving their
department; they do **not** gain any D3 commitment authority.

## 4. Hand-off Map (who passes work to whom)

| From | Typical hand-off | To |
|------|------------------|----|
| Procurement Lead | Routes intake | The owning department |
| Technical Purchasing (SE) | Validated spec ready to quote | RFQ Management (CC) |
| Technical Purchasing (SE) | Supplier can't meet spec | Supplier Development (SM) |
| Strategic Sourcing (SE) | Shortlist ready to quote | RFQ Management (CC) |
| Strategic Sourcing (SE) | Strategic supplier needs uplift | Supplier Development (SM) |
| Cost Reduction (CC) | Target ready to negotiate | RFQ Management (CC) |
| Cost Reduction (CC) | Idea needs spec change | Technical Purchasing (SE) |
| RFQ Management (CC) | Award approved | SAP Purchasing (TS) |
| RFQ Management (CC) | Terms need agreement | Human Owner via OPL → `/contracts` |
| SAP Purchasing (TS) | Transaction posted | Procurement Analytics (IP) |
| Supplier Development (SM) | Performance to analyze | Procurement Analytics (IP) |
| Procurement Analytics (IP) | Savings opportunity | Cost Reduction (CC) |
| Procurement Analytics (IP) | Supply risk | Strategic Sourcing (SE) |
| Procurement Automation (TS) | Workflow ready | Owning department |

## 5. Hand-off Rules

1. **Within a department:** members coordinate directly; the head is informed.
2. **Across departments:** hand off directly per the map above; the Procurement
   Lead is **informed**, and **decides** only if scope is unclear or disputed.
3. **To the Human Owner:** only via the Procurement Lead (OPL), and only for
   D3/D4 (see [escalation-rules.md](escalation-rules.md)).
4. Every hand-off is a **record**, using the message format in
   [communication-rules.md](communication-rules.md) — never a lost conversation.

## 6. Coverage Check

Every role belongs to exactly one department. Every department has exactly one
head. No responsibility is shared across departments. If a new need has no clear
owner, the Procurement Lead assigns it or proposes a new role/department to the
Human Owner.
