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

- [Performance optimization](/help/adobe-support-tools-guide/adobe-commerce-support/performance-optimization.md)
- [Best Practices & Stability](/help/adobe-support-tools-guide/adobe-commerce-support/best-practices-stability.md)
- [Monitoring and observability](/help/adobe-support-tools-guide/adobe-commerce-support/monitoring-observability.md)
- [Scalability and capacity planning](/help/adobe-support-tools-guide/adobe-commerce-support/scalability-capacity-planning.md)
- [Operational readiness](/help/adobe-support-tools-guide/adobe-commerce-support/operational-readiness.md)

These focus areas help ensure your platform remains stable, secure, and performant under peak load.

## Performance Optimization

* [Optimize Fastly Request Caching](performance-optimization.md#optimize-fastly-request-caching): Normalize your promotional tracking parameters, confirm your landing pages are cacheable, and use GraphQL GET for PWA or headless storefronts to raise your Fastly cache hit ratio.
* [Enable Fastly IO](performance-optimization.md#enable-fastly-io): Turn on Fastly Image Optimization and Deep IO so image transformations run at the CDN edge instead of the origin, cutting page render time on image-heavy storefronts.
* [Implement Redis L2 Cache](performance-optimization.md#implement-redis-l2-cache): Store cache data locally on each web node with the `REDIS_BACKEND` variable to cut latency and reduce network calls to Redis.
* [Enable MySQL and Redis Slave Connections](performance-optimization.md#enable-mysql-and-redis-slave-connections): Route read-heavy queries to replica nodes with `MYSQL_USE_SLAVE_CONNECTION` and `REDIS_USE_SLAVE_CONNECTION` so the master databases aren't the bottleneck under load.
* [Enable Asynchronous Order and Email Processing](performance-optimization.md#enable-asynchronous-order-and-email-processing): Queue order placement, order-data grid updates, and checkout emails to run in the background across three separate settings, so checkout stays fast under high order volume.
* [Configure Indexers for Update on Schedule](performance-optimization.md#configure-indexers-for-update-on-schedule): Move indexers from Update on Save to the cron-driven Update on Schedule mode to avoid locking during frequent catalog updates—except for the customer_grid indexer.
* [Consider Scaled (Split) Architecture](performance-optimization.md#consider-scaled-split-architecture): If tuning and code-level fixes still leave CPU maxed out under load, move to a six-node split-tier setup that scales web and database nodes independently.
For detailed steps for each of those performance optimization recommendations, refer to [Adobe Commerce holiday readiness > Performance optimization](performance-optimization.md)
## 2. Best Practices & Stability

* [Upgrade to Latest Adobe Commerce Version](best-practices-stability.md#upgrade-to-latest-adobe-commerce-version): Stay on a supported release to keep the security fixes and performance improvements Adobe ships in each version.
* [Install Latest ECE-Tools and Quality Patch Tool (QPT)](best-practices-stability.md#install-latest-ece-tools-and-quality-patch-tool-qpt): Update ece-tools with its dependencies and confirm the applicable Quality Patches Tool fixes are applied, for both cloud and on-premises installations.
* [Review and Clean Log Files](best-practices-stability.md#review-and-clean-log-files): Remove debug logs and monitor recurring errors to prevent disk overuse and improve log visibility.
* [Monitor Disk Size Growth](best-practices-stability.md#monitor-disk-size-growth): Keep the shared-files and database volumes under 70% usage so storage growth doesn't trigger an outage.
* [Review Slow Database Queries](best-practices-stability.md#review-slow-database-queries): Use APM tooling and the MySQL slow query log to find and fix costly queries before they compound under peak traffic.
* [Configure Cron Jobs Correctly](best-practices-stability.md#configure-cron-jobs-correctly): Confirm cron runs every minute under the correct user, since every async operation in Commerce depends on it.
* [Optimize Client-Side Settings](best-practices-stability.md#optimize-client-side-settings): Turn on CSS, JavaScript, and HTML minification and bundling to speed up storefront load times.

## 3. Monitoring & Observability

* [Monitor Traffic with New Relic](monitoring-observability.md#monitor-traffic-with-new-relic): Use Fastly logs streaming into New Relic to spot traffic anomalies, abusive IPs, malicious requests targeting endpoints like payment, and device/browser trends.
* [Customize New Relic Alerts](monitoring-observability.md#customize-new-relic-alerts): Set up your own NRQL-based alerts for unusual traffic, slow GraphQL queries, or rising error rates, on top of Adobe's managed alerts.
* [Track Apdex Score](monitoring-observability.md#track-apdex-score): Watch the Apdex score (target ≥ 0.85) to keep backend and frontend response times in a range users consider satisfactory.
* [Review Support Insights (SWAT Report)](monitoring-observability.md#review-support-insights-swat-report): Run a SWAT report before and after peak events to identify system-level risks and improvement areas.

## 4. Scalability & Capacity Planning

* [Plan Cluster Upsize Early](scalability-capacity-planning.md#plan-cluster-upsize-early): Request a temporary compute upsize from Adobe Support at least 10 business days before a major promotion.
* [Enable Fastly Origin Shielding](scalability-capacity-planning.md#enable-fastly-origin-shielding): Route uncached requests through a Shield POP near your origin so fewer requests hit the origin server directly.
* [Conduct Load and Failover Tests](scalability-capacity-planning.md#conduct-load-and-failover-tests): Test load and recovery scenarios ahead of major campaigns to confirm your scaling and rollback plans actually hold up.

## 5. Operational Readiness

* [Apply All Security and Performance Patches](operational-readiness.md#apply-all-security-and-performance-patches): Finish all patching before code freeze so deployments aren't disrupted later.
* [Run Pre-Holiday Health Checks](operational-readiness.md#run-pre-holiday-health-checks): Test backups, cron health, and cache warmup scripts so operations run smoothly under load.
* [Establish Monitoring Playbooks](operational-readiness.md#establish-monitoring-playbooks): Document alert thresholds, escalation paths, and 24x7 contacts so the team can respond fast during peak.
* [Document Rollback Plans](operational-readiness.md#document-rollback-plans): Keep versioned rollback strategies ready so you can recover quickly from a bad deployment.