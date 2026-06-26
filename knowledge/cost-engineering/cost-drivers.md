---
id: cost-drivers
title: Cost Drivers — What Makes Parts Expensive
owner: Cost Reduction (CC)
status: active
updated: 2026-06-26
links: [should-cost-method.md, material-rates.md, process-rates.md]
---

# Cost Drivers — What Makes Parts Expensive

> Understanding cost drivers tells you WHERE to attack. Use this before running
> a should-cost model — identify the dominant drivers first.

---

## 1. The Pareto Rule of Part Cost

Typically, 1–2 drivers account for 70–80% of part cost:

| Dominant cost element | Typical part type |
|---|---|
| Material | Large heavy parts (frame, housing, ballast) |
| Machining time | Precision parts (shaft, gear, hydraulic body) |
| Manual labor | Complex weld assemblies, multi-operation builds |
| Tooling / NRE | High-complexity castings, stampings (first order) |
| Surface treatment | Parts with complex coating spec or large area |
| Supplier margin | Trading company in chain; monopoly supplier |

---

## 2. Material Cost Drivers

| Driver | Lever |
|---|---|
| Heavy part (high net weight) | Lightweight redesign (VA/VE) — reduce section, change geometry |
| Premium material grade | Downgrade to lower grade if engineering allows (must confirm with Technical Purchasing) |
| High scrap factor | Better nesting, near-net process (forging vs. machining), or blank optimization |
| Import material (forex + duty) | Switch to domestic equivalent |
| Low-volume high-rate | Aggregate demand across projects; buy in larger batch |

---

## 3. Process Cost Drivers

| Driver | Lever |
|---|---|
| Long machine cycle time | Optimize geometry for faster cutting; higher-power machine |
| High setup cost (small batch) | Increase batch size; combine with similar parts |
| Multiple process steps | Combine operations (laser cut + form in one machine) |
| Manual operations | Automate or use CNC |
| Precision tolerance (tight) | Relax if not functional-critical (Engineering must approve) |
| Complex surface treatment | Simplify spec if corrosion/wear requirements allow |

---

## 4. Labor Cost Drivers

| Driver | Lever |
|---|---|
| Long weld seams | Weld design optimization (fewer, shorter passes) |
| High-skill welder required | Simplify joint geometry |
| Multi-pass weld (thick section) | Reduce section where possible; verify structural adequacy |
| Manual assembly complexity | Design for assembly (DFA) — reduce parts, simplify fit |

---

## 5. Overhead & Margin Drivers

| Driver | Lever |
|---|---|
| Trading company in supply chain | Source direct from manufacturer |
| Sole-source monopoly | Develop second source |
| Supplier high SGA (sales-heavy) | Negotiate; or find leaner manufacturer |
| KRDA is small customer (low priority) | Bundle spend, offer longer commitment for volume discount |

---

## 6. KRDA-Specific Cost Driver Patterns

For KRDA's typical parts (agricultural implements, R&D prototypes):

| Part family | Dominant driver | Common lever |
|---|---|---|
| Implement frame (welded steel) | Material weight + weld labor | Reduce plate thickness where structural analysis allows; optimize weld count |
| Blade / cutting edge | Material grade (S55C, hardfacing) | Volume consolidation; hardfacing vs. alloy steel trade-off |
| Hydraulic cylinder (custom) | Machining (bore, seal groove) + material (tube) | Standardize bore sizes; avoid non-standard stroke |
| Cast housing | Tooling (first order) + casting yield | Amortize over larger lifetime volume; design for DFM |
| Sprocket / chain | Material + hobbing process | Buy standard pitch if possible; custom only if necessary |
| Fasteners (bolts, nuts) | Supplier margin (trading) | Source directly from distributor/manufacturer; aggregate |
| Prototype one-offs | Setup cost dominant | Laser cut from flat (no tooling); avoid complex machining |

---

## 7. How to Use This File

1. **Before modeling:** identify the 1–2 dominant drivers from the table above.
2. **Build the should-cost:** focus accuracy on the dominant elements; EST others.
3. **Gap analysis:** if quote > should-cost, look at driver → identify which element is inflated.
4. **VA/VE ideas:** use the lever column to generate design-for-cost proposals.
5. **Negotiation brief:** present the driver to the supplier: "We calculate material accounts for 60% of cost; current steel price is X, suggesting a different price than your quote."
