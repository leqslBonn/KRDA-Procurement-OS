# /skills

Reusable **analytical capabilities** the AI employees apply — the "how to do X
well" methods that workflow steps invoke. A skill is narrower than a workflow and
richer than a template.

> ทักษะวิเคราะห์ที่ใช้ซ้ำได้ — "วิธีทำ X ให้ดี" ที่ step ใน workflow เรียกใช้

## Skill vs Workflow vs Template

| | What it is | Example |
|--|-----------|---------|
| **Workflow** (`/workflows`) | End-to-end process: many steps, many employees, gateways, escalation | `rfq.md` |
| **Skill** (`/skills`) | One reusable method an employee performs inside a step | `compare_quotation.md` |
| **Template** (`/templates`) | Blank document format the skill fills | `bid-tab.md` |

Flow: **workflow step → invokes a skill → outputs via a template.** Skills hold the
*know-how*; they do not duplicate process (workflows) or format (templates).

## Catalog

| Skill | Owner (dept) | Invoked by | Fills template |
|-------|--------------|-----------|----------------|
| [compare_quotation.md](compare_quotation.md) | RFQ Mgmt (CC) | rfq, price_negotiation | bid-tab |
| [cost_breakdown.md](cost_breakdown.md) | Cost Reduction (CC) | cost_down, price_negotiation | should-cost |
| [supplier_scorecard.md](supplier_scorecard.md) | Supplier Dev (SM) | supplier_audit, scheduled | supplier-scorecard |
| [supplier_risk.md](supplier_risk.md) | Strat Sourcing (SE) | supplier_selection | (risk_database) |
| [supplier_audit.md](supplier_audit.md) | Supplier Dev (SM) | supplier_audit (wf) | audit-report |
| [technical_review.md](technical_review.md) | Tech Purchasing (SE) | rfq, engineering_change | spec-sheet |
| [drawing_review.md](drawing_review.md) | Tech Purchasing (SE) | engineering_change, qualification | spec-sheet |
| [rfq_summary.md](rfq_summary.md) | RFQ Mgmt (CC) | rfq | (digest) |
| [presentation.md](presentation.md) | Analytics (IP) | reviews, reporting | (deck) |
| [executive_report.md](executive_report.md) | Chief of Staff / IP | every managed task | (exec recommendation) |

## Conventions

- One skill per file; use [_TEMPLATE.md](_TEMPLATE.md).
- A skill names its **method** (the actual technique), its inputs, and its output.
- Reference templates and knowledge by link — never restate them.
- Where a skill produces a file (deck, report), it may use the host `pptx` / `docx`
  skills as the production tool (an automation detail, not a method change).
