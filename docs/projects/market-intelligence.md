# Market Intelligence & Data Assets

!!! success "Active — Critical Data Assets Created and Shared"

---

## Overview

The Market Intelligence & Data Assets project encompasses the creation, curation, and distribution of critical pricing data that informs every valuation decision within the COE. Qasim has built a comprehensive data ecosystem that combines transactional pricing outcomes, scraped retail listings, and OEM residual value settings into a unified intelligence layer.

---

## Key Data Assets

| Asset | Description | Coverage |
|---|---|---|
| `appraisal_raw_data (29)` | Transactional pricing outcomes from completed appraisals | Historical pricing decisions and outcomes |
| `combined_car_sites_240723` | Scraped retail listings from UAE market platforms | Multi-platform retail pricing snapshot |
| **OEM RV Setting Files** | Residual value settings by manufacturer | Toyota, Lexus, Honda, Volvo, BEV, CJDR |

---

## Market Intelligence Sources

The data assets are sourced from a comprehensive set of UAE market platforms, providing broad coverage of the retail and wholesale landscape.

| Platform | Type | Data Captured |
|---|---|---|
| **Dubizzle** | Retail listings | Asking prices, listing age, seller type |
| **Dubicars** | Retail listings | Dealer and private pricing |
| **Cars24** | Retail / Trade-in | Instant pricing estimates |
| **YallaMotor** | Retail listings | New and used pricing |
| **CarSwitch** | Retail listings | Inspected vehicle pricing |
| **Emirates Auction** | Auction results | Wholesale and salvage pricing |
| **Copart MEA** | Auction results | Salvage and export pricing |

---

## OEM Residual Value Files

The OEM RV setting files provide manufacturer-specific residual value curves that are essential for accurate depreciation modeling. These files cover the most commonly traded brands in the UAE market.

| Brand Group | Brands Covered |
|---|---|
| **Japanese** | Toyota, Lexus, Honda |
| **European** | Volvo |
| **Electric** | BEV (Battery Electric Vehicles) |
| **American** | CJDR (Chrysler, Jeep, Dodge, Ram) |

---

## Data Pipeline

The market intelligence pipeline follows a structured flow: raw data is collected from market platforms (via scraping or manual extraction), normalized into consistent formats, enriched with OEM RV data, and made available for consumption by the pricing tools, Power BI dashboards, and the Dual-Agent Architecture.

---

## Strategic Value

These data assets represent a significant competitive advantage for the COE. By maintaining a comprehensive, up-to-date view of the UAE used-car market, the pricing team can make faster, more accurate valuation decisions grounded in real market data rather than intuition or outdated benchmarks.
