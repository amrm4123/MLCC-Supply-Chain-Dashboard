# MLCC Supply Chain Dashboard

Interactive **Power BI dashboard** for analyzing the supply chain of **MLCC (Multilayer Ceramic Capacitor)** components — covering suppliers, subtier relationships, manufacturing locations, materials, and risk/tier classification. Built on a dedicated **star schema data model** prepared for BI consumption.

## Overview

The dashboard turns raw MLCC component and supplier data into decision-ready analytics:

- **Supplier & subtier coverage** — who supplies each MLCC series, across Tier 1, Tier 2 and subtier levels
- **Manufacturing locations** — where components and sub-components are actually produced
- **Risk classification** — component risk dimensions to support obsolescence and supply continuity analysis
- **Material & series breakdown** — Murata MLCC Class II series and their supply chain attributes
- **Supply chain tree paths** — full subtier path tracing from component down to raw-material suppliers

## Data Model (Star Schema)

`model/MLCC_Star_Schema_Model.xlsx` implements a classic star schema:

**Fact tables**

| Table | Contents |
|---|---|
| `Fact_DataSummary` | Aggregated supply chain measures per supplier/component/location combination |
| `Fact_SubtierPath` | Full subtier tree paths for tracing multi-level supplier dependencies |

**Dimension tables**

| Table | Contents |
|---|---|
| `Dim_MLCCSupplier` | Tier-1 MLCC manufacturers/suppliers |
| `Dim_SubtierSupplier` | Subtier (Tier 2+) suppliers |
| `Dim_Material` | Materials and component series attributes |
| `Dim_Country` | Country / geography dimension |
| `Dim_Risk` | Risk classification dimension |
| `Dim_Tier` | Supply chain tier dimension |

## Repository Structure

```
├── MLCC Dashboard.pbix                          # Power BI dashboard (open with Power BI Desktop)
├── model/
│   └── MLCC_Star_Schema_Model.xlsx              # Star schema model (facts + dimensions)\
└── docs/
    └── Supply Chain Intelligence Platform.docx  # Related supply chain intelligence platform design notes
```

## Tools

- **Power BI Desktop** — dashboard development and visualization
- **Excel (Power Query / data modeling)** — source data preparation and star schema authoring
- **Dimensional modeling** — star schema design (facts, dimensions, surrogate relationships)

## Getting Started

1. Clone the repository
2. Open `MLCC Dashboard.pbix` in **Power BI Desktop**
3. If prompted for data sources, point to the files under `data/` and `model/`
4. Explore the report pages: supplier overview, subtier paths, location analysis, and risk views

## Author

**Amr Al-Kayal** — [GitHub](https://github.com/amrm4123)
