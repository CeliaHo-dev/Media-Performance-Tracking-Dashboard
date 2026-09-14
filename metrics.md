# Metrics

## Shared metrics

- **CPM** = `Spend / Impressions × 1,000`
- **CTR** = `Clicks / Impressions × 100`
- **CPC** = `Spend / Clicks`
- **Platform share** = `Platform spend / Total spend × 100`
- **Period delta** = `(Current − Previous) / |Previous| × 100`

## Facebook

- **CPE** = `Spend / Post Engagement`
- **VTR** = `ThruPlays / Impressions × 100`
- **Cost per ThruPlay** = `Spend / ThruPlays`
- **Cost per message** = `Spend / Messaging Conversations Started`
- **Cost per like** = `Spend / Page Likes`
- **Engagement rate** = `Post Engagement / Impressions × 100`

## TikTok

- **6s view rate** = `View 6s / Impressions × 100`
- **15s view rate** = `View 15s / Impressions × 100`
- **Cost per 6s view** = `Spend / View 6s`
- **Cost per 15s view** = `Spend / View 15s`
- **CPF** = `Spend / Paid Follows`

## Important comparability note

The overview combines Facebook `ThruPlays` and TikTok `View 6s` into a single convenience video-rate indicator. Those platform events are **not identical definitions**, so the combined value should be treated as a reporting proxy rather than a strict cross-platform apples-to-apples KPI. Platform-specific rates remain the more defensible metrics.

## Creative status

The front end labels creatives as **Good / Average / Review** using simple rules relative to the current filtered-set averages (for example, ±15% around average CPM/CTR and basic video-rate thresholds). This is a **heuristic**, not a statistical significance test or machine-learning model.
