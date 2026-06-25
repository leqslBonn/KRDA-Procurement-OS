---
id: skill-presentation
title: Presentation
type: skill
owner: Procurement Analytics (IP)
used_by: [reviews, reporting]
uses: [../dashboard/, ../knowledge/taxonomy/]
status: active
updated: 2026-06-25
---

# Presentation

> Turn procurement analysis into a clear, decision-oriented slide deck for reviews
> and stakeholder updates.

## Purpose
Communicate findings and recommendations visually — sourcing reviews, savings
updates, supplier performance, category strategy — so decisions are easy.

## When to Use
Periodic reviews, category/savings updates, or when a managed task's
[executive_report](executive_report.md) needs a deck form.

## Inputs

| Input | Source |
|-------|--------|
| Analysis / KPI data | `../dashboard/`, `/projects` |
| Source records | `/rfq`, `/cost_down`, `/suppliers` |

## Method

1. **Define the audience & decision** — what they must decide/know.
2. **Storyline** — situation → analysis → options → recommendation.
3. **One message per slide**; lead with the takeaway.
4. **Evidence** — every chart/number links to a source record.
5. **Close** — explicit recommendation + decision required (D-class).
6. **Produce** the deck (may use the host `pptx` skill as the file tool).

## Output

| Output | Destination / Template |
|--------|------------------------|
| Slide deck | `../dashboard/reports/` (or project folder) |

## Quality Bar
- [ ] Every figure sourced; no unsourced numbers.
- [ ] One clear message per slide.
- [ ] Ends with a concrete recommendation + decision required.

## Common Errors
- ❌ Data dump with no storyline or recommendation.
- ❌ Unsourced or inconsistent figures across slides.
- ❌ Burying the ask.

## Limitations / Guardrails
- Communicates; does not decide. Commitments shown are proposals (D3 → Human Owner).
- Confidential prices/terms only to the authorized audience.

## Links
- Source: [`/dashboard`](../dashboard/README.md)
- Pairs with: [executive_report.md](executive_report.md)
- Production tool: host `pptx` skill (automation detail)
