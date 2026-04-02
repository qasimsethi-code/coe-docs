# Pending Tasks & Roadmap

This page provides a prioritized view of all pending tasks, active blockers, and planned future work. Tasks are organized by priority level to guide execution sequencing.

---

## Priority Legend

| Priority | Meaning |
|---|---|
| :red_circle: **Immediate** | Must be addressed now — blocks other work or has direct operational impact |
| :orange_circle: **High** | Important and time-sensitive — should be resolved within the current sprint |
| :yellow_circle: **Medium** | Significant but not blocking — target for completion within the current quarter |
| :green_circle: **Planned** | Future work with defined scope — scheduled for upcoming quarters |

---

## Task Backlog

### :red_circle: Immediate Priority

| Task | Details | Dependencies |
|---|---|---|
| **Build Phase 2 of PAD flow** | For Each loop → click Enquiry ID → Pictures tab → download ZIP → close modal | Phase 1 complete |
| **Finalize VIN scan flow** | Fully automated VIN scan integrating MOI + Autorola logic | Architecture defined |

### :orange_circle: High Priority

| Task | Details | Dependencies |
|---|---|---|
| **Resolve GitHub Codespaces tunnel relay block** | Workaround: browser-based access or local clone | GitHub infrastructure |
| **Submit IT helpdesk request for Entra ID App Registration** | Admin consent required via itservices.symphonysummit.com | IT tenant admin approval |

### :yellow_circle: Medium Priority

| Task | Details | Dependencies |
|---|---|---|
| **Resolve Google Custom Search API 403 error** | Error appeared after billing activation | Google API billing/configuration |
| **Complete SAP P01 RFC implementation** | Via Power Automate SAP ERP Connector | IT/admin approval for connector |
| **OneDrive ZIP deployment reliability** | Ensure consistent ZIP build pack deployment | OneDrive sync stability |
| **Vehicle Valuation Workflow vNext** | Next version of the flagship workflow | Multiple component updates |
| **Power BI analytics layer** | Analytics over appraisal data for leadership dashboards | Data pipeline completion |

### :green_circle: Planned

| Task | Details | Target |
|---|---|---|
| **Phase 3 Autorola: pricing decision injection** | Inject ACQUIRE/NEGOTIATE/DECLINE decisions back into Autorola | After Phase 2 completion |
| **Copilot Studio ↔ Claude API live bridge** | Deploy and harden the agent bridge with governance + explainability | After Foundry approval |
| **Documentation site formalization** | MkDocs / GitHub Pages deployment and executive demo refinement | Current quarter |

---

## Blocker Tracker

Active blockers that are preventing progress on key initiatives.

| Blocker | Affected Project(s) | Required Action | Owner |
|---|---|---|---|
| Entra ID App Registration consent | PnP.PowerShell, SharePoint schema | IT helpdesk request | IT Admin |
| GitHub Codespaces tunnel relay | Development workflow | Browser-based workaround or local clone | GitHub / IT |
| Google Custom Search API 403 | af-pricing-agent | Billing/configuration review | Qasim |
| SAP ERP Connector approval | SAP P01 Integration | IT/admin coordination | IT / SAP Team |

---

## Completed Milestones

For reference, the following milestones have been successfully completed.

| Milestone | Completion |
|---|---|
| Vehicle Valuation Workflow v1.0–v1.7+ | :white_check_mark: Active |
| Semi-automated IA pricing workflow | :white_check_mark: Daily use |
| Autorola PAD Phase 1 (login + extraction) | :white_check_mark: Working |
| DSR Excel consolidation script | :white_check_mark: Built |
| Dubizzle live scraping | :white_check_mark: Working |
| af-pricing-agent PWA deployment | :white_check_mark: Installed |
| Dual-Agent Architecture validation | :white_check_mark: Confirmed |
| IDP 2026 creation and versioning | :white_check_mark: Complete |
| PnP.PowerShell installation (module only) | :white_check_mark: Installed |
| Appraisal templates and quality standards | :white_check_mark: Authored |
