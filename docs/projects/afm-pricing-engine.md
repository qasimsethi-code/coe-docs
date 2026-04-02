# AFM Pricing Engine & HTML Tools

!!! success "Built — 84 Vehicles Across 25 Brands"

---

## Overview

The AFM Pricing Engine & HTML Tools suite provides the analytical foundation for vehicle pricing decisions within the COE. This collection includes an Excel-based pricing engine, an interactive HTML pricing widget, and a data import hub — all designed to deliver fast, accurate pricing calculations grounded in current market data.

---

## Components

### AFM Pricing Engine v3.0

The AFM Pricing Engine is an Excel workbook that serves as the core calculation tool for vehicle valuations. It incorporates the AFM guidelines, margin schemes, and risk tier logic used across the COE's pricing operations.

### Interactive Pricing Widget

The Interactive Pricing Widget is an HTML tool featuring cascading dropdowns for Make, Model, Grade, and Year selection. Once a vehicle is selected, the widget provides live calculations for:

| Metric | Description |
|---|---|
| **SIV** | Standard Invoice Value |
| **GM** | Gross Margin calculation |
| **Risk** | Risk tier assessment |

The widget currently covers **84 vehicles across 25 brands**, providing comprehensive coverage of the most commonly appraised vehicles in the UAE market.

### Data Import Hub

The Data Import Hub is an HTML tool designed for refreshing stock data, AFM guidelines, and BYD matrix data on the client side. It uses **SheetJS** for client-side Excel file processing, enabling data updates without server-side infrastructure — an important consideration given corporate IT constraints.

---

## Technology

| Component | Technology |
|---|---|
| **Pricing Engine** | Microsoft Excel (workbook with formulas and macros) |
| **Pricing Widget** | HTML / CSS / JavaScript with cascading dropdowns |
| **Data Import Hub** | HTML / JavaScript / SheetJS |
| **Data Sources** | AFM guidelines, BYD matrix, stock data files |

---

## Usage

These tools are used daily by the pricing team to quickly calculate valuations, verify margin targets, and assess risk tiers. The client-side design ensures that the tools work offline and do not require network connectivity or server infrastructure, making them resilient and portable.
