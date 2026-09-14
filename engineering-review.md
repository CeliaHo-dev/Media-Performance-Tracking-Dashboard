# Engineering review and next improvements

This portfolio edition intentionally preserves the working Apps Script architecture while documenting where I would take the system next.

## Strengths in the current design

- Centralized column mapping for heterogeneous Facebook/TikTok schemas.
- Server-side filtering rather than shipping raw rows to the browser.
- Reusable group aggregation helpers.
- Previous-period comparison logic with equal-length date windows.
- Script-level cache versioning for inexpensive global invalidation.
- Clear split between analytics logic and the visualization layer.
- Installable triggers plus a scheduled fallback.

## Production improvements I would make next

### 1. Avoid repeated full-sheet reads

`getSheetData_()` currently loads the entire used range. A cache miss can trigger several reads, especially when previous-period data is requested. I would cache normalized rows once per version or move the data to BigQuery / a relational database for larger workloads.

### 2. Use hashed cache keys

The current implementation truncates long cache keys to stay under Apps Script limits. A stronger approach is to hash the serialized filters (for example SHA-256) and use the digest in the cache key, eliminating possible prefix collisions.

### 3. Separate data access from analytics services

Introduce repository/service modules such as `FacebookRepository`, `TikTokRepository`, and `MetricsService` so aggregation logic can be unit-tested independently from `SpreadsheetApp`.

### 4. Validate the input contract

Add explicit header/schema validation and return a descriptive setup error if required fields are missing or renamed.

### 5. Replace heuristic creative scoring

The Good/Average/Review rules are useful operationally, but a mature version would use minimum-volume thresholds, confidence intervals, objective-specific benchmarks, and possibly Bayesian/shrinkage estimates before ranking low-volume creatives.

### 6. Improve trigger observability

Add a lightweight log sheet or Cloud Logging fields for refresh duration, row count, cache hit/miss, and failures.

### 7. Clarify cross-platform KPI definitions

Avoid presenting platform-specific video events as directly equivalent. Maintain a metric dictionary and show exact definitions in the UI.

### 8. Add tests

The next technical step would be pure-function tests for date-window generation, deltas, grouping, KPI formulas, and filter behavior, using a JavaScript test runner outside Apps Script.
