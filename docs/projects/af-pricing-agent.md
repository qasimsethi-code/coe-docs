# af-pricing-agent & vehicle-pricing-widget

!!! success "Active — PWA Installed as Desktop Application"

---

## Overview

The af-pricing-agent and vehicle-pricing-widget form an AI-powered vehicle appraisal tool built with Node.js and React. The application provides a modern, interactive interface for pricing analysis, incorporating UAE-specific pricing logic within the Claude system prompt and real-time market data from Dubizzle via a Puppeteer-based scraper.

---

## Architecture

| Component | Technology | Description |
|---|---|---|
| **Frontend** | React / Vite | Interactive pricing widget with Trade-In tab |
| **Backend** | Express.js (port 3001) | Proxy backend for API calls and scraping |
| **AI Engine** | Anthropic Claude API | UAE-specific pricing logic via system prompt |
| **Market Scraper** | Puppeteer | Live Dubizzle scraping for trade-in benchmarking |
| **Deployment** | PWA | Installed as standalone desktop application |

---

## Key Features

The application delivers several capabilities that directly support the appraisal workflow.

**UAE-Specific Pricing Logic** is embedded in the Claude system prompt, ensuring that all AI-generated valuations account for regional market dynamics, GCC/non-GCC specifications, and local dealer pricing patterns.

**Live Market Data** is sourced from Dubizzle through a Puppeteer-based scraper, providing real-time retail listing prices for comparison during the appraisal process. The Trade-In tab has been confirmed working and provides immediate access to benchmarking data.

**Progressive Web App (PWA)** deployment means the application can be installed as a standalone desktop application, providing a native-like experience without requiring traditional software installation — an important consideration given corporate IT constraints.

---

## Known Issues

The Google Custom Search API was configured to supplement the Dubizzle scraper with broader market data. However, following billing activation, the API returns a 403 error. Resolution of this issue is tracked as a medium-priority task on the [Roadmap](../roadmap.md).

---

## Repository

The project is maintained in the `af-pricing-agent` and `vehicle-pricing-widget` repositories on GitHub under the `qasimsethi-code` account.
