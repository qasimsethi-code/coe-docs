# Architecture & Design

This page presents the system architecture of the COE's pricing and appraisal ecosystem, illustrating how all components connect and interact to deliver end-to-end vehicle valuation capabilities.

---

## System Architecture Overview

The following diagram shows the high-level architecture of the COE pricing ecosystem, including all major platforms, data flows, and integration points.

```mermaid
graph TB
    subgraph USER["👤 Appraiser Interface"]
        PA[Power Apps<br/>Appraiser UI]
        PWA[af-pricing-agent<br/>PWA Desktop App]
        CLI[COE CLI<br/>coe-cli.cjs]
    end

    subgraph AI_AGENTS["🤖 Dual-Agent Architecture"]
        CLAUDE[Anthropic Claude<br/>External Research Agent]
        COPILOT[Microsoft Copilot<br/>Internal Appraisal Agent]
        BOT[Appraisal Engine Bot<br/>Copilot Studio v1.0+]
    end

    subgraph POWER_PLATFORM["⚡ Power Platform"]
        PAUTO[Power Automate<br/>Cloud Orchestration]
        PAD[Power Automate Desktop<br/>Autorola Automation]
        PBI[Power BI<br/>Analytics & Dashboards]
    end

    subgraph DATA_LAYER["💾 Data & Storage"]
        SP[SharePoint<br/>Appraisal Records & Schema]
        OD[OneDrive<br/>ZIP Files & Build Packs]
        EXCEL[AFM Pricing Engine<br/>Excel v3.0]
    end

    subgraph EXTERNAL["🌐 External Systems"]
        SAP[SAP P01<br/>S/4HANA Vehicle Data]
        AUTO[Autorola<br/>Auction & Fleet Monitor]
        MOI[MOI System<br/>Accident Verification]
    end

    subgraph MARKET["📊 UAE Market Intelligence"]
        DUB[Dubizzle]
        DC[Dubicars]
        C24[Cars24]
        YM[YallaMotor]
        CS[CarSwitch]
        EA[Emirates Auction]
        COPART[Copart MEA]
    end

    %% User to Agents
    PA --> PAUTO
    PA --> BOT
    PWA --> CLAUDE
    CLI --> CLAUDE
    CLI --> COPILOT

    %% Agent flows
    CLAUDE --> |VIN Decode, Market<br/>Benchmark, MOI Check| COPILOT
    COPILOT --> |ACQUIRE / NEGOTIATE<br/>/ DECLINE + AED| PA

    %% Power Platform flows
    PAUTO --> SP
    PAUTO --> SAP
    PAD --> AUTO
    PBI --> SP

    %% Bot integrations
    BOT --> SP
    BOT --> PAUTO

    %% External data
    SAP -.-> |RFC: Vehicle Header<br/>& Aftersales Profile| PAUTO
    AUTO -.-> |Enquiry Queue<br/>& Fleet Data| PAD
    MOI -.-> |Accident History| CLAUDE

    %% Market data
    DUB -.-> CLAUDE
    DC -.-> CLAUDE
    C24 -.-> CLAUDE
    YM -.-> CLAUDE
    CS -.-> CLAUDE
    EA -.-> CLAUDE
    COPART -.-> CLAUDE
    DUB -.-> |Puppeteer Scraper| PWA

    %% Data layer connections
    SP --> PBI
    EXCEL --> PA
    OD --> PAD

    %% Styling
    classDef userNode fill:#e3f2fd,stroke:#1565c0,stroke-width:2px,color:#0d47a1
    classDef aiNode fill:#f3e5f5,stroke:#7b1fa2,stroke-width:2px,color:#4a148c
    classDef powerNode fill:#fff3e0,stroke:#e65100,stroke-width:2px,color:#bf360c
    classDef dataNode fill:#e8f5e9,stroke:#2e7d32,stroke-width:2px,color:#1b5e20
    classDef extNode fill:#fce4ec,stroke:#c62828,stroke-width:2px,color:#b71c1c
    classDef marketNode fill:#e0f7fa,stroke:#00838f,stroke-width:2px,color:#006064

    class PA,PWA,CLI userNode
    class CLAUDE,COPILOT,BOT aiNode
    class PAUTO,PAD,PBI powerNode
    class SP,OD,EXCEL dataNode
    class SAP,AUTO,MOI extNode
    class DUB,DC,C24,YM,CS,EA,COPART marketNode
```

---

## Architecture Layers

The system is organized into six distinct layers, each with a clear responsibility.

### Appraiser Interface Layer

This layer provides the user-facing touchpoints for the pricing team. **Power Apps** serves as the primary enterprise UI for the Vehicle Valuation Workflow. The **af-pricing-agent PWA** provides a lightweight, installable desktop tool for quick pricing lookups. The **COE CLI** enables command-line access to the Dual-Agent Architecture for power users.

### Dual-Agent Layer

The AI layer is built on a complementary two-agent model. **Claude** handles all external research — VIN decoding, UAE market benchmarking across seven platforms, MOI accident interpretation, and GCC/Non-GCC verification. **Microsoft Copilot** manages internal appraisal logic using SAP P01 data and Autorola comments to produce final trade-in decisions. The **Appraisal Engine Bot** in Copilot Studio provides a conversational interface with built-in explainability.

### Power Platform Layer

The orchestration layer leverages Microsoft's Power Platform. **Power Automate (Cloud)** handles workflow orchestration between SharePoint, SAP, and other services. **Power Automate Desktop** manages desktop-level automation for Autorola interactions. **Power BI** provides the analytics and dashboard layer for leadership reporting.

### Data & Storage Layer

**SharePoint** serves as the primary data architecture for appraisal records and governance data. **OneDrive** stores ZIP files, build packs, and deployment artifacts. The **AFM Pricing Engine** (Excel v3.0) provides the calculation backbone for margin and risk analysis.

### External Systems Layer

**SAP P01** (S/4HANA) provides vehicle header and aftersales profile data via RFC calls. **Autorola** supplies auction queue data and fleet intelligence. The **MOI System** provides accident verification data.

### Market Intelligence Layer

Seven UAE market platforms provide the retail and wholesale pricing data that grounds every valuation in current market reality.

---

## Data Flow Summary

The primary data flow follows this sequence:

1. **Vehicle Intake** — VIN entered via Power Apps or COE CLI
2. **External Research** — Claude queries market platforms, MOI, and performs VIN decoding
3. **Internal Analysis** — Copilot processes SAP data and Autorola comments
4. **Valuation** — Both agents produce independent pricing; results are cross-validated
5. **Decision** — Final ACQUIRE / NEGOTIATE / DECLINE recommendation with AED pricing
6. **Storage** — All data, decisions, and audit trails written to SharePoint
7. **Reporting** — Power BI dashboards surface analytics for leadership

---

## Design Principles

| Principle | Implementation |
|---|---|
| **Modularity** | Each component can be updated, tested, or rolled back independently |
| **Audit Readiness** | Every decision is logged with full reasoning chain |
| **Governance-First** | All data flows respect M365 and corporate compliance boundaries |
| **Manual Fallback** | Every automated path has a documented manual alternative |
| **Zero Hallucination** | AI agents are constrained to produce only data-grounded outputs |
| **Versioned Deployment** | Build packs are versioned (v1.0–v1.7+) for precise change tracking |
