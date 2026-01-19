# Fundraising Analytics KPI Contract

## Global definitions
- New Donor: donor whose first-ever donation date is within the selected period
- Active Donor: donated in last N days (default N=90)
- Recurring Donor: donor with active recurring plan OR donation flagged recurring

## KPI list

### Total Donations
- Meaning: total donation amount in the selected period
- Grain: donation transaction
- Rule: SUM(FactDonation.amount)

### Donor Retention Rate (Monthly Cohort)
- Meaning: of donors first donating in month M, % donating again in month M+N
- Grain: cohort_month × activity_month
- Rule:
  - cohort_month = month(first_donation_date)
  - retained in month t if >=1 donation in month t
  - retention = retained / cohort_size

### Campaign ROI
- Meaning: profitability of campaign spend
- Rule: (AttributedDonations - CampaignCost) / CampaignCost
- Attribution v1: last-touch within 14 days (documented in FactTouchpoint)
