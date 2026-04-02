# Workflow Automations

This page provides a comprehensive status tracker for all workflow automations owned or managed by Qasim Sethi within the COE. Automations are categorized by their current status: Built, In Progress, or Planned.

---

## Automation Status Overview

| Automation | Platform | Status |
|---|---|---|
| Semi-automated Instant Auction pricing workflow | Manual + Templates | :green_circle: Built / Actively Used |
| Structured valuation message templates for Teams & email | Templates | :green_circle: Built / Actively Used |
| Excel-driven RV & margin logic | Excel | :green_circle: Built / Actively Used |
| Power BI-ready datasets | Power BI | :green_circle: Built / Actively Used |
| DSR Excel consolidation | Python / Claude Code | :green_circle: Built |
| Dubizzle live scraping for trade-in benchmarking | Puppeteer / Node.js | :green_circle: Working |
| Autorola login → queue extraction | PAD | :green_circle: Working (Phase 1) |
| Per-enquiry ZIP photo download loop | PAD | :orange_circle: In Progress (Phase 2) |
| Full Power Platform orchestration | Power Platform | :orange_circle: In Progress |
| Pricing decision injection back to Autorola | PAD | :blue_circle: Planned (Phase 3) |
| SAP P01 data pull via Power Automate | SAP ERP Connector + RFC | :blue_circle: Designed, Pending IT |
| SharePoint schema for appraisal records | SharePoint / PnP | :red_circle: Blocked on Entra Consent |
| Copilot Studio ↔ Claude API bridge | Power Automate / Azure | :blue_circle: Planned |
| AI-assisted documentation | Claude / Copilot / MkDocs | :blue_circle: Planned |

---

## Status Definitions

| Status | Meaning |
|---|---|
| :green_circle: **Built / Actively Used** | Automation is complete and in daily or regular use |
| :green_circle: **Working** | Automation functions correctly but may not yet be in full production use |
| :orange_circle: **In Progress** | Automation is under active development |
| :blue_circle: **Planned / Designed** | Architecture is defined; implementation has not yet started or is pending approval |
| :red_circle: **Blocked** | Implementation is halted due to an external dependency or blocker |

---

## Automation Themes

Beyond the individual automations listed above, Qasim's automation strategy follows several overarching themes that guide design and implementation decisions.

**One-Click Installers** are preferred wherever possible, enabling rapid deployment of tools and configurations without manual setup steps. Silent install and uninstall capabilities are built into deployment scripts to support both initial rollout and clean removal.

**Validation and Rollback Scripts** accompany every automation, ensuring that changes can be verified after deployment and reversed if issues are detected. This rollback-friendly approach is essential in a corporate environment where unintended changes can have wide-reaching consequences.

**Manual-First Fallback** is a core design principle. When IT restrictions block automation (GPOs, Zscaler, MDM policies), every automated workflow has a documented manual procedure that can be followed as a fallback. This ensures that business operations are never dependent on a single automation path.

**Local-Only Testing** is enforced before any tenant-wide deployment. All automations are tested in isolation on Qasim's local environment before being promoted to production, minimizing the risk of disruption to other users or systems.
