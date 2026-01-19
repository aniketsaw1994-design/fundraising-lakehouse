
# Fundraising Lakehouse (Azure/Fabric) — Synthetic Data → ETL → Power BI

## Problem
Build an end-to-end fundraising analytics platform to measure donor retention, recurring giving, and campaign ROI.

## Architecture (high level)
Data Generator (Python) → Bronze (raw) → Silver (cleaned) → Gold (star schema marts) → Power BI semantic model → Insights

See: [architecture/architecture.md](architecture/architecture.md)

## KPIs
Definitions and calculation rules: [docs/business_kpis.md](docs/business_kpis.md)

## Data Model
Gold star schema + table grains: [docs/data_model.md](docs/data_model.md)

## How to Run
Step-by-step runbook: [docs/runbook.md](docs/runbook.md)

## Outputs
- Gold tables: FactDonation, DimDonor, DimCampaign, DimDate, DimChannel
- Power BI dashboard screenshots in: powerbi/screenshots/
