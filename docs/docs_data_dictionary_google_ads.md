# Data dictionary — Google Ads (portfolio case study)

## Files
- `data_raw/google_ads_daily_clicks_raw_cleaned.csv`  
  Source: your exported time-series chart (daily clicks). Cleaned to ISO date format.
- `data_seed/google_ads_daily_campaign_performance_extended_simulated.csv`  
  Purpose: extend the time range to ~3 months and add realistic marketing fields needed for analysis.

## Columns (extended simulated file)
- `date` — calendar date (YYYY-MM-DD)
- `campaign_name` — simulated campaign identifier (2 campaigns)
- `impressions` — simulated daily impressions
- `clicks` — daily clicks (real where available; simulated for the extended period)
- `cost` — simulated daily cost in account currency units (currency not enforced)
- `conversions` — kept at 0 (on-site purchases will be simulated separately in orders/events tables)

## Notes
- Real input only contains daily clicks and no campaign breakdown.
- The extended file preserves the overall click pattern and adds typical marketing metrics (impressions, cost) required to compute CTR/CPC/ROAS in later steps.
