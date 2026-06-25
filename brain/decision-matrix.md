---
id: framework-decision-matrix
title: Decision Matrix
type: framework
used_by: [all frameworks, Chief of Staff]
status: active
updated: 2026-06-25
---

# Decision Matrix

> The generic weighted multi-criteria decision tool every other framework builds on.

## Purpose
Provide one consistent, transparent method for choosing among options — so all
decisions are scored the same way and are auditable.

## When to Use
Any multi-option decision: supplier choice, lever choice, award, make/buy, etc.
Domain frameworks supply the criteria & weights; this supplies the math & rules.

## Method

1. **Frame** — state the decision, options, and decision class (D0–D4).
2. **Criteria & weights** — list criteria; assign weights summing to 100%.
   **Fix weights before scoring** (and before seeing prices).
3. **Gates** — define must-pass gates (e.g. technical conformance, qualification).
4. **Score** — rate each option per criterion (e.g. 1–5), with a source for each.
5. **Compute** — weighted score = Σ(weight × score); apply gates (fail = excluded).
6. **Sensitivity** — would a reasonable weight change flip the result? Note it.
7. **Recommend** — highest eligible score; record rationale, dissent, and TBDs.

## Scoring Template

| Criterion | Weight | Opt A | Opt B | Opt C |
|-----------|:---:|:---:|:---:|:---:|
| ... | % | | | |
| **Gate (pass/fail)** | — | | | |
| **Weighted total** | 100% | | | |

## Rules
- No unsourced scores; unknown → `TBD`, not a guess.
- A single criterion never silently dominates (that is what weights are for).
- The Chief of Staff uses this to balance department inputs without letting one
  employee dominate ([chief-of-staff §6](../company/chief-of-staff.md)).

## Escalation / Commitment Gate
- The *decision method* is D0; the *resulting commitment* follows the
  [approval-matrix](approval-matrix.md).

## Links
- Used by: every domain framework in [/brain](README.md)
- Doctrine: [chief-of-staff.md](../company/chief-of-staff.md)
