---
id: material-rates
title: Material Rates Reference
owner: Cost Reduction (CC)
status: active
updated: 2026-06-26
links: [should-cost-method.md, yield-scrap.md]
---

# Material Rates Reference

> Rates for should-cost modeling. **Every rate must carry a source and date.**
> Mark estimates `EST`. Update when market moves >5% or rate is >3 months old.
>
> All rates in **THB** unless noted. Exchange rate ref: TH Customs / BOT.

---

## Rate Table — Last Updated 2026-06-26

| Material | Grade / Spec | Form | Rate (THB/kg) | Source | Date | Notes |
|---|---|---|---|---|---|---|
| Mild steel | SS400 / A36 | Plate ≥3mm | `TBD` | — | — | Common implement frame material |
| Mild steel | SPHC | Hot-rolled coil | `TBD` | — | — | Sheet metal stamping |
| Mild steel | SPCC | Cold-rolled sheet | `TBD` | — | — | Cover/guard panels |
| Carbon steel | S45C | Round bar | `TBD` | — | — | Shaft, pivot pin |
| Carbon steel | S55C | Flat bar / plate | `TBD` | — | — | Blade, cutting edge |
| Alloy steel | SCM440 | Round bar | `TBD` | — | — | High-stress rotating parts |
| Stainless | SUS304 | Sheet / plate | `TBD` | — | — | Corrosion-exposed parts |
| Aluminium | A6061-T6 | Plate / bar | `TBD` | — | — | Weight-critical brackets |
| Aluminium | A5052 | Sheet | `TBD` | — | — | Non-structural covers |
| Natural rubber | NR | Sheet / roll | `TBD` | — | — | Vibration isolation, seal |
| NBR rubber | 70 Shore | Sheet | `TBD` | — | — | Oil-resistant seals |
| HDPE | GP | Sheet / rod | `TBD` | — | — | Wear liner, guide |
| PA66 (Nylon) | — | Rod / tube | `TBD` | — | — | Low-friction bushing |

> **Fill TBD:** Get current prices from: NS BlueScope Thailand / SSI / local steel service center. Or request supplier cost breakdown.

---

## How to Use Rates

1. Obtain net part weight from drawing or CAD (kg).
2. Apply scrap factor → [yield-scrap.md](yield-scrap.md).
3. `Material cost = Net weight × (1 + scrap%) × Rate (THB/kg)`
4. If part uses multiple materials, calculate each separately and sum.

---

## Rate Sources (Thailand)

| Material type | Suggested source |
|---|---|
| Steel | NS BlueScope Thailand price list; SSI (Sahaviriya Steel); local service center quotation |
| Aluminium | Thai Aluminium Co. / distributor quotation |
| Rubber | Thai Rubber Association (TRA) natural rubber price; NR price board |
| Plastics | Distributor quotation (LG Chem, SABIC agents in Thailand) |
| International reference | LME (London Metal Exchange) for copper, aluminium, nickel |

---

## Exchange Rate (for import materials)

| Currency pair | Rate | Date | Source |
|---|---|---|---|
| USD/THB | `TBD` | — | Bank of Thailand (BOT) |
| JPY/THB | `TBD` | — | BOT |
| EUR/THB | `TBD` | — | BOT |

Import duty rates (Thai Customs) vary by HS code — confirm before using for import materials.

---

## Update Protocol

- Refresh rates when: market news reports >5% steel price movement, or rate date >3 months.
- New rate entry: fill all columns including source URL/document and date.
- Old rate: do not delete — add a new row with new date; keeps history.
