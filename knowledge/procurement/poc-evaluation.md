---
id: poc-evaluation
title: POC / Pilot Evaluation Method
owner: Procurement (all) / Technical Purchasing
status: active
updated: 2026-06-26
links: [../../brain/startup-vendor-evaluation-framework.md, saas-tco.md]
---

# POC / Pilot Evaluation Method

> How to run a **proof-of-concept / pilot** with an IoT/smart-farm/software vendor so it
> proves something — and doesn't trap you in "pilot purgatory."

## Why
For a startup with no production track record, a POC is how you de-risk before buying.
But a bad POC wastes months, leaks data, or quietly becomes lock-in. Define it tightly.

## Define BEFORE Starting (the contract of the POC)

| Item | Decide upfront |
|------|----------------|
| Objective | The one question the POC must answer |
| Success criteria | Specific, measurable KPIs + thresholds (go/no-go) |
| Scope | Sites, devices, users, features — keep it small |
| Duration | Fixed end date (e.g. 4–8 weeks) — no open-ended |
| Data | What data is shared; **KRDA owns it**; deletion after |
| Cost | Paid vs free POC; who funds hardware/effort |
| IP / NDA | NDA in place; ownership of anything built |
| Exit | What happens to data/devices at the end; no auto-rollover |

## Success Criteria (examples — make them measurable)

- Sensor data accuracy ≥ X% vs reference
- System uptime ≥ X% over the pilot
- Integration with existing system works (data flows end-to-end)
- Farmer/operator can use it (usability check)
- Scales from 1 → N devices without breaking

## Run & Evaluate

1. Baseline before the POC (so you can measure improvement).
2. Run within fixed scope/duration; log issues + vendor responsiveness.
3. Score against the **pre-agreed** success criteria — not moved goalposts.
4. Feed the result into the [vendor scorecard](../../templates/vendor-pitch-scorecard.md)
   (criterion #2 maturity, #6 integration, #11 support).

## Go / No-Go Decision

- **Go:** success criteria met + data/escrow/exit terms secured → recommend award (D3 → Human Owner).
- **Iterate:** close but gaps → defined second round, fixed scope.
- **No-go:** criteria missed or red flags → stop; data deleted; no obligation.

## Pitfalls
- ❌ Starting a POC with no written success criteria → can't say no.
- ❌ Open-ended pilot that drifts for months (pilot purgatory).
- ❌ Letting the vendor keep/own the farm data from the POC.
- ❌ POC quietly auto-converting to a paid contract.

## Links
- Framework: [startup-vendor-evaluation-framework](../../brain/startup-vendor-evaluation-framework.md)
- TCO: [saas-tco](saas-tco.md) · NDA: [nda workflow](../../workflows/nda.md)
