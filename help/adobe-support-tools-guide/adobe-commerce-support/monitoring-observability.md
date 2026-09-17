---
title: Monitoring & observability
description: Monitoring and observability recommendations to help Adobe Commerce merchants prepare their environments for high-traffic events such as the holiday season.
feature-set: Commerce
feature: Support
solution: Commerce
role: Developer, Admin, Leader
---

# Monitoring & observability

This section provides technical recommendations for preparing Adobe Commerce environments—both Commerce on cloud infrastructure and on-premises—for high-traffic events such as the holiday season.

>[!NOTE]
>
>Steps marked **(Cloud only)** apply to Commerce on cloud infrastructure, which includes a bundled [!DNL New Relic] Observability subscription. On-premises environments will need their own APM tooling to achieve equivalent monitoring.

## Monitor traffic with New Relic (Cloud only) {#monitor-traffic-with-new-relic}

Leverage integrated [!DNL Fastly] logs in [!DNL New Relic] to track real-time traffic patterns, countries of origin, and anomalies. See [Investigate performance](https://experienceleague.adobe.com/en/docs/commerce-on-cloud/user-guide/monitor/new-relic/investigate/investigate-performance). Adobe Commerce on cloud infrastructure includes a [!DNL New Relic] Observability subscription with [!DNL Fastly] logs streaming in near real time, which you can use to:

* Identify countries your web requests originate from.
* Find abusive IP addresses or user agents crawling your site.
* Identify malicious traffic targeting specific endpoints (for example, payment).
* Build reports on device and browser types.

Example NRQL query to monitor traffic by source country:

```sql
SELECT count(*) FROM Log
WHERE cache_status IS NOT NULL
AND project_id = '<YOUR_PROJECT_ID>'
AND (content_type LIKE 'text/html;%' OR url LIKE '%graphql%' OR url LIKE '%rest%')
FACET geo_country_code
SINCE 7 days ago UNTIL today
```

Queries can be modified, segmented further, and turned into dashboards for centralized tracking.

## Customize New Relic alerts (Cloud only) {#customize-new-relic-alerts}

Create NRQL-based alerts for unusual traffic patterns, slow GraphQL queries, or increased error rates. In addition to Adobe's managed alerts, you can configure your own alerts and notifications—for example, flagging bot traffic or elevated GraphQL response times—from the [!DNL New Relic] dashboard under **[!UICONTROL Alerts & AI]**.

## Track Apdex score (Cloud only) {#track-apdex-score}

Monitor user satisfaction levels (target ≥ 0.85) to balance backend and frontend performance, using the bundled [!DNL New Relic] subscription. Apdex measures user satisfaction with response time on a scale from 0 (worst—all responses **frustrated**) to 1 (best—all responses **satisfied**), and reports both an App Server score (backend performance) and an End User score (client-side performance). See [Troubleshoot performance using New Relic on Adobe Commerce](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-40830).

## Review Support Insights (SWAT report) {#review-support-insights-swat-report}

Run and review Support Insights (SWAT) reports before and after peak events to identify system-level risks and improvement areas. See [Site-Wide Analysis Tool](https://experienceleague.adobe.com/en/docs/commerce-operations/tools/site-wide-analysis-tool/intro).