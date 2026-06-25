# /commands

The **front door** of the organization. A command is a named action the Human
Owner (or an employee) invokes; the Chief of Staff receives it, applies the
[operating doctrine](../company/chief-of-staff.md), and dispatches the right
workflow, skills, and employees.

> ประตูหน้าขององค์กร — คำสั่งที่ Human Owner เรียก แล้ว Chief of Staff กระจายงานต่อ

## Command vs Workflow vs Skill

| | What it is |
|--|-----------|
| **Command** (`/commands`) | A trigger / entry point with arguments — the verb you invoke |
| **Workflow** (`/workflows`) | The end-to-end process the command runs |
| **Skill** (`/skills`) | A reusable method inside a workflow step |

A command is **thin**: it names what to start, captures arguments, assigns the
record/ID (per [memory architecture](../memory/architecture.md)), and hands off to
a workflow. It never restates the workflow.

## Catalog

| Command | Dispatches to | Creates (ID) |
|---------|---------------|--------------|
| [new_supplier.md](new_supplier.md) | supplier_audit (if needed) | `/suppliers/<slug>/` (`SUP-<slug>`) |
| [new_rfq.md](new_rfq.md) | supplier_selection → rfq | `/rfq/<id>/` (`RFQ-YYYY-NNN`) |
| [costdown.md](costdown.md) | cost_down | `/cost_down/<id>/` (`CD-YYYY-NNN`) |
| [prepare_negotiation.md](prepare_negotiation.md) | price_negotiation (prep) | brief in `/rfq` or `/cost_down` |
| [meeting.md](meeting.md) | — (logs decisions) | row in `meeting_history` |
| [weekly_report.md](weekly_report.md) | presentation / executive_report | `/dashboard/reports/` |
| [monthly_report.md](monthly_report.md) | presentation / executive_report | `/dashboard/reports/` |

## Conventions

- One command per file; use [_TEMPLATE.md](_TEMPLATE.md).
- A command states its invocation syntax, arguments, and the workflow it triggers.
- Memory routing follows [architecture.md](../memory/architecture.md): one canonical
  record, one index row, one stable ID — link, never copy.
- Every commitment the command leads to remains **D3 → Human Owner**.
