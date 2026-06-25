# KRDA Procurement OS

**Version 0.10** · pre-1.0 (Phase 2 — Intelligence Platform) · [releases](releases/README.md) · [CHANGELOG](releases/CHANGELOG.md) · [roadmap](releases/ROADMAP.md)

**An AI-powered Procurement Operating System for KRDA.**

This repository is not a chatbot. It is a complete, file-based **AI procurement
department** — a team of specialized AI agents that work together through shared
knowledge, reusable workflows, and standard templates to run real procurement
operations.

> ระบบปฏิบัติการจัดซื้อด้วย AI สำหรับ KRDA — ไม่ใช่แชตบอต แต่เป็น "แผนกจัดซื้อ AI"
> ทั้งแผนกที่ทำงานร่วมกันผ่านความรู้กลาง, workflow ที่ใช้ซ้ำได้, และเทมเพลตมาตรฐาน

---

## Vision

Build an AI organization capable of assisting the full procurement value chain:

- Technical Purchasing
- Strategic Sourcing
- Supplier Development
- Cost Reduction
- RFQ Management
- SAP Purchasing
- Procurement Analytics
- Procurement Automation

The system is designed to **grow for years**. Every part is modular, every
workflow is reusable, every agent has a clear responsibility, and knowledge is
never duplicated.

---

## Operating Principles

1. **Modular** — every file does one thing and can be replaced independently.
2. **Reusable** — workflows and templates are written once and reused everywhere.
3. **Single source of truth** — facts live in exactly one place (`/knowledge`);
   everything else links to them. Never copy knowledge between files.
4. **Clear ownership** — every agent has a defined scope, inputs, and outputs.
5. **Maintainable** — plain Markdown, predictable structure, stable naming.
6. **Auditable** — work products and decisions are recorded as files, not chat.

---

## Repository Map

| Folder        | Purpose |
|---------------|---------|
| `/company`    | Who KRDA is — governance, org, profile, glossary. |
| `/agents`     | AI employees — the roles and their responsibilities. |
| `/brain`      | Reusable decision frameworks — how the org decides. |
| `/workflows`  | Reusable procedures (engine: `workflows/ENGINE.md`). |
| `/skills`     | Reusable analytical methods that workflow steps invoke. |
| `/simulation` | Training scenarios the AI company practices on. |
| `/improvement`| Weekly self-review and continuous improvement. |
| `/memory`     | How agents remember — state, conventions, continuity. |
| `/projects`   | Active and past procurement initiatives (one folder each). |
| `/templates`  | Standard document formats (RFQ, eval, cost-down, etc.). |
| `/suppliers`  | Supplier master data and qualification records. |
| `/rfq`        | RFQ working area and request tracking. |
| `/cost_down`  | Cost-reduction initiatives and savings tracking. |
| `/contracts`  | Contracts, terms, and agreement records. |
| `/knowledge`  | The single source of truth — methods, standards, references. |
| `/dashboard`  | Reporting and KPI views. |
| `/schedule`   | Recurring tasks and procurement calendar. |
| `/commands`   | Invocable entry-point actions (the org's front door). |
| `/releases`   | Versioned release notes (OS-style version history). |

See [ARCHITECTURE.md](ARCHITECTURE.md) for how these fit together, and
[CLAUDE.md](CLAUDE.md) for the rules every AI agent must follow in this repo.

---

## Status

🟢 **v0.10 — Intelligence Platform built.** On top of the v0.9 operating system:
the **Procurement Brain** (12 decision frameworks), the **Workflow Engine**, a
14-domain **Knowledge System**, the **Simulation Center**, the **Memory Engine**
(auto-archival), the **KPI System**, and **Continuous Improvement**. See
[releases](releases/README.md).

Pre-1.0: structurally complete and self-improving, but still runs on **no real data
yet** with `TBD` knowledge references.

## Path to v1.0 (see [ROADMAP](releases/ROADMAP.md))

- [ ] **v0.11** — Fill `/knowledge` (Cost Engineering first); retrain employees; train on simulations.
- [ ] **v0.12** — Onboard first real records; dashboards show real KPI values.
- [ ] **v0.13** — Automate intake & memory archival; simulation set to 100.
- [ ] **v1.0** — No `TBD` in core paths; proven end-to-end on real cases.
