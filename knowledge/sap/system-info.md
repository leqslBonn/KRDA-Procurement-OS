---
id: KB-SAP-002
title: KRDA SAP System Environment
owner: SAP Purchasing
status: active
updated: 2026-06-30
source: "SAP System > Status + Installed Software (screenshots, 2026-06-30, user YEP2101001, client 100, system PE7)"
links: [./field-map.md, ../../workflows/sap.md, ../../company/overview.md]
---

# KRDA SAP System Environment

> Single source of truth for **which SAP KRDA runs**. Drives T-code validity,
> field maps, and SAP-agent (Kevin / TS) assumptions. Quote exact values; mark
> unknowns `TBD`.

> ⚠️ **Provisional (2026-06-30):** captured from the **PE7** system while user was
> on a training/observation login. User moves to the **real PU (Purchasing) role**
> on 2026-07-01 and will re-capture; confirm client/role/authorizations then.

---

## 1. Product Version

**SAP ERP 6.0, Enhancement Package 5 (EHP5)** — classic **ECC**, **not S/4HANA**.

Determined from installed software components (`System > Status` → Product Version
→ Installed Software):

| Component | Release | SP-Level | Meaning |
|-----------|:-------:|:--------:|---------|
| **SAP_APPL** | **605** | 0020 | **ERP 6.0 EhP5** — the version-defining component |
| SAP_BASIS | 702 | 0027 | NetWeaver 7.02 (7.0 EhP2) |
| SAP_ABA | 702 | 0027 | Application Basis (pairs with BASIS) |
| PI_BASIS | 702 | 0027 | Basis Plug-In |
| SAP_BS_FND | 702 | 0021 | Business Suite Foundation |
| SAP_BW | 702 | 0027 | Business Warehouse (embedded) |
| SAP_AP | 700 | 0039 | Application Platform |
| WEBCUIF | 701 | 0020 | Web UI Framework |
| SAP_HR | 600 | 0191 | HR / HCM |

UI: classic **SAP GUI** session (`SESSION_MANAGER`), not Fiori.

## 2. System / Landscape

| Item | Value |
|------|-------|
| System ID (SID) | **PE7** (production) |
| Client (observed) | **100** |
| Other connections (SAP Logon) | KRDA = PE7 · QAS-QE7 = QE7 (quality) · SKC-KRDA = PE2 |
| Installation number | 0021249592 |
| Unicode | Yes |
| License expiration | 31.12.9999 (no expiry) |

## 3. Technical Stack

| Layer | Value |
|-------|-------|
| Database | **Oracle 19c** (19.27.0.0.0) |
| Operating system | Linux, x86_64 |
| Server / host | P7D1VMDSI01 |
| DB schema owner | SAPSR3 |
| SAP GUI (client tool) | **7.40** ("SAP Logon 740") — separate from backend version |

## 4. Implications for Procurement OS

- T-codes in [field-map.md](./field-map.md) and [sap.md workflow](../../workflows/sap.md)
  are **ECC MM** codes — valid here (no S/4 Fiori-only flows).
- KRDA Favorites in use: PR — `ME51N` / `ME52N` / `ME53N`; PO — `ME21N`;
  source assign — `ME56`; goods movement — `MIGO` / `MB21` / `MB22` / `MBST`.
- No S/4HANA simplifications (e.g. Business Partner-only vendor model) apply;
  classic vendor master (`XK01/XK02/XK03`, `MK0x`) is in effect.

## 5. Open / To Confirm (after PU move, 2026-07-01)

- [ ] Re-capture `System > Status` from the **real PU client/role**.
- [ ] Confirm working **client** (still 100? or production PU client).
- [ ] Confirm **authorizations** (which T-codes the PU role can post vs display).
- [ ] Confirm exact **EhP/SP** if any patch applied during/after the move.
