# E-commerce Funnel & Revenue Analytics (SQL Case Study)

This project demonstrates how I design an analytics-ready dataset and use SQL to answer business questions for a digital product store.

## Business goal
Understand where conversion drops in the funnel (Ads → Sessions → Events → Orders) and identify opportunities to improve revenue efficiency.

## Inside the project
- Dimensional data model (products, campaigns, customers, dates)
- Event-based funnel analytics (view → add_to_cart → checkout → purchase)
- Campaign performance metrics (spend, CTR/CPC, ROAS)
- Product & bundle performance analysis (AOV, attach rate)
- Segmentation (RFM) and cohort-style views (optional)

## Data notes
- Google Ads spend data is based on real export (impressions/clicks/cost).
- Orders and on-site events are simulated for portfolio purposes (assumptions documented).

## Tech stack
SQL (PostgreSQL or SQLite), CSV seeds, clear documentation in /docs.

## Repository structure
See folder layout below.

Google Ads clicks are based on a real export (daily time series).
Impressions and cost are simulated in an extended dataset to enable time-series and performance analysis.
