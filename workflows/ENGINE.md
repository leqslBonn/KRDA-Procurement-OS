---
id: workflow-engine
title: Workflow Engine — The Standard Pipeline
type: workflow-standard
owner: Chief of Staff
status: active
updated: 2026-06-25
---

# Workflow Engine — The Standard Pipeline

> Every incoming request runs through **one** standard pipeline. Domain workflows
> (`rfq`, `cost_down`, …) are specializations that plug into these stages.

This is the operating loop of the organization. It unifies the
[Chief of Staff doctrine](../company/chief-of-staff.md), the [brain frameworks](../brain/README.md),
the department reviews, and the [memory engine](../memory/architecture.md).

## The Pipeline

```
①  Incoming Request
        ↓
②  Classification            [Chief of Staff]  → decision class D0–D4
        ↓
③  Task Breakdown            [Chief of Staff]  → smallest sub-tasks
        ↓
④  Assign AI Employees       [Chief of Staff]  → coverage matrix, none skipped
        ↓
⑤  Technical Review          [SE: Tech Purchasing]  → technical-purchasing-framework
        ↓
⑥  Business Review           [SE/CC: Strat Sourcing, RFQ]  → sourcing/rfq-evaluation
        ↓
⑦  Risk Review               [SM/SE]  → supplier-risk-framework
        ↓
⑧  Cost Review               [CC: Cost Reduction]  → cost-down / cost_breakdown
        ↓
⑨  Conflict Detection        [Chief of Staff]  → surface, don't average
        ↓
⑩  Chief of Staff Review     [Chief of Staff]  → balance, decision-matrix
        ↓
⑪  Executive Recommendation  [Chief of Staff]  → executive-summary template
        ↓                                          → Human Owner (D3/D4 gate)
⑫  Archive Knowledge         [Memory Engine]  → registers + lessons-learned
```

## Stage Reference

| # | Stage | Owner | Framework / artifact |
|---|-------|-------|----------------------|
| 1 | Incoming Request | `/commands` or Human Owner | — |
| 2 | Classification | Chief of Staff | [decision-framework](../company/decision-framework.md) D0–D4 |
| 3 | Task Breakdown | Chief of Staff | doctrine §2 |
| 4 | Assign Employees | Chief of Staff | [coverage matrix](../company/chief-of-staff.md#4-department-coverage-matrix) |
| 5 | Technical Review | Technical Purchasing | [technical-purchasing-framework](../brain/technical-purchasing-framework.md) |
| 6 | Business Review | Strat Sourcing / RFQ Mgmt | [supplier-selection](../brain/supplier-selection-framework.md), [rfq-evaluation](../brain/rfq-evaluation-framework.md) |
| 7 | Risk Review | Supplier Dev / Strat Sourcing | [supplier-risk-framework](../brain/supplier-risk-framework.md) |
| 8 | Cost Review | Cost Reduction | [cost-down-framework](../brain/cost-down-framework.md) |
| 9 | Conflict Detection | Chief of Staff | doctrine §5 |
| 10 | Chief of Staff Review | Chief of Staff | [decision-matrix](../brain/decision-matrix.md) |
| 11 | Executive Recommendation | Chief of Staff | [executive-summary](../templates/executive-summary.md) → Human Owner |
| 12 | Archive Knowledge | Memory Engine | [memory architecture](../memory/architecture.md), lessons-learned |

## Rules

1. **No stage skipped.** A stage may return "N/A — reason," but is never silently omitted.
2. **No employee dominates.** Reviews (5–8) are independent inputs; the Chief of
   Staff balances them at stage 10 ([decision-matrix](../brain/decision-matrix.md)).
3. **Evidence-based.** Every review cites sources; unknowns are `TBD`.
4. **Commitment gate.** Stage 11 *proposes*; the Human Owner approves any D3/D4
   ([approval-matrix](../brain/approval-matrix.md)).
5. **Always archive.** Stage 12 updates memory so the next case starts smarter.

## How Domain Workflows Plug In

A domain workflow (e.g. [rfq.md](rfq.md)) implements stages 5–8 with its own steps
and gateways, then returns to stages 9–12 of the engine. Lightweight requests may
collapse stages but never bypass classification (2), the commitment gate (11), or
archival (12).
