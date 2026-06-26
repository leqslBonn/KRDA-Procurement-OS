---
id: overhead-sga-profit
title: Overhead, SGA & Profit Rates
owner: Cost Reduction (CC)
status: active
updated: 2026-06-26
links: [should-cost-method.md, labor-rates.md, process-rates.md]
---

# Overhead, SGA & Profit Rates

> Applied on top of direct costs (material + process + labor) in should-cost
> models. Rates vary by supplier type and size. Use appropriate tier.

---

## The Stack

```
Direct cost base = Material + Process + Labor

Manufacturing overhead  = Direct base × Overhead %
                        (factory rent, utilities, supervision, maintenance)

Cost of goods (COGS)   = Direct base + Manufacturing overhead

SGA (Selling, General  = COGS × SGA %
& Administrative)       (sales team, admin, management, finance)

Total cost             = COGS + SGA

Profit                 = Total cost × Profit %

Selling price          = Total cost + Profit
(= Should-cost)
```

---

## Rate Benchmarks by Supplier Type (Thailand, EST)

| Supplier type | Overhead % | SGA % | Profit % | Total markup on direct cost |
|---|---|---|---|---|
| Large manufacturer (>500 staff, high automation) | 25–35% | 8–12% | 10–15% | ~50–65% |
| Mid-size fabricator (50–500 staff) | 20–30% | 6–10% | 8–12% | ~38–55% |
| Small fabricator / job shop (<50 staff, Pathumthani) | 15–25% | 4–8% | 8–15% | ~30–52% |
| Casting / forging specialist | 20–30% | 5–8% | 10–15% | ~38–57% |
| Surface treatment job shop | 15–20% | 4–6% | 8–12% | ~28–40% |
| Trading company (buying & reselling) | 5–10% | 10–20% | 10–25% | **Very high** — prefer direct manufacturer |

> All rates `EST`. Use for modeling; confirm with supplier breakdown if possible.

---

## Conservative Modeling Rate (default when supplier type unknown)

| Element | Rate |
|---|---|
| Manufacturing overhead | **20%** of direct base |
| SGA | **8%** of COGS |
| Profit | **10%** of total cost |

These are mid-range rates for a typical Thai SME manufacturer.

---

## Example Calculation

Assume direct base (material + process + labor) = 1,000 THB:

| Step | Calculation | Value |
|---|---|---|
| Manufacturing overhead | 1,000 × 20% | 200 |
| COGS | 1,000 + 200 | 1,200 |
| SGA | 1,200 × 8% | 96 |
| Total cost | 1,200 + 96 | 1,296 |
| Profit | 1,296 × 10% | 130 |
| **Should-cost** | 1,296 + 130 | **1,426 THB** |

If supplier quotes 2,000 THB → gap = 574 THB (40%) → investigate which element.

---

## How to Use in Negotiation

1. Share the model logic (not necessarily the numbers) with supplier.
2. Ask supplier to confirm: "Is your overhead rate in line with industry typical?"
3. If supplier claims overhead >35% on a standard fabrication job → challenge or ask for plant tour / P&L reference.
4. Profit: 8–12% is reasonable for a healthy Thai manufacturer. <5% is unsustainable; >20% is excessive unless highly specialized.

---

## Notes

- **Trading company premium:** If buying via distributor/trader, add 15–30% on top of manufacturer should-cost. Always try to source from manufacturer directly for strategic parts.
- **Vertical integration:** A supplier who does laser + bend + weld + coat in-house will have lower SGA than one who subcontracts steps.
- **Volume effect on overhead:** Overhead per unit drops as volume rises (fixed cost spread). Adjust model if KRDA volume is significantly different from supplier's typical run.
