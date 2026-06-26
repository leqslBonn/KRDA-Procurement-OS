---
id: yield-scrap
title: Yield & Scrap Factors
owner: Cost Reduction (CC)
status: active
updated: 2026-06-26
links: [should-cost-method.md, material-rates.md]
---

# Yield & Scrap Factors

> The difference between **net part weight** and **actual material purchased**.
> Always apply in should-cost — ignoring scrap understates material cost.

---

## 1. Key Terms

| Term | Definition |
|---|---|
| **Net weight** | Weight of the finished part (from drawing / CAD) |
| **Gross weight** | Material purchased to make one part (net + all scrap) |
| **Scrap factor** | (Gross − Net) ÷ Net × 100% |
| **Yield** | Net ÷ Gross × 100% |
| **Buy-to-fly ratio** | Gross ÷ Net (same as 1 + scrap%) |

```
Gross weight = Net weight × (1 + scrap%)
Material cost = Gross weight × Material rate (THB/kg)
```

---

## 2. Typical Scrap Factors by Process (Thailand, EST)

| Process | Scrap factor | Buy-to-fly | Notes |
|---|---|---|---|
| Laser cut from sheet | 15–35% | 1.15–1.35 | Depends on nesting efficiency |
| Plasma / oxy-fuel cut | 20–40% | 1.20–1.40 | Wider kerf, lower nesting |
| CNC turning (bar stock) | 30–60% | 1.30–1.60 | Depends on part vs. bar diameter |
| CNC milling (plate) | 20–50% | 1.20–1.50 | Depends on pocket depth, geometry |
| Forging (from billet) | 10–20% | 1.10–1.20 | Near-net; flash trimmed |
| Sand casting | 20–40% | 1.20–1.40 | Runner/riser + rejection rate |
| Die casting | 10–25% | 1.10–1.25 | Runner + trim; high yield at volume |
| Stamping (progressive) | 15–30% | 1.15–1.30 | Skeleton scrap; recoverable |
| Sheet metal bend (pre-cut) | 3–8% | 1.03–1.08 | Minimal if laser pre-cut |
| Welded fabrication (steel) | 5–10% | 1.05–1.10 | Consumables + weld spatter |

> All `EST`. Nesting efficiency (laser, plasma) varies widely — get actual nesting ratio from supplier for precision model.

---

## 3. Scrap Recovery Credit

Scrap material has resale value (steel swarf, offcuts):

| Material | Scrap value (THB/kg) | Source | Date |
|---|---|---|---|
| Steel scrap (mixed) | `TBD` | Local scrap dealer | — |
| Aluminium scrap | `TBD` | Local scrap dealer | — |
| Cast iron scrap | `TBD` | Local scrap dealer | — |

**Net material cost after recovery:**
```
Net material cost = (Gross weight × Buy rate) − (Scrap weight × Scrap rate)
```

For should-cost, scrap credit is often omitted (conservative approach). Include when negotiating with a high-volume supplier who recovers it.

---

## 4. Process Rejection / Rework Factor

Separate from geometric scrap — units that fail quality inspection:

| Process | Typical rejection rate | Notes |
|---|---|---|
| Laser cut (CNC) | 0.5–2% | Low for CNC processes |
| Manual welding | 2–8% | Depends on operator skill |
| Sand casting | 3–10% | Shrinkage, porosity |
| Die casting | 1–5% | At established production |
| Machining (CNC) | 1–3% | Setup scrap higher for new programs |
| Surface treatment | 1–5% | Re-process or scrap |

Rejection cost per unit:
```
Rejection adder = (Unit cost before reject) × rejection rate
```

Apply when modeling complex or new processes.

---

## 5. How to Estimate Net Weight

1. From CAD model: use mass properties (set correct material density).
2. From drawing: calculate volume from dimensions, × material density.
   - Steel density: 7.85 kg/dm³ (7,850 kg/m³)
   - Aluminium: 2.70 kg/dm³
   - Cast iron: 7.20 kg/dm³
3. If no CAD/drawing: weigh a sample part directly.

Mark weight as `EST` if calculated without CAD; note method.
