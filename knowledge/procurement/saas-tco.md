---
id: saas-tco
title: Software / SaaS TCO Method (3–5 year)
owner: Procurement (all) / Cost Reduction
status: active
updated: 2026-06-26
links: [../../brain/startup-vendor-evaluation-framework.md, poc-evaluation.md]
---

# Software / SaaS TCO Method (3–5 year)

> The "should-cost" equivalent for **software / IoT / SaaS** — total cost over the real
> ownership period, not the upfront subscription. Use to compare vendors fairly.

## Why
A SaaS pitch shows a low monthly price. The real cost is the **3–5 year total**:
integration, cloud, support, growth in users/devices, and the cost to **leave**. Compare
vendors on TCO, not sticker.

## Cost Elements

| Element | One-time | Recurring | Notes |
|---------|:--------:|:---------:|-------|
| Subscription / license | | ✅ | Per user / device / site / data volume — confirm the unit |
| Implementation / setup | ✅ | | Onboarding, config |
| Integration / API dev | ✅ | (maint.) | Connect to existing systems, SAP, sensors |
| Customization | ✅ | | Vendor or internal effort |
| Hardware / IoT devices | ✅ | (replace) | Sensors, gateways, connectivity |
| Connectivity | | ✅ | SIM/data, network |
| Cloud / hosting | | ✅ | If not in subscription |
| Data migration | ✅ | | In and (importantly) **out** |
| Training | ✅ | (refresh) | Users + admins |
| Support / maintenance | | ✅ | SLA tier; updates |
| Internal admin/ops effort | | ✅ | Your team's time to run it |
| **Exit / switching cost** | ✅ (future) | | Data export, re-platform, escrow — the lock-in tax |

## Method

1. Pick the horizon (3 or 5 yr) — same for all vendors.
2. List every element above; mark one-time vs recurring; get the **unit** right
   (per user? per device? per site?).
3. Project growth (users/devices/sites over the horizon) — SaaS scales with usage.
4. `TCO = Σ one-time + Σ (recurring × horizon, grown by usage) + exit cost`
5. Normalize across vendors (same horizon, same scope, same growth assumptions).
6. Mark estimates `EST`; flag what the vendor must confirm in writing.

## TCO Comparison

| Element | Vendor A | Vendor B | Vendor C |
|---------|---------:|---------:|---------:|
| One-time total | | | |
| Recurring × horizon | | | |
| Exit / switching | | | |
| **3–5 yr TCO** | | | |
| TCO per site / per year | | | |

## Watch-outs
- **Per-unit traps:** "cheap per device" × thousands of devices = huge.
- **Overage / tier jumps:** price steps when data/users grow.
- **Exit cost is real:** data export fees, re-integration → favors open/portable vendors.
- A higher sticker with lower integration + exit cost can win on TCO.

## Links
- Framework: [startup-vendor-evaluation-framework](../../brain/startup-vendor-evaluation-framework.md)
- Scorecard criterion #8 (TCO): [vendor-pitch-scorecard](../../templates/vendor-pitch-scorecard.md)
