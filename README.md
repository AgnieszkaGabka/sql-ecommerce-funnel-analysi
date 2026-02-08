# The Excellence Lab — Marketing Performance Analytics (SQL Portfolio Project)

## Overview
This project simulates a marketing analytics workflow for an e-commerce-style digital products store (The Excellence Lab).
The goal is to demonstrate end-to-end analytical work:
- designing a relational data model
- loading and transforming data
- building an analytical layer (views)
- producing KPI queries and data validation checks
- translating results into business insights

## Business Questions
1. Which campaigns are the most efficient (ROAS / CPA / CPC / CTR)?
2. Which products generate the highest simulated revenue?
3. How do cost and performance change over time?
4. What would be the next recommended actions (scale / pause / reallocate)?

## Data Sources
- Google Ads exports (base signal: impressions, clicks, cost)
- Simulated extensions:
  - extended time range
  - simulated conversions (for analysis completeness)
  - simulated revenue attribution via campaign → product mapping

> Note: Conversions and revenue are simulated for portfolio purposes and clearly marked as such.

## Data Model (Star Schema)
Core tables:
- `staging_google_ads` — raw / semi-clean marketing export
- `dim_date` — calendar dimension
- `dim_campaign` — campaign dimension
- `dim_product` — product catalog (9 products + 7 bundles)
- `fact_ad_spend` — daily spend & performance by campaign
- `bridge_campaign_product` — mapping campaigns → promoted products (with allocation weights)

Analytical layer:
- `vw_campaign_product_performance` — unified view combining spend + product pricing + simulated revenue

## Repository Structure
- `sql/ddl/` — schema definitions (CREATE TABLE)
- `sql/load/` — seeding and loading scripts (INSERT, ETL steps)
- `sql/analytics/` — analytical view, KPI queries, validation checks
- `data_seed/` — CSV seed files (e.g., product catalog)

## How to Run Locally
Requirements:
- Docker Desktop
- DBeaver (or any SQL client)

Steps:
1. Start containers:
   - `docker compose up -d`
2. Connect to PostgreSQL via DBeaver (localhost:5432)
3. Execute scripts in order:
   - `sql/ddl/` (schema)
   - `sql/load/` (seed + load)
   - `sql/analytics/040_vw_campaign_product_performance.sql`
4. Run analysis queries:
   - `sql/analytics/041_kpi_queries.sql`
5. Run data checks:
   - `sql/analytics/050_data_validation_checks.sql`

## Key Metrics Produced
- CTR, CPC, CPA
- Simulated revenue and ROAS (conversion-based, attributed via product mapping)
- Campaign ranking and product ranking
- Daily trends (cost vs revenue)

## Notes on Assumptions
- Conversions are simulated to enable meaningful KPI analysis.
- Campaign → product attribution is simulated using `bridge_campaign_product`.
- This approach mirrors real-world situations where tracking is incomplete and assumptions must be explicit.

## Next Steps (Planned)
- Write a structured analytical report with risks, limitations, correlations, and recommendations (TCBA-aligned).
- Add a concise PDF portfolio version of the report for CV attachments.
- 
## Business Analysis Report
The project includes a full Business Analysis report (PDF) summarizing the analytical approach, key findings, assumptions, and decision implications.
The report is intended for non-technical stakeholders and demonstrates how analytical insights were translated into business-relevant conclusions.
