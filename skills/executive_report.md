---
id: skill-executive-report
title: Executive Report
type: skill
owner: Chief of Staff / Procurement Analytics (IP)
used_by: [every managed task]
uses: [../company/chief-of-staff.md, ../dashboard/]
status: active
updated: 2026-06-25
---

# Executive Report

> Assemble the single, evidence-based **Executive Recommendation** the Chief of
> Staff delivers to the Human Owner.

## Purpose
Synthesize all department inputs into one decision-ready document — balanced, no
single employee dominating, every claim sourced.

## When to Use
Step 8 of the Chief of Staff [operating doctrine](../company/chief-of-staff.md) —
the close of every managed task.

> **Format is canonical** in
> [chief-of-staff.md §7](../company/chief-of-staff.md). This skill is *how to fill
> it well*; it does not restate the format.

## Inputs

| Input | Source |
|-------|--------|
| Department responses | each employee's hand-off |
| Supporting records | `/rfq`, `/cost_down`, `/suppliers`, `/projects` |
| Conflicts & risks | [risk_database](../memory/risk_database.md), task notes |

## Method

1. **Restate objective** — goal, scope, decision class.
2. **Gather inputs from all six departments** — mark each Lead / Contribute / N/A.
3. **Weigh, don't average** — balance inputs by relevance; record dissent.
4. **Resolve conflicts** — surface disagreements and how each was settled.
5. **Build evidence basis** — every key fact with a source link; gaps as `TBD`.
6. **State one recommendation** + the exact decision required (D3/D4 or informational).
7. **Log** the decision in [meeting_history.md](../memory/meeting_history.md).

## Output

| Output | Destination / Template |
|--------|------------------------|
| Executive Recommendation | format: [chief-of-staff.md §7](../company/chief-of-staff.md) → `/projects/<id>/` |

## Quality Bar
- [ ] All six departments covered (explicit verdict each — none skipped).
- [ ] No single employee's view adopted verbatim.
- [ ] Every claim sourced; unknowns `TBD`.
- [ ] One recommendation; commitment routed to Human Owner.

## Common Errors
- ❌ Skipping a department's input.
- ❌ Letting one loud employee dominate.
- ❌ Unsourced assertions or hidden conflicts.
- ❌ Recommending a commitment as if already approved.

## Limitations / Guardrails
- Proposes only; the Human Owner decides every commitment (D3/D4).

## Links
- Doctrine & format: [chief-of-staff.md](../company/chief-of-staff.md)
- Decision log: [meeting_history.md](../memory/meeting_history.md)
- Deck form: [presentation.md](presentation.md)
