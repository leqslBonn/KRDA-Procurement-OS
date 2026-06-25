---
id: TPL-KPI-DASHBOARD
title: KPI Dashboard — Template
type: template
status: active
updated: 2026-06-25
---

# KPI Dashboard — <Period (YYYY-Www / YYYY-MM)>

> The standard reporting layout for `/dashboard`. KPI **definitions** are canonical
> in `/knowledge/taxonomy`; this form shows **values** (sourced, never invented).
> Filled via the [presentation](../skills/presentation.md) / [executive_report](../skills/executive_report.md) skills.

| Field | Value |
|-------|-------|
| Period | ... |
| Prepared by | Procurement Analytics (IP) |
| Data coverage (% spend) | ... |

## Core KPIs

| KPI | Definition ref | Target | Actual | Trend | Source |
|-----|----------------|--------|--------|-------|--------|
| Validated savings (THB / %) | `../knowledge/taxonomy/` | | | ↑/↓ | `/cost_down/savings-register.md` |
| RFQ cycle time | `../knowledge/taxonomy/` | | | | `rfq_database` |
| On-time delivery (OTD) % | `../knowledge/taxonomy/` | | | | `/suppliers` |
| Supplier quality (PPM) | `../knowledge/taxonomy/` | | | | `/suppliers` |
| Spend under management | `../knowledge/taxonomy/` | | | | `/dashboard` |
| Open high risks (≥6) | `../knowledge/taxonomy/` | | | | `risk_database` |

## Spend Snapshot

| By | Top items | Spend | Note |
|----|-----------|-------|------|
| Category | ... | ... | |
| Supplier | ... | ... | |

## Attention / Decisions Due
- ... (link to `meeting_history` items pending Human Owner)

## Notes
- Every value links to a source record. No unsourced numbers.
