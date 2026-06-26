---
id: roadmap
title: Roadmap v0.2 → v1.0
status: active
updated: 2026-06-25
---

# Roadmap — v0.2 → v1.0

The path from the document foundation to a production-ready AI Procurement OS.
v0.1–v0.10 are released; v0.11→v1.0 are the forward milestones with exit criteria.

## Released

| Version | Theme | Exit criteria met |
|---------|-------|-------------------|
| v0.1–v0.9 | Foundation → governance → employees → workflows → memory → skills → commands → templates | ✅ (see CHANGELOG) |
| **v0.10** | **Intelligence Platform** (brain, knowledge system, engine, simulation, memory engine, KPI, improvement) | ✅ structure complete |

## Forward Milestones

### v0.11 — Knowledge & Training ✅ (2026-06-26)
**Goal:** make the brain literate and the employees trained.
- [x] Author `/knowledge/cost-engineering/*` — 8 articles KB-CE-001–008.
- [x] Author `taxonomy/kpi-definitions.md` + `spend-categories.md` — KB-TAX-001, KB-TAX-002.
- [x] Retrain all 9 employees to 18-section schema (B4 done).
- [x] Fill `company/overview.md` with real KRDA data (brought forward from v0.12).
- [x] Extract `knowledge/procurement/procedure.md` from official manuals (KB-PROC-001).
- [x] Update `brain/approval-matrix.md` with real KRDA THB thresholds.
- [x] Create `memory/current-context.md` (was missing).
- [ ] Grow simulation to ~40 scenarios — **in progress** (at 15 → target 40).
- **Exit criteria met** — cost-down & RFQ runnable with real knowledge; KPIs defined.

### v0.12 — First Real Data (target: 2026-07)
**Goal:** operate on real KRDA work.
- [ ] Onboard first real supplier(s) into `/suppliers/`.
- [ ] Run first real RFQ end-to-end (command → workflow → record → register).
- [ ] Record first real cost-down case.
- [ ] Dashboards show real, sourced KPI values (at least 3 KPIs with real data).
- **Exit:** one full `command → workflow → skill → record → register` cycle on real data.

### v0.13 — Automation
**Goal:** remove manual toil.
- [ ] Author `/knowledge/power-automate/*` + `/ai-automation/*`.
- [ ] Automate Memory Engine register updates (backlog B5).
- [ ] Quote intake / RFQ reminders automated.
- [ ] Simulation set reaches **100**; continuous training loop running.
- **Exit:** Automation Coverage KPI meaningful; archival is automatic.

### v1.0 — Production-Ready
**Goal:** the org runs KRDA Technical Purchasing daily.
- [ ] No `TBD` in core paths (all referenced knowledge authored).
- [ ] Real records across all registers; memory proven single-source.
- [ ] KPIs tracked weekly/monthly; improvement loop demonstrably closing gaps.
- [ ] End-to-end proven on multiple real cases.
- **Exit:** stable, documented, automated, self-improving — **v1.0 cut**.

## Operating Cadence (always on from v0.10)
- Every completion → Memory Engine archives + a lesson.
- Every week → `/improvement` review → action plan (system before content).
- Every release → release note (this template) + CHANGELOG + VERSION bump.

## Principle
Improve the system before adding content. Refactor on architectural weakness.
Never duplicate knowledge. Build for the long term.
