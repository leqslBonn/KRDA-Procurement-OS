# /releases

KRDA Procurement OS is versioned like a real operating system. Every version ships
a **Release Note** documenting its state across six dimensions:

**Release Note · Folder Structure · Agents · Workflows · Memory · Commands.**

> ระบบมีเวอร์ชันเหมือน OS จริง — ทุกเวอร์ชันมี Release Note + สถานะครบ 6 ด้าน

## Current Version

**v0.10** — see [VERSION](../VERSION). Status: pre-1.0 (Phase 2 — Intelligence Platform).
Full forward plan: [ROADMAP.md](ROADMAP.md).

## Versioning Policy

- **v0.x** — building the OS: structure, governance, employees, processes, memory.
  Architecture may still evolve. No real production data yet.
- **v1.0** — first **production-ready** release: knowledge base populated (no `TBD`
  in core paths), first real operational data, dashboards/automation live.
- After v1.0: `vMAJOR.MINOR` — MINOR adds capability; MAJOR changes the architecture.

Each release is **cumulative**: the live folders are the current snapshot; a release
note records the **delta** under the six dimensions.

## Roadmap

| Version | Theme | Status |
|---------|-------|--------|
| [v0.1](v0.1.md) | Foundation & structure | ✅ released |
| [v0.2](v0.2.md) | Company governance | ✅ released |
| [v0.3](v0.3.md) | AI organization (departments) | ✅ released |
| [v0.4](v0.4.md) | AI employees (9) | ✅ released |
| [v0.5](v0.5.md) | Chief of Staff | ✅ released |
| [v0.6](v0.6.md) | Workflows (BPMN-like) | ✅ released |
| [v0.7](v0.7.md) | Memory system & architecture | ✅ released |
| [v0.8](v0.8.md) | Skills | ✅ released |
| [v0.9](v0.9.md) | Commands & standard templates | ✅ released |
| [v0.10](v0.10.md) | Intelligence Platform (Phase 2) | ✅ released (current) |
| v0.11 | Knowledge & training (Cost Engineering, retrain) | 🔜 next |
| v0.12 | First real operational data | ⏳ planned |
| v0.13 | Automation; simulation to 100 | ⏳ planned |
| [v1.0](v1.0.md) | Production-ready release | 🎯 target |

Detailed milestones & exit criteria: [ROADMAP.md](ROADMAP.md).

## Files

| File | Purpose |
|------|---------|
| [CHANGELOG.md](CHANGELOG.md) | One-line history of every version. |
| [_TEMPLATE.md](_TEMPLATE.md) | Release-note template (the six dimensions). |
| `v*.md` | Per-version release notes. |

## How to Cut a Release

1. Finish the version's work in the live folders.
2. Copy [_TEMPLATE.md](_TEMPLATE.md) → `vX.Y.md`; fill the six dimensions (delta).
3. Add a line to [CHANGELOG.md](CHANGELOG.md); bump [../VERSION](../VERSION).
4. Update the roadmap row above.
