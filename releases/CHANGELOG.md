# Changelog — KRDA Procurement OS

All notable changes, newest first. Each version has a full note in `vX.Y.md`.
Format inspired by Keep a Changelog; versions are pre-1.0 (building the OS).

## [0.11.0] — 2026-06-26 — Knowledge, Training & Real Company Data

- Filled `company/overview.md` with real KRDA data: full legal name, headcount (200/7), Pathumthani address, ASEAN scope, approval matrix from official manual.
- Extracted `knowledge/procurement/procedure.md` (KB-PROC-001) from EN v1 (2021) + TH v2 (2023) official manuals — 13 sections incl. 3-stage vendor registration, competitor product policy.
- Retrained all 9 AI employees: 14 → 18 sections; mandatory brain framework links; KRDA-specific examples (agricultural machinery, Thai suppliers) + common mistakes + training materials.
- Authored 8 cost-engineering knowledge articles: KB-CE-001 (should-cost method) through KB-CE-008 (cost drivers).
- Authored `knowledge/taxonomy/kpi-definitions.md` (KB-TAX-001) — 10 KPIs with formulas, measurement windows, cadence.
- Authored `knowledge/taxonomy/spend-categories.md` (KB-TAX-002) — CMD taxonomy, 10 L1 / ~55 L2 codes.
- Updated `brain/approval-matrix.md` with real KRDA THB thresholds (3 authority tables from KB-PROC-001).
- Created `memory/current-context.md` (was referenced everywhere but missing).
- Commits: `be66953`, `9429ba8`.

## [0.10.0] — 2026-06-25 — Procurement Intelligence Platform (Phase 2)
- Added `/brain` (12 decision frameworks) — INTELLIGENCE layer.
- Added Workflow Engine standard (`workflows/ENGINE.md`).
- Restructured `/knowledge` into 14 searchable domains + taxonomy.
- Added `/simulation` (training engine, 5 seeds, plan to ≥100).
- Added Memory Engine + negotiation_history + lessons_learned registers.
- Added KPI system (`dashboard/kpis.md`, 10 KPIs).
- Added `/improvement` (weekly self-review → actions).
- Expanded employee template to 18 sections (frameworks mandatory).

## [0.9.0] — 2026-06-25 — Commands & Standard Templates
- Added `/commands` (7): new_supplier, new_rfq, costdown, prepare_negotiation, meeting, weekly_report, monthly_report.
- Standardized `/templates` to the 8-template standard set (+ supporting).
- INTERFACE layer wired into ARCHITECTURE.

## [0.8.0] — 2026-06-25 — Skills
- Added `/skills` (10): compare_quotation, cost_breakdown, supplier_scorecard, supplier_risk, supplier_audit, technical_review, drawing_review, rfq_summary, presentation, executive_report.
- Separated method (skill) from process (workflow) and format (template).

## [0.7.0] — 2026-06-25 — Memory System & Architecture
- Added 8 memory registers (index + native) and `memory/architecture.md` (auto-routing, dedup, retrieval).

## [0.6.0] — 2026-06-25 — Workflows (BPMN-like)
- Added 8 workflows with BPMN-like flow + 10 sections each; commitment gates to Human Owner.

## [0.5.0] — 2026-06-25 — Chief of Staff
- Added Chief of Staff operating doctrine (8-step task management, executive layer).

## [0.4.0] — 2026-06-25 — AI Employees
- Upgraded 9 agents to full 14-section employee definitions, each tagged to a department.

## [0.3.0] — 2026-06-25 — AI Organization
- Added `/company/organization`: departments (6), reporting-lines, escalation-rules, communication-rules.

## [0.2.0] — 2026-06-25 — Company Governance
- Added constitution, vision, mission, core-principles, decision-framework, org-chart, glossary.

## [0.1.0] — 2026-06-25 — Foundation & Structure
- Initialized repo: root README/CLAUDE/ARCHITECTURE; 13-folder skeleton; template & workflow frameworks.
