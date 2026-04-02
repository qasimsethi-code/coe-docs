# Appraisal Engine Bot

!!! success "v1.0+ — Copilot Studio Agent with Built-in Explainability"

---

## Overview

The Appraisal Engine Bot is a Copilot Studio agent (v1.0+) that provides guided appraisal logic with built-in explainability. It serves as the conversational interface for the Vehicle Valuation Workflow, enabling appraisers to interact with the pricing system through natural language while maintaining full governance compliance.

---

## Key Capabilities

| Capability | Description |
|---|---|
| **Guided Appraisal Logic** | Walks appraisers through the valuation process step by step |
| **Built-in Explainability** | Clarifies the reasoning behind specific valuations and pricing decisions |
| **Risk Flags** | Identifies and surfaces risk indicators (structural accidents, non-GCC specs, high-mileage) |
| **Condition Interpretation** | Translates inspection data into pricing adjustments with clear justification |
| **Governance-Safe Responses** | Operates strictly within M365 compliance boundaries |

---

## Design Principles

The Appraisal Engine Bot is designed with a zero-hallucination mandate. Every response must be grounded in actual data — whether from SAP, Autorola, market intelligence, or the appraisal template. The bot does not speculate or generate unsupported pricing recommendations.

**M365 Compliance** is enforced at every level. The bot operates within Copilot Studio's governance framework, ensuring that all interactions are logged, auditable, and compliant with Al-Futtaim's corporate policies.

**Explainability** is not optional. When the bot provides a valuation or recommendation, it must also provide the reasoning chain — which data sources were consulted, what adjustments were applied, and why the final figure was reached. This transparency is critical for building trust with appraisers and leadership.

---

## Integration Points

The Appraisal Engine Bot integrates with the broader Vehicle Valuation Workflow ecosystem.

| System | Integration |
|---|---|
| **SharePoint** | Reads and writes appraisal records |
| **Power Automate** | Triggers and receives workflow orchestration events |
| **Power BI** | Surfaces analytics and dashboards within conversations |
| **SAP P01** | Accesses vehicle and aftersales data (planned) |

---

## Current Status

The bot is at version 1.0+ and is operational within the Copilot Studio environment. Ongoing development focuses on expanding its knowledge base, improving condition interpretation accuracy, and preparing for SAP P01 data integration.
