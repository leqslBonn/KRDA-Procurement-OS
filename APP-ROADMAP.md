# KRDA Procurement Console — App Roadmap & Module Status

Single source of truth for the **app** (`console.html`). Built incrementally,
module by module ("on the job"). Status mirrored in the app's **📊 Modules** page.

> Status legend: 🟢 ready (usable on real work) · 🟡 beta (works, needs real data/polish)
> · 🟠 building (in progress) · ⚪ planned (not started)

**Updated:** 2026-06-30 · **App version:** 1.1

---

## Overall progress

Done-weighted across all planned modules. See the live bar in the app's Modules page.

`████████░░░░░░░░  ~45%` (9 of 16 modules at usable level; 4 new this build)

---

## Modules

| # | Module | Status | % | Real-use? | What's missing |
|---|--------|:------:|:--:|-----------|----------------|
| 1 | Vendor Evaluation | 🟢 ready | 100 | ✅ yes | — |
| 2 | TCO Calculator | 🟢 ready | 100 | ✅ yes | — |
| 3 | Acceptance (single) | 🟢 ready | 90 | ✅ yes | multi-milestone (→ #11) |
| 4 | Report / Print-PDF | 🟢 ready | 95 | ✅ yes | pull from more modules |
| 5 | SOW Builder | 🟡 beta | 80 | ✅ yes | save to history |
| 6 | Contract Terms Checklist | 🟡 beta | 80 | ✅ yes | export to report |
| 7 | Milestone Payment Tracker | 🟡 beta | 80 | ✅ yes | link to acceptance |
| 8 | Negotiation Prep | 🟡 beta | 75 | ✅ yes | save brief |
| 9 | Should-cost (metal) | 🟡 beta | 70 | ⚠️ rates EST | real KRDA rates |
| 10 | Case History | 🟡 beta | 60 | ⚠️ local only | save more record types |
| 11 | POC Planner | ⚪ planned | 0 | ❌ no | build form + success criteria |
| 12 | Supplier Database | ⚪ planned | 0 | ❌ no | CRUD + qualification status |
| 13 | RFQ / Quote Compare | ⚪ planned | 0 | ❌ no | normalize + bid-tab |
| 14 | Approval Router (THB→who signs) | ⚪ planned | 0 | ❌ no | KRDA approval bands |
| 15 | KPI Dashboard | ⚪ planned | 0 | ❌ no | needs real data |
| 16 | Risk Register | ⚪ planned | 0 | ❌ no | risk log + severity |

---

## How a module graduates ⚪ → 🟢

1. **⚪ planned** — listed, no UI.
2. **🟠 building** — UI exists, logic partial.
3. **🟡 beta** — works end-to-end; uses example/EST data; not yet validated on a real case.
4. **🟢 ready** — proven on at least one real KRDA case; data is real (no EST in core path).

Each module has a **QA check** (in the app) — what to verify before trusting it on real work.

---

## Build log

| Date | App ver | Change |
|------|---------|--------|
| 2026-06-30 | 1.1 | + Modules status page; + SOW Builder, Contract Checklist, Milestone Tracker, Negotiation Prep |
| 2026-06-30 | 1.0 | Vendor Eval, TCO, Should-cost, Acceptance, Report, History, Minutes, Manual; TH/EN; icon + desktop shortcut |

## Next up (priority order)
1. Approval Router (quick, high value — enter THB → who signs)
2. POC Planner
3. Supplier Database
4. RFQ / Quote Compare
