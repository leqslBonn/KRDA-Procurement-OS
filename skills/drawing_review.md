---
id: skill-drawing-review
title: Drawing Review
type: skill
owner: Technical Purchasing (SE)
used_by: [engineering_change.md, supplier_selection.md]
uses: [../templates/spec-sheet.md, ../knowledge/standards/]
status: active
updated: 2026-06-25
---

# Drawing Review

> Read an engineering drawing and extract the purchasing-relevant requirements:
> dimensions, tolerances, GD&T, material, finish, criticals, and change state.

## Purpose
Turn a drawing into a clear, buyable spec and catch ambiguities before they reach
a supplier.

## When to Use
At new-part intake, before issuing an RFQ, and inside
[engineering_change.md](../workflows/engineering_change.md) (assess what changed).

## Inputs

| Input | Source |
|-------|--------|
| Drawing + revision | Engineering / `/projects` |
| Drawing standards (GD&T, title block) | `../knowledge/standards/` *(TBD)* |
| Prior revision (for changes) | `/projects` |

## Method

1. **Identify** part no., revision, title-block data, scale, units.
2. **Extract** critical dimensions, tolerances, GD&T, datums.
3. **Capture** material, heat-treat, surface finish, coating.
4. **Mark criticals / key characteristics** (safety/function).
5. **Diff vs prior revision** (for changes) — what moved, added, removed.
6. **List ambiguities/gaps** as `TBD` questions back to engineering.
7. **Populate** the spec sheet acceptance criteria.

## Output

| Output | Destination / Template |
|--------|------------------------|
| Extracted spec / change list | `../templates/spec-sheet.md` → `/projects/<id>/` |

## Quality Bar
- [ ] Revision/title-block verified (right drawing, right rev).
- [ ] All criticals and tolerances captured.
- [ ] Ambiguities raised as `TBD`, not guessed.

## Common Errors
- ❌ Reviewing a superseded revision.
- ❌ Missing GD&T / datum implications on inspection.
- ❌ Silently interpreting an ambiguous callout.

## Limitations / Guardrails
- Reads and extracts; does not change the drawing — changes are engineering +
  Human Owner (engineering_change).

## Links
- Workflows: [engineering_change.md](../workflows/engineering_change.md), [supplier_selection.md](../workflows/supplier_selection.md)
- Template: [spec-sheet.md](../templates/spec-sheet.md)
- Knowledge: `../knowledge/standards/`
