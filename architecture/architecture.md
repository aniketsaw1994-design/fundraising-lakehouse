# Architecture

## Data flow
1. Python generates synthetic datasets (donors, campaigns, daily donations, touchpoints)
2. Ingest to Bronze (raw, append-only)
3. Transform to Silver (clean, typed, deduped, conformed)
4. Publish Gold marts (star schema)
5. Serve to Power BI via SQL endpoint
6. Dashboards: Exec overview, retention cohorts, campaign ROI, recurring giving

## Diagram (v1)
[Data Generator]
      |
      v
[Bronze Lakehouse]
      |
      v
[Silver Cleaned]
      |
      v
[Gold Star Schema] ---> [SQL Endpoint] ---> [Power BI Semantic Model] ---> [Dashboards/Insights]
