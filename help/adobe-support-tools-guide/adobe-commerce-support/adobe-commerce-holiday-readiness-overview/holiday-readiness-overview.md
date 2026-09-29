---
title: Adobe Commerce holiday readiness overview
description: Executive-level guidance for preparing Adobe Commerce on cloud infrastructure environments for high-traffic events such as the holiday season.
feature-set: Commerce
feature: Support
solution: Commerce
role: Developer, Admin, Leader
TQID: 'https://experienceleague.adobe.com/63svzoaJbKTgiO3iJR3iCyr4-slOLmt4QaVT2Y--NYI'
product_v2:
  - id: eadea719-cf89-469b-a6fd-a236a7138047
    internal-label: Commerce
feature_v2:
  - id: cdfd3bc1-dc23-5cf0-b965-d3c0c55cde67
    internal-label: Best Practices
  - id: dac87252-6066-4d6e-a9d2-f6d84c323de7
    internal-label: Configuration
  - id: e8818fe6-9c8b-4bc0-9ef8-377a10b7bc75
    internal-label: Architecture
subfeature_v2:
  - id: f8ddfd3b-6194-46e8-a176-0e918039be56
    internal-label: Cloud architecture
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
---

# Adobe Commerce holiday readiness overview

This playbook provides executive-level guidance for preparing Adobe Commerce on Cloud Infrastructure environments for high-traffic events, such as the holiday season. It consolidates technical recommendations into five strategic focus areas:

- Performance optimization
- Best Practices and Stability
- Monitoring and observability
- Scalability and capacity planning
- Operational readiness

These focus areas help ensure your platform remains stable, secure, and performant under peak load.

## Performance Optimization

* Optimize Fastly Request Caching: Normalize your promotional tracking parameters, confirm your landing pages are cacheable, and use GraphQL GET for PWA or headless storefronts to raise your Fastly cache hit ratio.
* Enable Fastly IO: Turn on Fastly Image Optimization and Deep IO so image transformations run at the CDN edge instead of the origin, cutting page render time on image-heavy storefronts.
* Implement Redis L2 Cache: Store cache data locally on each web node with the `REDIS_BACKEND` variable to cut latency and reduce network calls to Redis.
* Enable MySQL and Redis Slave Connections: Route read-heavy queries to replica nodes with `MYSQL_USE_SLAVE_CONNECTION` and `REDIS_USE_SLAVE_CONNECTION` so the master databases aren't the bottleneck under load.
* Enable Asynchronous Order and Email Processing: Queue order placement, order-data grid updates, and checkout emails to run in the background across three separate settings, so checkout stays fast under high order volume.
* Configure Indexers for Update on Schedule: Move indexers from Update on Save to the cron-driven Update on Schedule mode to avoid locking during frequent catalog updates—except for the customer_grid indexer.
* Consider Scaled (Split) Architecture: If tuning and code-level fixes still leave CPU maxed out under load, move to a six-node split-tier setup that scales web and database nodes independently.

For detailed steps for each of those performance optimization recommendations, refer to [Adobe Commerce holiday readiness > Performance optimization](/help/adobe-support-tools-guide/adobe-commerce-support/adobe-commerce-holiday-readiness-overview/performance-optimization.md).

## Best Practices and Stability

* Upgrade to Latest Adobe Commerce Version: Stay on a supported release to keep the security fixes and performance improvements Adobe ships in each version.
* Install Latest ECE-Tools and Quality Patch Tool (QPT): Update ece-tools with its dependencies and confirm the applicable Quality Patches Tool fixes are applied, for both cloud and on-premises installations.
* Review and Clean Log Files: Remove debug logs and monitor recurring errors to prevent disk overuse and improve log visibility.
* Monitor Disk Size Growth: Keep the shared-files and database volumes under 70% usage so storage growth doesn't trigger an outage.
* Review Slow Database Queries: Use APM tooling and the MySQL slow query log to find and fix costly queries before they compound under peak traffic.
* Configure Cron Jobs Correctly: Confirm cron runs every minute under the correct user, since every async operation in Commerce depends on it.
* Optimize Client-Side Settings: Turn on CSS, JavaScript, and HTML minification and bundling to speed up storefront load times.

For detailed steps for each of those best practices and stability recommendations, refer to [Adobe Commerce holiday readiness > Best Practices and Stability](/help/adobe-support-tools-guide/adobe-commerce-support/adobe-commerce-holiday-readiness-overview/best-practices-stability.md).

## Monitoring and Observability

* Monitor Traffic with New Relic: Use Fastly logs streaming into New Relic to spot traffic anomalies, abusive IPs, malicious requests targeting endpoints like payment, and device/browser trends.
* Customize New Relic Alerts: Set up your own NRQL-based alerts for unusual traffic, slow GraphQL queries, or rising error rates, on top of Adobe's managed alerts.
* Track Apdex Score: Watch the Apdex score (target ≥ 0.85) to keep backend and frontend response times in a range users consider satisfactory.
* Review Support Insights (SWAT Report): Run a SWAT report before and after peak events to identify system-level risks and improvement areas.

For detailed steps for each of those monitoring and observability recommendations, refer to [Adobe Commerce holiday readiness > Monitoring and Observability](/help/adobe-support-tools-guide/adobe-commerce-support/adobe-commerce-holiday-readiness-overview/monitoring-observability.md).

## Scalability and Capacity Planning

* Plan Cluster Upsize Early: Request a temporary compute upsize from Adobe Support at least 10 business days before a major promotion.
* Enable Fastly Origin Shielding: Route uncached requests through a Shield POP near your origin so fewer requests hit the origin server directly.
* Conduct Load and Failover Tests: Test load and recovery scenarios ahead of major campaigns to confirm your scaling and rollback plans actually hold up.

For detailed steps for each of those scalability and capacity planning recommendations, refer to [Adobe Commerce holiday readiness > Scalability and Capacity Planning](/help/adobe-support-tools-guide/adobe-commerce-holiday-readiness-overview/adobe-commerce-support/scalability-capacity-planning.md).

## Operational Readiness

* Apply All Security and Performance Patches: Finish all patching before code freeze so deployments aren't disrupted later.
* Run Pre-Holiday Health Checks: Test backups, cron health, and cache warmup scripts so operations run smoothly under load.
* Establish Monitoring Playbooks: Document alert thresholds, escalation paths, and 24x7 contacts so the team can respond fast during peak.
* Document Rollback Plans: Keep versioned rollback strategies ready so you can recover quickly from a bad deployment.

For detailed steps for each of those operational readiness recommendations, refer to [Adobe Commerce holiday readiness > Scalability and Operational Readiness](/help/adobe-support-tools-guide/adobe-commerce-support/adobe-commerce-holiday-readiness-overview/operational-readiness.md).
