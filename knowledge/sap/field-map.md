---
id: sap-field-map
title: SAP PR/PO Field Map (KRDA)
owner: SAP Purchasing (TS)
status: active
updated: 2026-06-26
links: [../procurement/procedure.md, ../../workflows/sap.md, ../../brain/approval-matrix.md]
---

# SAP PR/PO Field Map (KRDA)

> Reference for preparing SAP-ready PR/PO and master data. **Field lists are the
> standard SAP MM set; confirm KRDA-specific required fields, value lists, and
> custom (Z) fields with the SAP key user before binding use.** Mark unknowns `TBD`.

## Transaction Codes (SAP MM)

| T-code | Use |
|--------|-----|
| ME51N / ME52N / ME53N | Create / change / display Purchase Requisition (PR) |
| ME21N / ME22N / ME23N | Create / change / display Purchase Order (PO) |
| ME2N / ME2L / ME2M | PO list by number / vendor / material |
| XK01 / XK02 / XK03 | Create / change / display vendor master (central) |
| MM01 / MM02 / MM03 | Create / change / display material master |
| ME11 / ME12 / ME13 | Create / change / display purchasing info record |
| ME01 | Maintain source list |
| MIGO | Goods receipt |
| MIRO | Invoice verification |

> Confirm which T-codes KRDA authorizes for the AI-prepared workflow vs. human posting.

## Purchase Requisition (PR) — key fields

| Field | SAP name | Notes |
|-------|----------|-------|
| Material | MATNR | Or short text if no material master |
| Short text | TXZ01 | Description |
| Quantity | MENGE | + base unit MEINS |
| Delivery date | EEIND | Required |
| Plant | WERKS | KRDA plant code `TBD` |
| Purchasing group | EKGRP | Buyer group `TBD` |
| Account assignment | KNTTP | e.g. K=cost center, F=order, P=project |
| Cost center / Order / WBS | KOSTL / AUFNR / PS_PSP_PNR | R&D project trace |
| Tracking / requisitioner | AFNAM | Who requested |
| Valuation price | PREIS | Estimated price |

## Purchase Order (PO) — key fields

| Field | SAP name | Notes |
|-------|----------|-------|
| Vendor | LIFNR | Must exist in vendor master |
| Company code | BUKRS | `TBD` |
| Purchasing org | EKORG | `TBD` |
| Net price | NETPR | + currency WAERS (THB default) |
| Incoterms | INCO1 / INCO2 | e.g. EXW, FCA, DAP |
| Payment terms | ZTERM | e.g. NT30 = net 30 days |
| Delivery date | EINDT | Per schedule line |
| Tax code | MWSKZ | VAT 7% (Thailand) — confirm code |
| Cost assignment | KNTTP + KOSTL/AUFNR | As PR |

## Master Data Prerequisites

- **Vendor master (XK01):** legal name (TH/EN), Tax ID (13-digit), address, bank
  details, payment terms, reconciliation account. Dual approval (PU + Accounting) to create.
- **Material master (MM01):** material number, type, base UoM, purchasing group, plant.
- **Info record (ME11):** vendor × material price reference; update after each award.
- **Source list (ME01):** approved sources per material; mark fixed source if single-source.

## Rules
- Verify the [approval-matrix](../../brain/approval-matrix.md) band is satisfied **before**
  flagging a PR/PO for Human Owner posting (per [KB-PROC-001](../procurement/procedure.md)).
- Never post — AI prepares; Human Owner posts/releases (D3).
- Search existing vendor/material **before** creating (no duplicates).
- Default Thailand: currency THB, VAT 7%; confirm exact tax code.

## To Confirm With KRDA SAP Key User (`TBD`)
- [ ] Plant (WERKS), company code (BUKRS), purchasing org/group codes
- [ ] Custom Z-fields on PR/PO, mandatory fields, value lists
- [ ] Release strategy / approval workflow mapping to the approval-matrix bands
- [ ] Tax codes, payment-term keys used
