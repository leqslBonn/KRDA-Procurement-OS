---
id: framework-quality-escalation
title: Quality Escalation Framework
type: framework
used_by: [../agents/supplier-development.md, ../agents/technical-purchasing.md]
status: active
updated: 2026-06-25
---

# Quality Escalation Framework

> The logic for classifying a quality issue and escalating it to the right level.

## Purpose
Contain quality issues fast, protect the product, and drive corrective action — by severity.

## When to Use
On any incoming/field quality issue, nonconformity, or supplier escape.

## Decision Inputs

| Input | Source |
|-------|--------|
| Defect / nonconformity | Incoming QC, Production, field |
| Supplier & part | `/suppliers`, `/projects` |
| Spec & criticals | [technical-purchasing-framework](technical-purchasing-framework.md) |

## Framework (severity → response)

| Severity | Definition | Response |
|----------|------------|----------|
| Critical | Safety / function / line-down / field risk | Immediate containment + **L3 Human Owner** |
| Major | Spec nonconformity, sortable | Quarantine + CAPA + scorecard hit |
| Minor | Cosmetic / non-functional | Note + trend + CAPA if recurring |

## Decision Rule
- Classify by impact on **safety → function → fit → cosmetic**.
- Containment first (quarantine/stop), then disposition (use-as-is needs
  engineering sign-off), then CAPA.
- Repeat/major → supplier qualification status review
  ([supplier_audit](../workflows/supplier_audit.md)).

## Escalation / Commitment Gate
- Critical issues and any **use-as-is deviation** → **D3 → Human Owner** (+ engineering).
- Disqualifying a critical supplier → **D3**.

## Pitfalls
- ❌ Shipping/using nonconforming parts without disposition.
- ❌ Closing without root cause.
- ❌ Under-classifying a safety/critical issue.

## Links
- Workflow: [supplier_audit.md](../workflows/supplier_audit.md)
- Frameworks: [delivery-recovery-framework](delivery-recovery-framework.md), [supplier-risk-framework](supplier-risk-framework.md)
- Knowledge: `../knowledge/manufacturing/`, `../knowledge/supplier-management/`
