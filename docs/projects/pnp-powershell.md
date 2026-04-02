# PnP.PowerShell Installation

!!! danger "Blocked — Entra ID App Registration Requires IT Tenant Admin Consent"

---

## Overview

The PnP.PowerShell Installation project involved installing PnP.PowerShell 3.1.0 on Qasim's corporate device to enable programmatic SharePoint management. The installation itself was successfully completed through a creative workaround, but the module's functionality is currently blocked pending IT tenant admin consent for Entra ID App Registration.

---

## Installation Approach

Corporate IT restrictions (GPOs, Intune/MDM policies, Zscaler) prevented standard installation methods. Qasim devised an innovative workaround to complete the installation.

| Step | Action |
|---|---|
| 1 | Split the PnP.PowerShell package into chunks small enough for upload |
| 2 | Push the chunks to a private GitHub repository |
| 3 | Reassemble the package on the corporate device via GitHub API base64 JSON responses |
| 4 | Install the reassembled module into the D:\ drive profile |

### Environment Details

| Parameter | Value |
|---|---|
| **Module Version** | PnP.PowerShell 3.1.0 |
| **PowerShell Version** | 7.6.0 |
| **Profile Location** | D:\ drive (corporate device) |
| **Installation Method** | GitHub API chunk reassembly |

---

## Current Blocker

While the module is installed, it cannot authenticate to SharePoint because Entra ID App Registration requires IT tenant admin consent. This consent must be granted by Al-Futtaim's IT administration team through the IT helpdesk portal (itservices.symphonysummit.com).

Until this consent is granted, the SharePoint schema for appraisal records — a key component of the Vehicle Valuation Workflow — cannot be deployed programmatically.

---

## Strategic Importance

PnP.PowerShell is essential for programmatic SharePoint management, which underpins the data architecture of the Vehicle Valuation Workflow. Once unblocked, it will enable automated creation and management of SharePoint lists, libraries, and schemas that store appraisal records, audit trails, and governance data.
