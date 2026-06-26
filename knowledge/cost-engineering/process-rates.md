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
| Laser cutting | CO₂ / fiber 2kW | `TBD` | Machine-hr | — | — | Mild steel ≤12mm; rate varies by power |
| Laser cutting | Fiber 4–6kW | `TBD` | Machine-hr | — | — | Thicker plate, faster |
| Plasma cutting | CNC plasma | `TBD` | Machine-hr | — | — | Lower tolerance, thick plate |
| Oxy-fuel cutting | Manual / CNC | `TBD` | Machine-hr | — | — | Thick section >25mm |
| Press brake bending | CNC press brake | `TBD` | Machine-hr | — | — | Up to 3m bend length |
| Punching | CNC turret punch | `TBD` | Machine-hr | — | — | Sheet metal holes/cutouts |
| Roll forming | Plate roll | `TBD` | Machine-hr | — | — | Cylindrical/conical shapes |

### Machining

| Process | Equipment type | Rate (THB/hr) | Basis | Source | Date | Notes |
|---|---|---|---|---|---|---|
| CNC turning | Lathe (small <500mm) | `TBD` | Machine-hr | — | — | Shaft, bushing, pin |
| CNC turning | Lathe (large >500mm) | `TBD` | Machine-hr | — | — | Large flange, drum |
| CNC milling | VMC 3-axis | `TBD` | Machine-hr | — | — | Bracket, housing |
| CNC milling | HMC / 4-axis | `TBD` | Machine-hr | — | — | Complex geometry |
| Grinding | Surface grinder | `TBD` | Machine-hr | — | — | Flat ground surface |
| Grinding | Cylindrical grinder | `TBD` | Machine-hr | — | — | Precision shaft |
| Drilling | Radial drill | `TBD` | Machine-hr | — | — | Large holes, manual |
| Tapping | CNC or manual | `TBD` | Machine-hr | — | — | Threaded holes |

### Welding & Fabrication

| Process | Rate (THB/hr) | Basis | Source | Date | Notes |
|---|---|---|---|---|---|
| MIG welding (manual) | `TBD` | Labor-hr | — | — | Most common for frames |
| TIG welding (manual) | `TBD` | Labor-hr | — | — | Precision/thin wall |
| Robotic MIG | `TBD` | Machine-hr | — | — | High-volume repeat weld |
| Spot welding | `TBD` | Machine-hr | — | — | Sheet metal assembly |
| Submerged arc | `TBD` | Machine-hr | — | — | Heavy plate buildup |

### Surface Treatment

| Process | Rate | Unit | Source | Date | Notes |
|---|---|---|---|---|---|
| Powder coating | `TBD` | THB/m² | — | — | Standard implement finish |
| Zinc electroplating | `TBD` | THB/m² | — | — | Corrosion protection small parts |
| Hot-dip galvanizing | `TBD` | THB/kg | — | — | Structural outdoor parts |
| Nickel plating | `TBD` | THB/m² | — | — | Wear/corrosion |
| Shot blasting | `TBD` | THB/m² | — | — | Surface prep before coat |
| Heat treatment (CH) | `TBD` | THB/kg | — | — | Carburize + harden |
| Annealing | `TBD` | THB/kg | — | — | Stress relief |

### Casting & Forging

| Process | Rate | Unit | Source | Date | Notes |
|---|---|---|---|---|---|
| Sand casting (grey iron) | `TBD` | THB/kg | — | — | Housing, bracket |
| Die casting (aluminium) | `TBD` | THB/kg | — | — | Complex near-net shape |
| Drop forging (steel) | `TBD` | THB/kg | — | — | Sprocket, link, crank |

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
