# Tools & Technologies

This page provides a comprehensive inventory of all platforms, languages, frameworks, and services used by Qasim Sethi in his COE operations and development work.

---

## Microsoft & Corporate Ecosystem

The Microsoft stack forms the backbone of Qasim's enterprise tooling, providing the governance, identity, and collaboration infrastructure required for corporate-grade solutions.

| Tool / Platform | Usage |
|---|---|
| **Microsoft 365** | Core productivity suite (Teams, Outlook, Word, Excel) |
| **Power Apps** | Appraiser user interface for the Vehicle Valuation Workflow |
| **Power Automate (Cloud)** | Workflow orchestration and integration |
| **Power Automate Desktop (PAD)** | Desktop-level automation (Autorola flows) |
| **Copilot (M365)** | AI-assisted productivity within the M365 ecosystem |
| **Copilot Studio** | Custom AI agent development (Appraisal Engine Bot) |
| **Power BI** | Analytics dashboards and reporting |
| **Tabular Editor (TE3)** | Power BI dataset modeling |
| **SharePoint** | Data architecture, document management, appraisal records |
| **Purview** | Interaction mitigation and compliance monitoring |
| **Intune / MDM** | Device management (corporate laptop) |
| **Azure API Management** | API gateway and governance |
| **Microsoft Entra ID** | Identity and access management |

---

## Automotive Platforms

These industry-specific platforms provide the market data, auction management, and vehicle intelligence that drive pricing decisions.

| Platform | Purpose |
|---|---|
| **Autorola** | Auction management and Fleet Monitor for wholesale intelligence |
| **SAP P01 (S/4HANA)** | Vehicle pricing, contracts, and opportunity IDs |
| **MOI System** | Ministry of Interior accident verification |
| **Dealer IA Systems** | Instant Auction dealer interfaces |

---

## UAE Market Intelligence Platforms

These platforms provide the retail and wholesale market data used for benchmarking and valuation.

| Platform | Data Type |
|---|---|
| **Dubizzle** | Retail listings (primary scraping target) |
| **Dubicars** | Retail listings |
| **Cars24** | Retail and trade-in pricing |
| **YallaMotor** | New and used vehicle pricing |
| **CarSwitch** | Inspected vehicle listings |
| **Emirates Auction** | Wholesale and salvage auction results |
| **Copart MEA** | Salvage and export auction results |

---

## Development & Scripting Stack

Qasim's personal development environment is built on Windows 11 and includes a comprehensive set of tools for scripting, development, and automation.

| Tool | Version / Notes |
|---|---|
| **Windows 11** | Primary development OS |
| **Git Bash** | Git operations and shell scripting |
| **Node.js** | v24 — JavaScript runtime |
| **npm** | Package management |
| **VS Code** | Primary code editor |
| **React** | Frontend framework (vehicle-pricing-widget) |
| **Vite** | Build tool for React projects |
| **Express.js** | Backend API server |
| **Puppeteer** | Browser automation and web scraping |
| **GitHub** | Source control and CI/CD |
| **Python** | Scripting and data processing |
| **PowerShell** | 5.1 and 7+ for system automation |
| **CMD / Batch** | Legacy scripting |
| **Registry (.reg) files** | System configuration management |

---

## AI & API Services

| Service | Usage |
|---|---|
| **Anthropic Claude API** | Pro + Claude Code — external research agent |
| **Claude Code CLI** | v2.1.78 — command-line AI development |
| **OpenAI** | LLM-assisted workflows |
| **Google Custom Search API** | Market data supplementation (currently 403 error) |
| **SheetJS** | Client-side Excel processing |
| **PnP.PowerShell** | SharePoint programmatic management (blocked on Entra consent) |

---

## Conceptual / Evaluated

| Tool | Status |
|---|---|
| **OpenClaw** | Conceptually considered as external AI agent |
| **Open Crawl** | Explicitly decided against integration |
