# Architecture

## Runtime flow

1. Normalized Facebook and TikTok records are available in `RAW_FB` and `RAW_TT`.
2. `WebDashboard.gs` converts rows into named objects based on the header row.
3. User filters are applied server-side: brand, objective, campaign type, month, and custom date range.
4. Aggregation functions compute totals, grouped breakdowns, creative metrics, daily trends, and prior-period deltas.
5. The serialized response is cached by function + filter combination + cache version.
6. HTML pages call server functions through `google.script.run`.
7. Chart.js renders the returned data in the browser.
8. Scheduled/change triggers increment the cache version and update `LAST_UPDATED`.

## Why a cache version?

Apps Script `CacheService` does not provide a convenient way to delete every possible filter-specific key. Instead, responses are namespaced by a version stored in `PropertiesService`. Incrementing the version instantly makes all old keys unreachable and therefore stale.

## Separation of concerns

- `Config.gs`: deployment constants.
- `Router.gs`: page routing and web-app bootstrapping.
- `Triggers.gs`: refresh lifecycle.
- `WebDashboard.gs`: data access, filtering, aggregation, KPI calculations, and response serialization.
- `*.html`: presentation, interaction, charts, tables, and client-side filters.
- `DemoData.gs`: synthetic data only for the public portfolio edition.

## Upstream ingestion

The supplied source code does not contain Facebook Marketing API or TikTok Ads API extraction logic. Therefore this portfolio repository intentionally treats platform ingestion as an upstream dependency rather than claiming direct API integration.
