# Portfolio positioning

## GitHub subtitle

**Automated multi-platform media analytics dashboard built with Google Apps Script, JavaScript, Google Sheets, and Chart.js.**

## CV bullet — concise

Built an automated Facebook/TikTok performance analytics web app in Google Apps Script, standardizing platform data from Google Sheets into interactive KPI, trend, objective, brand, and creative-level views with scheduled refresh and response caching.

## CV bullet — technical

Designed a Google Apps Script analytics layer over normalized advertising data, implementing schema mapping, server-side filters, grouped aggregations, KPI calculations, prior-period comparison, versioned CacheService responses, installable triggers, and Chart.js dashboards.

## SOP / MSc application framing

I moved beyond manually consuming campaign reports by building an internal analytics application that transformed heterogeneous platform data into a consistent decision layer. The project required me to define a data model, implement aggregation and metric logic, automate refresh behavior, and design interactive views for non-technical stakeholders. It strengthened my interest in business analytics and information systems because the core challenge was not visualization alone; it was designing the data and process layer that made reliable analysis reusable.

## Interview explanation

**Problem:** cross-platform performance reporting required repeated manual consolidation and made comparable analysis slow.

**Approach:** normalize the raw platform exports into two stable sheet schemas, create Apps Script services for filtering and aggregation, cache responses, invalidate cache automatically when data changes, and render role-friendly views in an HTML web app.

**Trade-off:** Google Sheets + Apps Script was fast to deploy and easy for business users, but it is not the final architecture for very large datasets. For scale, I would move the data layer to a warehouse and keep the dashboard/API boundary.

## Skills to tag

`Google Apps Script` · `JavaScript` · `Data Transformation` · `Business Analytics` · `Marketing Analytics` · `ETL / ELT Concepts` · `Google Sheets` · `Chart.js` · `Data Visualization` · `Caching` · `Automation` · `KPI Design`
