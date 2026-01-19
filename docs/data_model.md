# Data Model (Gold)

## Design approach
- Bronze/Silver/Gold lakehouse
- Gold is star schema for BI performance and clarity

## Dimensions

### DimDonor (grain: 1 row per donor)
Key: donor_id
Columns:
- donor_id (PK)
- signup_date
- acquisition_channel
- city/state/country
- age_band
- donor_segment (derived)

### DimCampaign (grain: 1 row per campaign)
Key: campaign_id
Columns:
- campaign_id (PK)
- campaign_name
- start_date, end_date
- campaign_cost
- objective

### DimChannel (grain: 1 row per channel)
Key: channel_id
Columns:
- channel_id (PK)
- channel_name (Email, Search, Social, Event, Referral)

### DimDate (grain: 1 row per date)
Key: date_key (YYYYMMDD)
Columns:
- date
- month_start, month_name, quarter, year

## Facts

### FactDonation (grain: 1 row per donation transaction)
Keys:
- donation_id (PK)
- donor_id (FK)
- campaign_id (FK)
- date_key (FK)
Columns:
- amount
- payment_method
- is_recurring (Y/N)
- source_system
- load_id, ingested_at (audit)

### FactTouchpoint (optional, grain: 1 row per donor interaction)
Keys:
- touchpoint_id (PK)
- donor_id (FK)
- campaign_id (FK)
- channel_id (FK)
- event_timestamp
Columns:
- touch_type (email_open/click/landing_visit)
- attributed_flag (for v1 attribution)
