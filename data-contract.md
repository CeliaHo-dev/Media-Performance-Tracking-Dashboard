# Data contract

The analytics service expects a normalized Google Sheets layer with the following headers.

## `RAW_FB`

| Field | Meaning |
|---|---|
| `Brand` | Brand/category identifier |
| `Objective Edited` | Standardized campaign objective |
| `Creative Name` | Creative identifier/name |
| `Camp Type` | Campaign classification |
| `Month` | Reporting month label |
| `Day` | Reporting date |
| `Amount Spent` | Spend in reporting currency |
| `Impressions` | Delivered impressions |
| `Link Clicks` | Link clicks |
| `Post Engagement` | Engagement events |
| `ThruPlays` | Facebook video completion proxy used in this implementation |
| `Messaging Conversations Started` | Started message conversations |
| `Page Likes` | Attributed page likes |

## `RAW_TT`

| Field | Meaning |
|---|---|
| `Brand` | Brand/category identifier |
| `Objective Edited` | Standardized campaign objective |
| `Creative Name` | Creative identifier/name |
| `Camp Type` | Campaign classification |
| `Month` | Reporting month label |
| `Day` | Reporting date |
| `Net cost` | Spend in reporting currency |
| `Impressions` | Delivered impressions |
| `Clicks` | Click events |
| `View 6s` | Six-second video views |
| `View 15s` | Fifteen-second video views |
| `Paid Follows` | Paid follows |

## Assumptions

- Header names must match exactly unless the column mapping in `WebDashboard.gs` is changed.
- Spend is displayed as Vietnamese đồng in the current UI.
- Dates are normalized to `yyyy-MM-dd` server-side.
- Empty numeric cells are treated as zero.
- The dashboard reads the entire used range of each raw sheet; for larger workloads, replace this storage layer with a database/warehouse.
