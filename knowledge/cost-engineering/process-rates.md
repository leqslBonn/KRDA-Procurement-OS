---
id: process-rates
title: Process & Machine Rates Reference
owner: Cost Reduction (CC)
status: active
updated: 2026-06-26
links: [should-cost-method.md, labor-rates.md, overhead-sga-profit.md]
---

# Process & Machine Rates Reference

> Machine-hour rates for should-cost modeling. Rates = full absorption (machine
> depreciation + energy + tooling wear + operator), **excluding** overhead & SGA
> (applied separately). Mark estimates `EST`. Source and date required.

---

## Rate Table — Last Updated 2026-06-26

### Metal Cutting & Forming

| Process | Equipment type | Rate (THB/hr) | Basis | Source | Date | Notes |
|---|---|---|---|---|---|---|
| Laser cutting | CO₂ / fiber 2kW | 1,200 `EST` | Machine-hr | Market benchmark | 2026-06 | Mild steel ≤12mm |
| Laser cutting | Fiber 4–6kW | 1,800 `EST` | Machine-hr | Market benchmark | 2026-06 | Thicker plate, faster |
| Plasma cutting | CNC plasma | 900 `EST` | Machine-hr | Market benchmark | 2026-06 | Lower tolerance, thick plate |
| Oxy-fuel cutting | Manual / CNC | 600 `EST` | Machine-hr | Market benchmark | 2026-06 | Thick section >25mm |
| Press brake bending | CNC press brake | 900 `EST` | Machine-hr | Market benchmark | 2026-06 | Up to 3m bend length |
| Punching | CNC turret punch | 1,000 `EST` | Machine-hr | Market benchmark | 2026-06 | Sheet metal holes/cutouts |
| Roll forming | Plate roll | 800 `EST` | Machine-hr | Market benchmark | 2026-06 | Cylindrical/conical |

### Machining

| Process | Equipment type | Rate (THB/hr) | Basis | Source | Date | Notes |
|---|---|---|---|---|---|---|
| CNC turning | Lathe (small <500mm) | 700 `EST` | Machine-hr | Market benchmark | 2026-06 | Shaft, bushing, pin |
| CNC turning | Lathe (large >500mm) | 1,100 `EST` | Machine-hr | Market benchmark | 2026-06 | Large flange, drum |
| CNC milling | VMC 3-axis | 900 `EST` | Machine-hr | Market benchmark | 2026-06 | Bracket, housing |
| CNC milling | HMC / 4-axis | 1,400 `EST` | Machine-hr | Market benchmark | 2026-06 | Complex geometry |
| Grinding | Surface grinder | 700 `EST` | Machine-hr | Market benchmark | 2026-06 | Flat ground surface |
| Grinding | Cylindrical grinder | 900 `EST` | Machine-hr | Market benchmark | 2026-06 | Precision shaft |
| Drilling | Radial drill | 450 `EST` | Machine-hr | Market benchmark | 2026-06 | Large holes, manual |
| Tapping | CNC or manual | 450 `EST` | Machine-hr | Market benchmark | 2026-06 | Threaded holes |

### Welding & Fabrication

| Process | Rate (THB/hr) | Basis | Source | Date | Notes |
|---|---|---|---|---|---|
| MIG welding (manual) | 450 `EST` | Labor-hr | Market benchmark | 2026-06 | Most common for frames |
| TIG welding (manual) | 550 `EST` | Labor-hr | Market benchmark | 2026-06 | Precision/thin wall |
| Robotic MIG | 1,200 `EST` | Machine-hr | Market benchmark | 2026-06 | High-volume repeat weld |
| Spot welding | 600 `EST` | Machine-hr | Market benchmark | 2026-06 | Sheet metal assembly |
| Submerged arc | 900 `EST` | Machine-hr | Market benchmark | 2026-06 | Heavy plate buildup |

### Surface Treatment

| Process | Rate | Unit | Source | Date | Notes |
|---|---|---|---|---|---|
| Powder coating | 250 `EST` | THB/m² | Market benchmark | 2026-06 | Standard implement finish |
| Zinc electroplating | 180 `EST` | THB/m² | Market benchmark | 2026-06 | Corrosion protection |
| Hot-dip galvanizing | 35 `EST` | THB/kg | Market benchmark | 2026-06 | Structural outdoor parts |
| Nickel plating | 400 `EST` | THB/m² | Market benchmark | 2026-06 | Wear/corrosion |
| Shot blasting | 120 `EST` | THB/m² | Market benchmark | 2026-06 | Surface prep before coat |
| Heat treatment (CH) | 45 `EST` | THB/kg | Market benchmark | 2026-06 | Carburize + harden |
| Annealing | 25 `EST` | THB/kg | Market benchmark | 2026-06 | Stress relief |

### Casting & Forging

| Process | Rate | Unit | Source | Date | Notes |
|---|---|---|---|---|---|
| Sand casting (grey iron) | 75 `EST` | THB/kg | Market benchmark | 2026-06 | Housing, bracket (excl. pattern) |
| Die casting (aluminium) | 180 `EST` | THB/kg | Market benchmark | 2026-06 | Complex near-net shape |
| Drop forging (steel) | 90 `EST` | THB/kg | Market benchmark | 2026-06 | Sprocket, link, crank |

> ⚠️ **All rates above are `EST` indicative Thailand job-shop benchmarks (mid-2026),
> NOT KRDA quotes.** Use for first-pass should-cost only. **Calibrate by back-calculating
> from 2–3 real supplier quotes** (see Rate Sources below), then update Source/Date.

---

## How to Use Process Rates

1. Identify all processes the part requires (from drawing + manufacturing knowledge).
2. Estimate machine time per unit — from part complexity, size, batch size.
   - For laser: estimate cut length (m) ÷ cut speed (m/min) + pierce count × pierce time.
   - For turning: estimate diameter × length → compute material removal volume → cycle time.
   - Mark cycle time as `EST` if not measured.
3. Add setup time ÷ batch size = setup cost per unit.
4. `Process cost/unit = Σ (Rate_i × Cycle_time_i) + Setup/batch`

---

## Setup Time Guidelines (EST)

| Process | Setup time (hr) |
|---|---|
| CNC laser (new program) | 0.25–0.5 |
| Press brake (per setup) | 0.25–1.0 |
| CNC turning (new program) | 0.5–1.5 |
| CNC milling (new program) | 1.0–3.0 |
| Welding fixture setup | 0.5–2.0 |

---

## Rate Sources (Thailand)

- Obtain from supplier quotation breakdowns (ask for itemized cost).
- Get 2–3 vendor quotes for a sample part → back-calculate implied rate.
- Industry reference: Thai industrial machinery association, trade publications.
- Internal: if KRDA has built similar parts before, use historical cost + inflation adjustment.
