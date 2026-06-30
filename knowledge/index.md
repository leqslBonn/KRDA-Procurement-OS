---
id: knowledge-index
title: Knowledge Index
status: active
updated: 2026-06-25
---

# Knowledge Index

Master search index for the knowledge base. Add a row when you add an article.
14 domains + taxonomy; content is filled across versions (v0.10+).

## Domains & Status

| # | Domain | Folder | Owner employee | Articles |
|---|--------|--------|----------------|:--------:|
| 1 | Mechanical | `mechanical/` | Technical Purchasing | 0 |
| 2 | Electronics | `electronics/` | Technical Purchasing | 0 |
| 3 | Hydraulics | `hydraulics/` | Technical Purchasing | 0 |
| 4 | Manufacturing | `manufacturing/` | Tech Purchasing / Cost Reduction | 0 |
| 5 | Cost Engineering | `cost-engineering/` | Cost Reduction | 8 |
| 6 | Supplier Management | `supplier-management/` | Supplier Development | 1 |
| 7 | Strategic Sourcing | `strategic-sourcing/` | Strategic Sourcing | 0 |
| 8 | Negotiation | `negotiation/` | RFQ Mgmt / Cost Reduction | 1 |
| 9 | SAP | `sap/` | SAP Purchasing | 2 |
| 10 | Procurement | `procurement/` | all | 3 |
| 11 | AI Automation | `ai-automation/` | Procurement Automation | 0 |
| 12 | Power Automate | `power-automate/` | Procurement Automation | 0 |
| 13 | Excel | `excel/` | Analytics / Automation | 0 |
| 14 | Engineering Standards | `engineering-standards/` | Technical Purchasing | 0 |
| — | Taxonomy | `taxonomy/` | Procurement Analytics | 2 |

## Article Registry

> One row per article. 16 articles (v0.11–v0.12). Add a row when you author one.

| Article ID | Title | Domain | Source/date | Used by |
|-----------|-------|--------|-------------|---------|
| KB-PROC-001 | KRDA Procurement Procedure Manual | Procurement | Official manual v1 May 2021 | approval-matrix, workflows/rfq, workflows/price_negotiation |
| KB-TAX-001 | KPI Definitions | Taxonomy | KRDA v0.11 2026-06-26 | dashboard/kpis, all agents |
| KB-TAX-002 | Spend Category Taxonomy (CMD codes) | Taxonomy | KRDA v0.11 2026-06-26 | commodity_database, rfq records, cost_down records |
| KB-CE-001 | Should-Cost Method | Cost Engineering | KRDA v0.11 2026-06-26 | cost-down-framework, negotiation-framework |
| KB-CE-002 | Material Rates | Cost Engineering | KRDA v0.11 2026-06-26 | KB-CE-001 |
| KB-CE-003 | Process & Machine Rates | Cost Engineering | KRDA v0.11 2026-06-26 | KB-CE-001 |
| KB-CE-004 | Labor Rates (Thailand) | Cost Engineering | KRDA v0.11 2026-06-26 | KB-CE-001 |
| KB-CE-005 | Overhead, SGA & Profit | Cost Engineering | KRDA v0.11 2026-06-26 | KB-CE-001 |
| KB-CE-006 | Tooling & NRE Amortization | Cost Engineering | KRDA v0.11 2026-06-26 | KB-CE-001 |
| KB-CE-007 | Yield & Scrap Factors | Cost Engineering | KRDA v0.11 2026-06-26 | KB-CE-001, KB-CE-002 |
| KB-CE-008 | Cost Drivers | Cost Engineering | KRDA v0.11 2026-06-26 | KB-CE-001, cost-down-framework |
| KB-SAP-001 | SAP PR/PO Field Map (KRDA) | SAP | KRDA v0.12 2026-06-26 | workflows/sap, approval-matrix |
| KB-SAP-002 | KRDA SAP System Environment (ECC 6.0 EhP5) | SAP | KRDA 2026-06-30 (PE7) | workflows/sap, sap-purchasing agent, field-map |
| KB-SM-001 | Supplier Audit Checklist | Supplier Management | KRDA v0.12 2026-06-26 | workflows/supplier_audit, supplier-risk-framework |
| KB-PROC-002 | Software / SaaS TCO Method | Procurement | v0.12 2026-06-26 | startup-vendor-evaluation-framework, vendor scorecard |
| KB-PROC-003 | POC / Pilot Evaluation Method | Procurement | v0.12 2026-06-26 | startup-vendor-evaluation-framework |
| KB-NEG-001 | Owner-Side Negotiation Playbook (outsourced dev/IoT) | Negotiation | v0.12 2026-06-26 | negotiation-framework, vendor_project_control |

## Priority Articles

Done (v0.11):
- [x] `cost-engineering/` — KB-CE-001 through KB-CE-008 (8 articles)
- [x] `taxonomy/kpi-definitions.md` (KB-TAX-001), `taxonomy/spend-categories.md` (KB-TAX-002)
- [x] `procurement/procedure.md` (KB-PROC-001)

Next (v0.12+):
- [ ] Fill `TBD` rates in `cost-engineering/material-rates.md`, `process-rates.md`, `labor-rates.md`
- [ ] `supplier-management/audit-checklist.md`
- [ ] `sap/field-map.md`
- [ ] `quality`→`supplier-management/audit-checklist.md`
- [ ] `sap/field-map.md`
