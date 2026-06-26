---
id: TPL-SOW-REQUIREMENT
title: SOW / Requirement — Template
type: template
status: active
updated: 2026-06-26
---

# SOW / Requirement — <Project Name>

> Define the job **before** selecting a vendor. Vague scope = cost creep + weak
> acceptance. Everything the vendor must deliver, and how "done" is judged, lives here.

| Field | Value |
|-------|-------|
| Project | ... |
| Owner (KRDA) | ... (you — the controller) |
| Objective | the business/farm outcome wanted |
| Budget band | ... → maps to [approval-matrix](../brain/approval-matrix.md) |

## 1. Scope

**In scope**
- ...

**Out of scope** (state explicitly — this is your cost-creep shield)
- ...

## 2. Requirements

| # | Requirement | Must / Should | Acceptance measure |
|---|-------------|:-------------:|--------------------|
| R1 | ... | Must | how it's verified |

## 3. Deliverables

| # | Deliverable | Format | Includes |
|---|-------------|--------|----------|
| D1 | ... | working system / code / docs / data | ... |

> Always require: **source code + documentation + data export + admin handover**, not
> just "it works." Specify security requirements.

## 4. Milestones & Payment (pay on accepted delivery)

| # | Milestone | Deliverable | Acceptance criteria | % Payment |
|---|-----------|-------------|---------------------|:---------:|
| M1 | Design / spec sign-off | design doc | meets R1–Rn | 10–20% |
| M2 | Build / POC | working module | passes test cases | 20–30% |
| M3 | Integration | end-to-end working | integrated, data flows | 20–30% |
| M4 | UAT / go-live | accepted system | UAT passed, docs delivered | 20–30% |
| **Retention** | held to warranty end | — | final accept + warranty | **10–20%** |

## 5. Ownership & Continuity (state up front)
- **IP:** KRDA owns all custom deliverables & source.
- **Data:** KRDA owns all operational/farm data; export on demand.
- **Escrow:** source-code escrow / handover if vendor ceases.

## 6. Support & Warranty
- Warranty period (free defect fix): ...
- Support / SLA after go-live: ...

## 7. Constraints
- Timeline, standards, integration targets (existing systems/SAP), security/privacy.

## 8. Evaluation Basis
Vendors scored via [vendor-pitch-scorecard](vendor-pitch-scorecard.md) /
[startup-vendor-evaluation-framework](../brain/startup-vendor-evaluation-framework.md).

> This SOW becomes the contract's scope and the acceptance baseline
> ([acceptance-checklist](acceptance-checklist.md)).
