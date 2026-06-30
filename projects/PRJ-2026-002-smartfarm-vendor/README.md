---
id: PRJ-2026-002
title: DRY-RUN — Smart-Farm IoT Vendor Selection (3 vendors)
owner: Chief of Staff
status: active
updated: 2026-06-26
links: [../../brain/startup-vendor-evaluation-framework.md, ../../templates/vendor-pitch-scorecard.md, ../../knowledge/procurement/saas-tco.md]
---

# Executive Recommendation — Smart-Farm IoT Vendor Selection

> **SYNTHETIC example** showing the report format. Vendors A/B/C and all numbers are
> illustrative. Real selection uses the same structure with real pitches/quotes.

| | |
|--|--|
| **Project** | Cassava trial-farm IoT: soil-moisture + weather sensors + dashboard + irrigation control |
| **Scope** | 50 sensor nodes, 5 gateways, 1 dashboard, 2 trial plots |
| **Owner (KRDA)** | Technical Purchasing (project controller) |
| **Date** | 2026-06-26 |
| **Decision class** | D3 (commitment) — 5-yr contract value > 2M THB |
| **Prepared via** | KRDA Procurement OS — [vendor eval framework](../../brain/startup-vendor-evaluation-framework.md) |

---

## 1. Objective
Select a vendor to build and operate a smart-farm IoT system for the cassava trial farm,
where **KRDA owns the data and the system can continue if the vendor fails.** Buy on total
value over 5 years, not the cheapest monthly price.

## 2. Recommendation
**Proceed with Vendor C (GrowLink) via a paid 8-week POC, then award on milestone terms.**
Hold Vendor A (AgriSense) as backup *if* it accepts KRDA data ownership. **Exclude Vendor B
(FarmIQ)** — fails the data-ownership and startup-viability gates.

## 3. Vendor Scorecard (weighted, score 1–5)

| Criterion | Wt | A · AgriSense | B · FarmIQ | C · GrowLink |
|-----------|:--:|:--:|:--:|:--:|
| Problem–solution fit | 15 | 4 | 4 | 4 |
| Technology & maturity (real vs slideware) | 15 | 5 | 2 *(demo only)* | 4 |
| Team & domain capability | 10 | 4 | 3 | 4 |
| Traction & references | 10 | 5 | 2 | 3 |
| Scalability | 10 | 4 | 2 | 4 |
| Integration & interoperability | 10 | 3 | 3 | 5 |
| **Data ownership & security (GATE)** | 10 | 2 🚩 | 1 🚩 | 5 ✓ |
| TCO 5-yr | 10 | 2 | 4 | 4 |
| **Startup viability (GATE)** | 5 | 4 | 1 🚩 | 4 |
| Lock-in / portability | 3 | 2 | 1 | 5 |
| Support & SLA | 2 | 4 | 3 | 4 |
| **Weighted total /5** | 100 | **3.6** | **2.4** | **4.1** |
| **Gate result** | | ⚠ data-owns-vendor | ✗ FAIL (3 gates) | ✓ PASS |

## 4. 5-Year TCO (THB) — [method](../../knowledge/procurement/saas-tco.md)

| Element | A · AgriSense | B · FarmIQ | C · GrowLink |
|---------|--------------:|-----------:|-------------:|
| Hardware (sensors/gateways), one-time | 550,000 | 380,000 | 480,000 |
| Setup / integration, one-time | 250,000 | 150,000 | 200,000 |
| Subscription (per yr × 5) | 1,400,000 | 900,000 | 1,100,000 |
| Support / SLA (per yr × 5) | 600,000 | 400,000 | 500,000 |
| Exit / switching (data export, re-platform) | 200,000 | 250,000 | 50,000 |
| **5-yr TCO** | **3,000,000** | **2,080,000** | **2,330,000** |

> B is cheapest on sticker but **fails the gates** → not eligible. Between eligible A and C,
> **C is ~670k cheaper over 5 yr AND owns-data/open** — clear winner on total value.

## 5. Evidence Basis (sources)
- Scorecards: this record (synthetic pitch notes) · TCO model: [saas-tco](../../knowledge/procurement/saas-tco.md)
- Gates: [startup-vendor-evaluation-framework](../../brain/startup-vendor-evaluation-framework.md)
- All figures `EST` / illustrative — real selection uses actual quotes + references.

## 6. Department Inputs (coverage — none skipped)

| Dept | Verdict | Key input |
|------|---------|-----------|
| OPL (Lead) | Lead | Coordinated eval; routes award to Human Owner |
| SE (Tech/Sourcing) | Contribute | C best integration; A most mature; B slideware on scale |
| SM (Supplier Dev) | Contribute | B viability risk (thin funding); C/A acceptable |
| CC (RFQ/Cost) | Contribute | 5-yr TCO: C best value among eligible |
| TS (SAP/Automation) | N/A | No SAP/master-data impact at selection stage |
| IP (Analytics) | Contribute | TCO model + scoring math (decision-matrix) |

## 7. Conflicts & Resolution
- **Cost vs gates:** B is cheapest (2.08M) — but fails data-ownership + viability + slideware
  gates → excluded despite price. *Gates override price.*
- **Maturity vs value:** A most mature (score 5 tech) but owns the data + costs most →
  conditional backup only if it accepts KRDA data ownership.

## 8. Risks & Open Items
- C is a smaller vendor → **POC first** to prove integration/scale before full award.
- Secure in contract: **KRDA data ownership, source-code escrow, milestone payments,
  10–20% retention, exit/data-export** ([contract-terms-checklist](../../templates/contract-terms-checklist.md)).
- ⚠️ **Approval routing:** 5-yr value > 2M THB. Per [approval-matrix](../../brain/approval-matrix.md)
  default (per-PO) the annual ~470k sits lower — **confirm whether KRDA approves on annual or
  total-contract value** (open item A2026-01).

## 9. Decision Required (Human Owner)
1. Approve **paid POC with Vendor C** (8 weeks, ~150k THB, defined success criteria —
   [poc-evaluation](../../knowledge/procurement/poc-evaluation.md)).
2. Authorize negotiation of contract terms (IP/data/escrow/milestones) with C.
3. Confirm the approval basis (annual vs total-contract) for the eventual award.

*No commitment is made until the Human Owner approves the above.*
