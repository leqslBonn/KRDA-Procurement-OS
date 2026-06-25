# /simulation — Simulation Center

Realistic procurement cases the AI company trains on. Each scenario runs through the
[Workflow Engine](../workflows/ENGINE.md), applies the [brain frameworks](../brain/README.md),
and is scored against a gold-standard — then **lessons are archived to memory**.

> ศูนย์ฝึก — เคสจัดซื้อเสมือนจริง ให้บริษัท AI ฝึกซ้ำ แล้วเก็บบทเรียนเข้า memory

## Why

A real organization gets better by doing. Simulation lets the AI company practice
decisions safely, expose weak frameworks, and grow knowledge before touching real
KRDA spend. This is the engine behind [Continuous Improvement](../improvement/README.md).

## How a Scenario Runs (training loop)

```
pick scenario ─► run through Workflow Engine (stages 2–11)
              ─► produce Executive Recommendation
              ─► score vs gold-standard (rubric)
              ─► capture lessons ─► /improvement + memory lessons-learned
              ─► if a framework/knowledge gap found ─► action item
```

## Scenario Schema

Every scenario file (see [_TEMPLATE.md](_TEMPLATE.md)) has: context, trigger, data
given, the ask, the **expected pipeline** (workflows/frameworks to apply), a
**gold-standard approach**, pitfalls, and a **scoring rubric**.

## Categories & Target (≥100)

| Category | Target | Seeded |
|----------|:------:|:------:|
| RFQ | 12 | ✅ |
| Supplier Selection | 10 | — |
| Late Delivery | 10 | ✅ |
| Poor Quality | 10 | — |
| Price Increase | 10 | ✅ |
| Engineering Change | 10 | ✅ |
| New Supplier | 8 | ✅ |
| Cost Down | 12 | — |
| Localization | 6 | — |
| NDA | 6 | — |
| Contract Review | 6 | — |
| **Total** | **100** | |

Seeds live in [scenarios/](scenarios/); the full set is generated toward v1.0 (see
[index.md](index.md) and the generation plan there).

## Files

| File | Purpose |
|------|---------|
| [index.md](index.md) | Scenario catalog + the 100-case generation plan. |
| [_TEMPLATE.md](_TEMPLATE.md) | Scenario format. |
| `scenarios/SIM-*.md` | Individual scenarios. |

## Rules
- Scenarios are **synthetic** — no real supplier names/prices unless cleared.
- Same commitment gate applies in training: recommendations stop at the Human Owner line.
- Every run ends by capturing at least one lesson (even "framework worked").
