---
id: skill-technical-review
title: Technical Review
type: skill
owner: Technical Purchasing (SE)
used_by: [rfq.md, engineering_change.md]
uses: [../templates/spec-sheet.md, ../knowledge/standards/]
status: active
updated: 2026-06-25
---

# Technical Review

> Verify that a supplier offer, sample, or change meets the controlled spec and
> acceptance criteria.

## Purpose
Protect technical correctness — confirm fit/function/material/tolerance before a
buy or a change proceeds.

## When to Use
Inside [rfq.md](../workflows/rfq.md) (tech-check of quotes) and
[engineering_change.md](../workflows/engineering_change.md) (technical impact).

## Inputs

| Input | Source |
|-------|--------|
| Controlled spec & acceptance criteria | `../templates/spec-sheet.md` → project copy |
| Supplier offer / sample / first article | `/rfq`, `/suppliers`, `/projects` |
| Applicable standards | `../knowledge/standards/` *(TBD)* |

## Method

1. **Restate requirements** — key characteristics, tolerances, materials, criticals.
2. **Check the offer** item-by-item against each acceptance criterion.
3. **Classify** — conform / nonconform / needs-data (`TBD`).
4. **Assess criticality** — does any gap affect fit, function, or safety?
5. **Verdict** — pass / conditional / fail, with evidence and required actions.

## Output

| Output | Destination / Template |
|--------|------------------------|
| Technical review verdict | `/projects/<id>/` (acceptance vs spec-sheet) |

## Quality Bar
- [ ] Every acceptance criterion checked.
- [ ] Unverified items marked `TBD`, never assumed.
- [ ] Critical characteristics flagged.

## Common Errors
- ❌ Passing on price/lead-time pressure despite a spec gap.
- ❌ Assuming a tolerance/material not stated.
- ❌ Reviewing against an uncontrolled/old spec.

## Limitations / Guardrails
- Cannot accept a deviation from a controlled spec — that needs engineering +
  Human Owner (via engineering_change).

## Links
- Workflows: [rfq.md](../workflows/rfq.md), [engineering_change.md](../workflows/engineering_change.md)
- Template: [spec-sheet.md](../templates/spec-sheet.md)
- Knowledge: `../knowledge/standards/`
