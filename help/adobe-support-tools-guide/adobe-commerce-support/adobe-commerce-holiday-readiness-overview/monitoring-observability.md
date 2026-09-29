---
title: Monitoring and observability
description: Monitoring and observability recommendations to help Adobe Commerce merchants prepare their environments for high-traffic events such as the holiday season.
feature-set: Commerce
feature: Support
solution: Commerce
role: Developer, Admin, Leader
product_v2:
  - id: eadea719-cf89-469b-a6fd-a236a7138047
    internal-label: Commerce
feature_v2:
  - id: 5a951749-fac9-5bc7-9a98-ebe4ff066437
    internal-label: Cloud
  - id: cdfd3bc1-dc23-5cf0-b965-d3c0c55cde67
    internal-label: Best Practices
  - id: ba9e5be9-7de1-4f71-a5d2-baead0e425ee
    internal-label: Security
  - id: 4239b8a6-e74f-567d-a7a5-b98b9ead0ea4
    internal-label: Observability
  - id: dac87252-6066-4d6e-a9d2-f6d84c323de7
    internal-label: Configuration
subfeature_v2:
  - id: 3c398179-d35a-51ba-b317-6c5b95feef5e
    internal-label: Logs
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
---

# Monitoring and observability

This section provides technical recommendations for monitoring Adobe Commerce environments to prepare for high-traffic events such as the holiday season.

>[!NOTE]
>
>Steps marked **(Cloud only)** apply to Commerce on cloud infrastructure. Most other recommendations also apply to on-premises deployments.

## Monitor traffic with New Relic (Cloud only) {#monitor-traffic-with-new-relic}

Adobe Commerce on cloud infrastructure includes a [!DNL New Relic] observability platform subscription, which seamlessly incorporates [!DNL Fastly] logs streaming into [!DNL New Relic] in near real-time. This integration lets you monitor your traffic patterns and trends in real time, so you can take corrective action.

Use these logs to:

* Identify countries your web requests originate from.
* Find abusive IP addresses or user agents crawling your site.
* Identify malicious traffic targeting specific endpoints, such as payment.
* Build reports on the device and browser types your customers use.

For example, monitor the source country of your traffic to confirm it reflects your promotions' and customers' geographic locations:

```sql
SELECT count(*) FROM Log
WHERE cache_status IS NOT NULL
AND project_id = '<YOUR_PROJECT_ID>'
AND (content_type LIKE 'text/html;%' or url LIKE '%graphql%' or url like '%rest%')
FACET geo_country_code
SINCE 7 days ago until today
```

Modify this query to suit your needs, segment it further, or turn it into a dashboard for centralized tracking. For details, see [New Relic log management](https://experienceleague.adobe.com/en/docs/commerce-on-cloud/user-guide/monitor/new-relic/log-management).

## Customize New Relic alerts (Cloud only) {#customize-new-relic-alerts}

In addition to the Managed Alerts set by Adobe Commerce Cloud, you can set a wide range of alerts and notifications for your platform during peak sale season—for example, notifying you of bot traffic or an increased response time on a GraphQL query. See [Managed alerts for Adobe Commerce](https://experienceleague.adobe.com/en/docs/commerce-operations/tools/managed-alerts-for-adobe-commerce/managed-alerts-for-magento-commerce) for the full list of built-in alerts.

[!DNL New Relic] Alerts and AI support NRQL-based query structures. Set up custom alerts from the [!DNL New Relic] dashboard under **[!UICONTROL Alerts & AI]**.

## Review Apdex score (Cloud only) {#review-apdex-score}

Apdex score measures user satisfaction with the response time of your web applications and services. You can review the Apdex score of your Adobe Commerce on cloud infrastructure using [!DNL New Relic].

An Apdex score ranges from 0 to 1. A score of 0 is the worst possible score, meaning 100% of response times were **frustrated**. A score of 1 is the best possible score, meaning 100% of response times were **satisfied**. [!DNL New Relic] reports both an App Server score, which reflects backend performance, and an End User score, which reflects client-side performance.

An Apdex score of 0.5 or lower warrants investigation. A score below 0.4 is considered an outage.

Along with Apdex, [!DNL New Relic] provides a range of stats to analyze performance issues on Adobe Commerce on cloud infrastructure. For steps, see [Troubleshoot performance using New Relic on Adobe Commerce](https://experienceleague.adobe.com/en/docs/commerce-knowledge-base/kb/troubleshooting/miscellaneous/troubleshoot-performance-using-new-relic-on-magento-commerce).

## Review support insights (SWAT report) {#review-support-insights-swat-report}

For a more detailed report on your environment, generate a Site-Wide Analysis Tool (SWAT) report. For more information about the SWAT tool, see [Site-Wide Analysis Tool](https://experienceleague.adobe.com/en/docs/commerce-operations/tools/site-wide-analysis-tool/intro).