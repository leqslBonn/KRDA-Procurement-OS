---
id: framework-technical-purchasing
title: Technical Purchasing Framework
type: framework
used_by: [../skills/technical_review.md, ../skills/drawing_review.md]
status: active
updated: 2026-06-25
---

# Technical Purchasing Framework

> The logic for deciding whether a part/offer is technically buyable and qualified.

## Purpose
Protect technical correctness — a consistent bar for accepting parts, samples, and changes.

## When to Use
Inside [technical_review](../skills/technical_review.md) and
[drawing_review](../skills/drawing_review.md).

## Decision Inputs

| Input | Source |
|-------|--------|
| Controlled spec / drawing | `../templates/spec-sheet.md` → project |
| Offer / sample / first article | `/rfq`, `/suppliers` |
| Standards | `../knowledge/engineering-standards/` |

## Framework (criteria & logic)

| Dimension | Pass condition |
|-----------|----------------|
| Dimensional / GD&T | Within tolerance on all key characteristics |
| Material | Spec material + verified (cert/test) |
| Process capability | Cpk adequate for criticals (where applicable) |
| Function / fit | Meets functional & assembly requirements |
| Criticals / safety | All critical characteristics conform |
| Documentation | First-article / PPAP-level evidence present |

## Decision Rule
- **Verdict = pass / conditional / fail.**
- Any **critical** characteristic failing → fail (no price/lead-time override).
- Unverified item → `TBD`, treated as not-yet-pass (never assumed conforming).

## Escalation / Commitment Gate
- Deviation from controlled spec → engineering + **Human Owner (D3)** via
  [engineering-change-framework](engineering-change-framework.md).

## Pitfalls
- ❌ Passing on commercial pressure despite a spec gap.
- ❌ Assuming a tolerance/material not stated.
- ❌ Reviewing an obsolete revision.

## Links
- Skills: [technical_review.md](../skills/technical_review.md), [drawing_review.md](../skills/drawing_review.md)
- Framework: [engineering-change-framework](engineering-change-framework.md)
- Knowledge: `../knowledge/mechanical/`, `../knowledge/engineering-standards/`
