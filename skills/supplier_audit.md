---
id: skill-supplier-audit
title: Supplier Audit (Assessment)
type: skill
owner: Supplier Development (SM)
used_by: [supplier_audit.md]
uses: [../templates/audit-report.md, ../knowledge/quality/]
status: active
updated: 2026-06-25
---

# Supplier Audit (Assessment)

> Conduct a structured assessment of a supplier against a quality/capability
> checklist and record evidence-based findings.

> **Skill vs workflow:** this skill is the *assessment method*. The end-to-end
> process (planning, status decision, escalation) is the workflow
> [supplier_audit.md](../workflows/supplier_audit.md). This skill fills its
> assessment step.

## Purpose
Produce objective, severity-rated findings and CAPA inputs — the factual core of
a qualification decision.

## When to Use
Inside the workflow [supplier_audit.md](../workflows/supplier_audit.md)
(assessment step).

## Inputs

| Input | Source |
|-------|--------|
| Audit checklist & standards | `../knowledge/quality/` *(TBD)* |
| Supplier record & history | `/suppliers/<supplier>/` |
| Technical capability input | Technical Purchasing (SE) |

## Method

1. **Set scope** — capability / quality system / process / re-qualification.
2. **Assess against checklist** — each item: conform / nonconform, with evidence.
3. **Rate findings** — major / minor / observation.
4. **Draft CAPA inputs** — for each nonconformity: action, owner, due.
5. **Record** in `../templates/audit-report.md`; only verified findings.

## Output

| Output | Destination / Template |
|--------|------------------------|
| Audit report | `../templates/audit-report.md` → `/suppliers/<supplier>/audits/<date>.md` |

## Quality Bar
- [ ] Every finding backed by evidence.
- [ ] Severity rated consistently.
- [ ] CAPA owner + due date for each nonconformity.

## Common Errors
- ❌ Recording findings not actually verified.
- ❌ Closing a finding without evidence.
- ❌ Mixing the assessment with the qualification *decision* (that's the workflow).

## Limitations / Guardrails
- Produces findings; the qualification status decision and disqualification
  escalation belong to the workflow + Human Owner.

## Links
- Workflow: [supplier_audit.md](../workflows/supplier_audit.md)
- Template: [audit-report.md](../templates/audit-report.md)
- Knowledge: `../knowledge/quality/`
