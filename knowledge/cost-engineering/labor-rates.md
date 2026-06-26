---
id: labor-rates
title: Labor Rates Reference (Thailand)
owner: Cost Reduction (CC)
status: active
updated: 2026-06-26
links: [should-cost-method.md, process-rates.md, overhead-sga-profit.md]
---

# Labor Rates Reference (Thailand)

> Direct labor rates for should-cost modeling. Rates = direct wage + statutory
> benefits. Overhead & SGA applied separately. Source and date required.

---

## Thailand Minimum Wage (2026)

| Region | Min. wage (THB/day) | THB/hr (8-hr day) | Source | Date |
|---|---|---|---|---|
| Bangkok & vicinity | `TBD` | `TBD` | Ministry of Labour | `TBD` |
| Pathumthani | `TBD` | `TBD` | Ministry of Labour | `TBD` |
| General provincial | `TBD` | `TBD` | Ministry of Labour | `TBD` |

> Ministry of Labour (mol.go.th) announces minimum wage annually. Confirm current rate.

---

## Effective Direct Labor Rate (with statutory benefits)

Statutory benefits in Thailand add ~20–30% on top of base wage:

| Benefit | % of base wage |
|---|---|
| Social Security (employer share) | 5% |
| Provident fund (typical) | 3–5% |
| Annual leave, sick leave, holidays | ~8–10% |
| Other statutory (workmen's comp, etc.) | ~2–3% |
| **Total burden factor** | **~18–25%** |

```
Effective rate (THB/hr) = Min. wage rate × (1 + burden factor)
```

---

## Skill-Level Rate Multipliers (Thailand manufacturing, EST)

| Skill level | Role examples | Multiplier vs. minimum wage |
|---|---|---|
| Unskilled / general labor | Material handling, cleaning | 1.0× |
| Semi-skilled | Press operator, basic assembly | 1.1–1.3× |
| Skilled | CNC operator, MIG welder | 1.5–2.0× |
| Highly skilled | TIG welder, CNC programmer | 2.0–3.0× |
| Technician / QC inspector | CMM operator, quality tech | 2.5–3.5× |

> Multipliers are `EST` — adjust based on actual supplier labor market.

---

## Rate Table (fill when confirmed)

| Skill level | THB/hr (base) | THB/hr (with burden) | Date | Source |
|---|---|---|---|---|
| Unskilled | `TBD` | `TBD` | — | — |
| Semi-skilled | `TBD` | `TBD` | — | — |
| Skilled welder / CNC op. | `TBD` | `TBD` | — | — |
| TIG welder / senior machinist | `TBD` | `TBD` | — | — |

---

## How to Use Labor Rates

1. Identify direct labor operations that cannot be attributed to a machine rate.
   - Manual welding → labor hours × skilled welder rate.
   - Machine-paced work (CNC) → labor component is small (load/unload only); captured in machine rate.
   - Manual assembly → estimate labor hours from operation list.
2. `Labor cost = Σ (Hours_i × Rate_i)`
3. Mark time estimates `EST` if not time-studied.

---

## Notes on Thai Labor Context

- **Pathumthani** (where KRDA is located): slightly above Bangkok minimum due to industrial competition.
- Overtime premium: 1.5× regular rate on weekdays; 2× on holidays (Labour Protection Act).
- For should-cost: use regular-time rate unless the process requires overtime by design.
- Foreign labor (Myanmar, Cambodia, Laos) is common in Thai fabrication shops — often at minimum wage level even for skilled roles. Account for this in rate calibration.

---

## Update Protocol

- Check Ministry of Labour announcement each January (effective from Jan or Apr).
- If supplier claims labor cost significantly exceeds these rates → ask for payroll evidence.
- If supplier is in higher-wage province (e.g., Bangkok core), apply regional premium.
