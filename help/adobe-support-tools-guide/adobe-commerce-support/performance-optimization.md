---
title: Performance optimization
description: Performance optimization recommendations to help Adobe Commerce merchants prepare their environments for high-traffic events such as the holiday season.
feature-set: Commerce
feature: Support
solution: Commerce
role: Developer, Admin, Leader
---

# Performance optimization

This section provides technical recommendations for preparing [!DNL Adobe Commerce] environments—both Commerce on cloud infrastructure and on-premises—for high-traffic events such as the holiday season.

>[!NOTE]
>
>Steps marked **(Cloud only)** apply to Commerce on cloud infrastructure. Most other recommendations also apply to on-premises deployments.

## Optimize Fastly request caching (Cloud only) {#optimize-fastly-request-caching}

Normalize tracking parameters and ensure landing pages are cacheable to maximize your cache hit ratio. Use GraphQL GET requests where possible for PWA/headless storefronts. See [Fastly custom cache configuration](https://experienceleague.adobe.com/en/docs/commerce-on-cloud/user-guide/cdn/setup-fastly/fastly-custom-cache-configuration).

* **Normalize unique parameters.** During the holiday season you are likely to run social media and ad-based promotions (for example, Google Ads, Facebook, or X) that include unique tracking query strings per customer. Update the [!DNL Fastly] **Ignored URL Parameters** list in the Adobe Commerce Admin to normalize these requests and improve cache performance.
* **Ensure landing pages are cacheable.** Confirm that promotion landing pages are cacheable in [!DNL Fastly]. Inspect the `x-cache` response header for a sequence of `HIT` values, or `MISS` followed by `HIT` on subsequent loads. See [!DNL Fastly]'s [debugging documentation](https://www.fastly.com/documentation/guides/full-site-delivery/caching/checking-cache/) for details.
* **Cache GraphQL queries.** For PWA/headless storefronts, make sure GraphQL queries use `GET` instead of `POST` whenever applicable.

[!DNL Fastly] origin shielding reduces traffic that reaches the Adobe Commerce origin directly: an edge Point of Presence (POP) checks for cached content first, then a Shield POP, and only then the origin server. Enable it in the Adobe Commerce Admin under Fastly configuration backend settings, and choose the shield location closest to your origin data center for best performance. It is not enabled by default. 

## Enable Fastly IO (Cloud only) {#enable-fastly-io}

Activate [!DNL Fastly] Image Optimization and Deep IO to offload image transformations to the CDN. This reduces origin load and improves page render time for image-heavy storefronts. See [[!DNL Fastly] image optimization](https://experienceleague.adobe.com/en/docs/commerce-on-cloud/user-guide/cdn/fastly-image-optimization).

1. On the **[!UICONTROL Fastly Configuration]** page, in the **[!UICONTROL Default IO config options]** field, select **[!UICONTROL Configure]**.
1. Review and confirm the [!DNL Fastly] IO snippet is enabled.
1. In the **[!UICONTROL Image Optimization]** configuration, set **[!UICONTROL Enable deep image optimization]** to *Yes*.
1. Verify the correct shield location is configured (see [!DNL Fastly] origin shielding above).

Verify the configuration is working by checking response headers: `x-cache` returns `HIT`, `fastly-io-info` and `fastly-stats` are populated, and image URL paths do not use the `/cache/` directory.

## Implement Redis L2 cache {#implement-redis-l2-cache}

Reduce latency by storing cache data locally on each web node, cutting network bandwidth to [!DNL Redis]. See [Level two cache](https://experienceleague.adobe.com/en/docs/commerce-operations/configuration-guide/cache/level-two-cache).

* On Commerce on cloud infrastructure, enable it with the `REDIS_BACKEND` deploy variable.
* On-premises, configure it directly in `app/etc/env.php`.

## Enable MySQL and Redis slave connections (Cloud only) {#enable-mysql-and-redis-slave-connections}

Offload read-heavy queries to replica nodes to reduce load on master databases. See [MySQL configuration best practices](https://experienceleague.adobe.com/en/docs/commerce-operations/implementation-playbook/best-practices/planning/mysql-configuration).

* **[!DNL Redis] slave connections** enable read-only connections to a [!DNL Redis] instance so read traffic can be served from a non-master node. Without this, [!DNL MySQL] can become a high-load bottleneck. Signs of a bottleneck in [!DNL New Relic] APM include rising response time in the Overview chart, and slow `SELECT` queries when sorting the **Database** tab by most time-consuming transaction. Enable with the deploy variable `REDIS_USE_SLAVE_CONNECTION` set to `true`. This is supported only on Staging and Production Pro cluster environments—not on Starter and Scaled architecture projects.
* **[!DNL MySQL] slave connection.** Enable the `MYSQL_USE_SLAVE_CONNECTION` flag on Pro cluster environments so specific read-only database queries are directed to the slave connection, offloading some query execution from the master connection.
* These deploy variables are specific to Commerce on cloud infrastructure. On-premises environments can achieve the same read/write splitting by configuring replica connections directly in `app/etc/env.php`.

## Enable asynchronous order and email processing {#enable-asynchronous-order-and-email-processing}

Use async processing to queue and execute high-volume operations in the background, ensuring faster checkout completion and reduced frontend latency. See [Order processing configuration](https://experienceleague.adobe.com/en/docs/commerce-operations/implementation-playbook/best-practices/maintenance/order-processing-configuration). This covers three related but distinct settings:

* **Asynchronous order placement.** The Async Order module (disabled by default) marks an order as received, queues it, and processes orders first-in-first-out. Enable it with the CLI command `bin/magento setup:config:set --checkout-async 1`, or by editing `app/etc/env.php`. Once enabled, order details aren't available immediately—the order stays queued until the `placeOrderProcess` consumer verifies it against inventory and updates it. Before disabling this module, verify that all in-flight async orders have finished processing.
* **Asynchronous order data processing** distinguishes storefront sales and promotion traffic from intensive order-processing traffic at the database level, to avoid read/write conflicts. Enable this at **[!UICONTROL Stores]** > **[!UICONTROL Settings]** > **[!UICONTROL Configuration]** > **[!UICONTROL Advanced]** > **[!UICONTROL Developer]** > **[!UICONTROL Grid Settings]** > **[!UICONTROL Asynchronous indexing]**. This schedules updates (through cron) to the Orders, Invoices, Shipments, and Credit Memos grids, avoiding locks and reducing processing time. For best results, run cron once every minute.
* **Asynchronous email notifications** move checkout and order-processing email notifications to the background. Enable this at **[!UICONTROL Stores]** > **[!UICONTROL Settings]** > **[!UICONTROL Configuration]** > **[!UICONTROL Sales]** > **[!UICONTROL Sales Emails > **[!UICONTROL General Settings]** > **[!UICONTROL Asynchronous Sending]**.

## Configure indexers for update on schedule {#configure-indexers-for-update-on-schedule}

Set indexers to run in scheduled mode to avoid locking and improve responsiveness during frequent catalog updates. See [Indexer configuration](https://experienceleague.adobe.com/en/docs/commerce-operations/implementation-playbook/best-practices/maintenance/indexer-configuration).

* An indexer can run in **Update on Save** or **Update on Schedule** mode.
* **Update on Save** indexes immediately whenever catalog or other data changes. It assumes low update and browsing intensity, and can cause significant delays and data unavailability under high load.
* **Update on Schedule** is recommended for production. It stores information about data updates and indexes in the background through a dedicated cron job.
* Set each indexer's update mode independently at **[!UICONTROL System]** > **[!UICONTROL Tools]** > **[!UICONTROL Index Management]**.

>[!IMPORTANT]
>
>The `customer_grid` indexer should not be set to **Update on Schedule** mode.

## Disable and evaluate catalog flat table

Using flat tables for products and categories is not recommended—this deprecated feature can cause performance degradation and indexing issues. Disable catalog flat tables in the Adobe Commerce Admin, in the **[!UICONTROL Storefront]** section.

Some third-party modules or customizations may still require flat tables to function. If so, evaluate the impact and risk of continuing to use those extensions before disabling flat tables.

## Consider scaled (split) architecture (Cloud only) {#consider-scaled-split-architecture}

Adopt split-tier architecture for high-load environments, scaling web and database nodes independently to handle increased transactions efficiently. See [Scaled architecture](https://experienceleague.adobe.com/en/docs/commerce-on-cloud/user-guide/architecture/scaled-architecture).

* If, after applying the preceding configuration and code-level optimizations, load testing or live infrastructure performance still shows CPU and other resources maxed out, consider moving to a scaled (split) architecture.
* Split-tier architecture uses a minimum of six nodes: three running [!DNL ElasticSearch], [!DNL MariaDB], [!DNL Redis], and other core services, and three dedicated to web traffic (`php-fpm` and `NGINX`).
* This allows core and database nodes to scale vertically while web nodes scale both horizontally and vertically—expanding infrastructure on demand for periods of high load.
* To switch to split-tier architecture ahead of an expected heavy-load period, contact your Adobe Account Team.