# SAP P01 Integration

!!! info "Designed — Pending IT/Admin Approval"

---

## Overview

The SAP P01 Integration project aims to connect the Vehicle Valuation Workflow directly to Al-Futtaim's SAP P01 environment (PAD IS Auto S/4HANA), enabling real-time access to vehicle header data and aftersales profiles during the appraisal process. The design is complete, including a 24-column SharePoint schema and a full technical specification document, but implementation is pending IT and admin approval.

---

## Technical Design

The integration uses a two-RFC architecture via the Power Automate SAP ERP Connector.

| RFC Function | Purpose |
|---|---|
| `Z_GET_VEHICLE_HEADER_BY_VIN` | Retrieves vehicle header information using VIN as the lookup key |
| `Z_GET_AFTERSALES_PROFILE_BY_INTVEHNO` | Retrieves the aftersales service profile using the internal vehicle number |

### Target SAP Environment

| Parameter | Value |
|---|---|
| **System** | P01 PAD IS Auto S/4HANA |
| **Client** | 100 |
| **Server** | vhoafpadai08 |
| **Connector** | Power Automate SAP ERP Connector |

---

## SharePoint Schema

A 24-column SharePoint schema has been designed to store the data retrieved from SAP. This schema is aligned with the broader Vehicle Valuation Workflow data architecture and supports the full appraisal lifecycle from intake to governance sign-off.

---

## Integration Flow

The planned integration flow begins when an appraiser enters a VIN into the Power Apps interface. Power Automate triggers the first RFC call (`Z_GET_VEHICLE_HEADER_BY_VIN`) to retrieve the vehicle header. The internal vehicle number from the header is then used to call the second RFC (`Z_GET_AFTERSALES_PROFILE_BY_INTVEHNO`). Both datasets are written to SharePoint and made available to the Copilot Studio agent and Power BI dashboards.

---

## Current Blockers

The primary blocker is IT/admin approval for the SAP ERP Connector configuration. This requires coordination with the SAP basis team and Power Platform administrators to establish the connection and authorize the RFC calls. The technical design is complete and ready for implementation once approval is granted.
