---
id: risk-database
title: Risk Database (Risk Register)
type: register-native
status: active
updated: 2026-06-25
---

# Risk Database (Risk Register)

> The organization's cross-cutting risk register. **Memory-native: this is the
> source of truth for procurement risks** (supply, single-source, quality,
> compliance, financial), linking to the records they affect.

## What This Is
A living register where any employee logs a risk, and the Chief of Staff / owning
department tracks mitigation. It does not duplicate supplier or contract facts —
it **references** them and adds risk assessment on top.

## Schema (highest severity on top)

| Risk ID | Type | Description | Affected | Likelihood | Impact | Severity | Owner | Mitigation | Status | Escalated |
|---------|------|-------------|----------|------------|--------|----------|-------|------------|--------|-----------|
| _RSK-2026-001_ | _single-source_ | _example_ | _supplier/part link_ | _L/M/H_ | _L/M/H_ | _score_ | _Strat Sourcing_ | _TBD_ | _open_ | _L3?_ |

> No risks logged yet.

## Conventions
- `Type`: supply / single-source / quality / compliance / financial / continuity.
- `Severity` = Likelihood × Impact; sort highest first.
- `Affected` links to the canonical record (`/suppliers`, `/projects`, `/contracts`).
- `Owner` is the responsible employee/department.
- Material risks are **escalated to the Human Owner (L3)** and noted in
  [meeting_history.md](meeting_history.md).
- Append-only history; close by setting `Status: closed`, never delete.

## Links
- Single-source designations: [supplier_database.md](supplier_database.md), [`supplier_selection.md`](../workflows/supplier_selection.md)
- Escalation: [`escalation-rules`](../company/organization/escalation-rules.md)
- Decisions: [meeting_history.md](meeting_history.md)
