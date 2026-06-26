# /workflows

Reusable, step-by-step procedures the agents follow. A workflow is written
**once** and reused across many cases — never copied per project.

> ขั้นตอนการทำงานที่ใช้ซ้ำได้ — เขียนครั้งเดียว ใช้ได้ทุกงาน ห้าม copy ต่อโปรเจกต์

## Status

🟢 **Core workflows active.** Eight reusable procedures are in place. Each is owned
by one employee/department, names the responsible role per step, and routes every
commitment through the Human Owner gate (D3/D4).

## What a Workflow Is

- A **BPMN-like** process: start event → tasks (by role) → XOR gateways →
  end event, with escalation events and calls to other workflows.
- Owned by one employee/department; may call templates and knowledge.
- Deterministic enough to reuse and audit; never copied per project.

## Workflow Format — flow + 10 sections

Every workflow file contains a **Flow (BPMN-like)** diagram plus, in order:
**1** Purpose · **2** Inputs · **3** Required AI Employees · **4** Decision Gates ·
**5** Outputs · **6** Escalation Rules · **7** KPI · **8** Checklist ·
**9** Common Mistakes · **10** Automation Opportunities.

## BPMN Notation

Canonical legend used by every workflow's **Flow** section:

| Symbol | Meaning |
|--------|---------|
| `●` | Start event (trigger) |
| `◉` | End event (outcome) |
| `[task — Role]` | Task / activity, performed by the named employee |
| `◇Gn` | Exclusive (XOR) gateway — a labeled decision; branches in §4 |
| `├─ yes/no ─►` | Conditional sequence flow out of a gateway |
| `∥` | Parallel tasks (run concurrently) |
| `⚑` | Escalation event (to L1/L2/L3 — see escalation-rules) |
| `⇒ name.md` | Calls / hands off to another workflow |

## Conventions

- One workflow per file. Use the [_TEMPLATE.md](_TEMPLATE.md) structure.
- Reference knowledge/templates by link — do not inline duplicate them.
- Each gateway in the Flow has a matching row in **§4 Decision Gates**.
- Every commitment branch escalates to the Human Owner (D3/D4).

## Active Workflows

| Workflow | Owner (dept) | Purpose |
|----------|--------------|---------|
| [rfq.md](rfq.md) | RFQ Management (CC) | RFQ-to-award: quote, compare, award. |
| [cost_down.md](cost_down.md) | Cost Reduction (CC) | Should-cost → validated, realized saving. |
| [supplier_selection.md](supplier_selection.md) | Strategic Sourcing (SE) | Need → risk-aware shortlist. |
| [supplier_audit.md](supplier_audit.md) | Supplier Development (SM) | Audit & qualification. |
| [price_negotiation.md](price_negotiation.md) | RFQ Management (CC) | Evidence-based negotiation to target. |
| [nda.md](nda.md) | Procurement Lead (OPL) | Confidentiality before sharing info. |
| [sap.md](sap.md) | SAP Purchasing (TS) | PR/PO prep & authorized posting. |
| [engineering_change.md](engineering_change.md) | Technical Purchasing (SE) | ECN purchasing impact & cut-in. |
| [vendor_project_control.md](vendor_project_control.md) | Procurement Lead + Tech Purchasing | Owner-side control of outsourced dev/IoT (SOW→select→contract→accept→pay). |

## How They Connect (orientation)

```
supplier_selection ──► rfq ──► price_negotiation ──► [Human Owner approves] ──► sap
       │                │                                   ▲
       ▼                ▼                                   │
  supplier_audit     nda (before sharing info)         cost_down
       │                                                    ▲
       └────────────────────► engineering_change ──────────┘
```

> Every commitment (award, price, posting, NDA, cut-in) is **D3 → Human Owner**.
> Workflows prepare and recommend; humans authorize.
