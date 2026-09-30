---
title: Performance optimization
description: Performance optimization recommendations to help Adobe Commerce merchants prepare their environments for high-traffic events such as the holiday season.
feature-set: Commerce
feature: Support
solution: Commerce
role: Developer, Admin, Leader
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

# Performance optimization

This section provides technical recommendations for preparing Adobe Commerce environments—both Commerce on cloud infrastructure and on-premises—for high-traffic events such as the holiday season.

>[!NOTE]
>
>Steps marked **(Cloud only)** apply to Commerce on cloud infrastructure. Most other recommendations also apply to on-premises deployments.

## Optimize Fastly request caching (Cloud only) {#optimize-fastly-request-caching}

[!DNL Fastly] caches responses at the edge to reduce load on your origin server. During peak season, a few configuration checks help you get the most out of that cache, especially when you're running promotions with tracking parameters or a headless storefront. For the full configuration reference, see [Customize cache configuration](https://experienceleague.adobe.com/en/docs/commerce-on-cloud/user-guide/cdn/setup-fastly/fastly-custom-cache-configuration).

* Normalize tracking parameters: During the holiday season, you're likely to run social and paid campaigns, such as Google Ads, Facebook, and X, that append unique tracking strings to every URL. Each unique string creates a separate cache entry for what's otherwise the same page, which lowers your cache hit ratio. Add these parameters to the **[!UICONTROL Ignored URL Parameters]** list in the [!DNL Fastly] configuration in the Adobe Commerce Admin so that [!DNL Fastly] treats them as equivalent.
* Confirm that your landing pages are cacheable: Check the `x-cache` response header on each promotion landing page. A cacheable page returns `HIT`, or a `HIT`/`MISS` pair on subsequent loads. If the header returns `MISS, MISS`, the page isn't caching and requires investigation.
* Use GET requests for GraphQL queries: If you run a PWA or headless storefront, send GraphQL queries as `GET` requests with the query included in the URL, rather than as `POST` requests. [!DNL Fastly] caches only `GET` requests where the query is part of the URL. A `GET` request with the query sent in the body isn't cached.

>[!NOTE]
>
>[!DNL Fastly] origin shielding also affects cache performance. For configuration details, see [Fastly origin shielding](/help/adobe-support-tools-guide/adobe-commerce-support/adobe-commerce-holiday-readiness-overview/scalability-capacity-planning.md#fastly-origin-shielding).

## Enable Fastly IO (Cloud only) {#enable-fastly-io}

[!DNL Fastly] IO offloads image resizing and format conversion to the [!DNL Fastly] edge network instead of the Adobe Commerce origin. This reduces server load and improves page rendering speed for image-heavy storefronts, a common bottleneck during high-traffic sales periods. For configuration options, see [Fastly image optimization](https://experienceleague.adobe.com/en/docs/commerce-on-cloud/user-guide/cdn/fastly-image-optimization).

Before you begin, confirm that origin shielding is configured. [!DNL Fastly] IO requires origin shielding as a prerequisite. For configuration details, see [Fastly origin shielding](/help/adobe-support-tools-guide/adobe-commerce-support/adobe-commerce-holiday-readiness-overview/scalability-capacity-planning.md#fastly-origin-shielding).

To enable [!DNL Fastly] IO:

1. In the Admin, go to the **[!UICONTROL Fastly Configuration]** page and select **[!UICONTROL Configure]** next to **[!UICONTROL Default IO config options]**.
1. Confirm that the [!DNL Fastly] IO snippet is enabled.
1. In the **[!UICONTROL Image Optimization]** configuration, set **[!UICONTROL Enable deep image optimization]** to *[!UICONTROL Yes]*. This setting disables Adobe Commerce's built-in image resizing and transfers the task to [!DNL Fastly].
1. Confirm that the shield location is set correctly. For configuration details, see [Fastly origin shielding](#fastly-origin-shielding).

>[!NOTE]
>
>Deep image optimization resizes product images only. CMS images, such as banners and content blocks, aren't affected and continue to use Adobe Commerce's built-in resizing.

To verify that [!DNL Fastly] IO is working, check the response headers on a product image request:

* The `x-cache` header returns `HIT`.
* The `fastly-io-info` and `fastly-stats` headers are populated.
* The image URL doesn't include a `/cache/` directory in the path.

## Implement Redis L2 cache {#implement-redis-l2-cache}

Implement effective caching practices so that your store performs reliably during peak traffic seasons. [!DNL Redis] L2 cache reduces network bandwidth to [!DNL Redis] by storing cache data locally on each web node. For background on how L2 cache works, see [Level two cache](https://experienceleague.adobe.com/en/docs/commerce-operations/configuration-guide/cache/level-two-cache).

On Commerce on cloud infrastructure, enable this by setting the `REDIS_BACKEND` deploy variable. For configuration steps, see [REDIS_BACKEND](https://experienceleague.adobe.com/en/docs/commerce-on-cloud/user-guide/configure/env/stage/variables-deploy#redis_backend) in the Commerce on Cloud Infrastructure Guide. On-premises, configure it directly in `app/etc/env.php`.

>[!NOTE]
>
>[!DNL Redis] is not supported as the L2 cache backend on Adobe Commerce 2.4.9 or later, or on patch releases later than 2.4.5-p16, 2.4.6-p14, 2.4.7-p9, or 2.4.8-p4. On these versions, use `VALKEY_BACKEND` instead.

## Enable MySQL and Redis slave connections (Cloud only) {#enable-mysql-and-redis-slave-connections}

[!DNL Redis] and [!DNL MySQL] slave connections offload read traffic to replica nodes, reducing load on the master connection during high-traffic periods. For configuration steps, see [MYSQL_USE_SLAVE_CONNECTION](https://experienceleague.adobe.com/en/docs/commerce-on-cloud/user-guide/configure/env/stage/variables-deploy#mysql_use_slave_connection) and [REDIS_USE_SLAVE_CONNECTION](https://experienceleague.adobe.com/en/docs/commerce-on-cloud/user-guide/configure/env/stage/variables-deploy#redis_use_slave_connection) in the Commerce on Cloud Infrastructure Guide.

### Redis slave connections

A [!DNL Redis] slave connection is a read-only connection to a [!DNL Redis] instance, allowing read traffic to be served from a non-master node. Without it enabled, [!DNL MySQL] can suffer a high-load bottleneck. Check [!DNL New Relic]'s APM Overview chart for rising response times as an early sign, then confirm in the **[!UICONTROL Database]** tab by sorting by most time-consuming transaction to identify slow [!DNL MySQL] `SELECT` queries. Enable this by setting the deploy variable `REDIS_USE_SLAVE_CONNECTION` to `true`.

>[!NOTE]
>
>`REDIS_USE_SLAVE_CONNECTION` is supported only on Staging and Production Pro cluster environments. It is not supported on Starter or Scaled (split) architecture projects. Enabling it on Scaled architecture causes [!DNL Redis] connection errors—use [!DNL Redis] L2 cache instead on that architecture. See [Implement Redis L2 cache](#implement-redis-l2-cache-implement-redis-l2-cache) above.

### MySQL slave connections 

Enable the `MYSQL_USE_SLAVE_CONNECTION` flag on Pro cluster environments to direct specific read-only database queries to a slave connection, offloading query execution from the master connection.

>[!CAUTION]
>
>Load test before enabling either setting in production. On environments with normal load, slave connections can slow performance by 10 to 15 percent. On environments with heavy, sustained load, they can improve performance by a similar margin. Evaluate under expected peak-season traffic before enabling.

## Enable asynchronous order and email processing {#enable-asynchronous-order-and-email-processing}

Use asynchronous processing to queue and execute high-volume order-related operations in the background, reducing frontend latency during peak traffic. This covers three related but distinct settings—see [Configuration best practices](https://experienceleague.adobe.com/en/docs/commerce-operations/performance-best-practices/configuration) for an overview.

* Asynchronous order placement: The Async Order module marks an order as received, places it in a queue, and processes orders first-in-first-out. It is disabled by default. Enable it from the command line:

  ```
  bin/magento setup:config:set --checkout-async 1
  ```
  
  Once enabled, order details aren't available immediately—the order remains queued until the `placeOrderProcess` consumer verifies it against inventory (enabled by default) and updates it. Before disabling this module, verify that all in-flight asynchronous orders have finished processing. For details, see [Checkout performance best practices](https://experienceleague.adobe.com/en/docs/commerce-operations/performance-best-practices/high-throughput-order-processing).

* Asynchronous order data processing: Intensive storefront sales and intensive order processing can conflict at the database level. Enabling this setting distinguishes the two traffic patterns, so orders are placed in temporary storage and moved in bulk to the Order Management grid without collisions. This schedules updates, by cron, to the Orders, Invoices, Shipments, and Credit Memos grids, avoiding locks and reducing processing time. For best results, configure cron to run once every minute.

>[!NOTE]
>
>How you enable this depends on your deployment mode. Adobe Commerce on cloud infrastructure Staging and Production environments run in Production mode by default, where this setting isn't available through the Admin. In Production mode, run `bin/magento config:set dev/grid/async_indexing 1` instead. In Default mode, go to **[!UICONTROL Stores]** > **[!UICONTROL Configuration]** > **[!UICONTROL Advanced]** > **[!UICONTROL Developer]** > **[!UICONTROL Grid Settings]** and set **[!UICONTROL Asynchronous Indexing]** to *[!UICONTROL Enable]*.

  For details, see [Scheduled order operations](https://experienceleague.adobe.com/en/docs/commerce-admin/stores-sales/order-management/orders/order-scheduled-operations).

* Asynchronous email notifications: This setting moves checkout and order-processing email notifications to the background. Enable it at **[!UICONTROL Stores]** > **[!UICONTROL Configuration]** > **[!UICONTROL Sales]** > **[!UICONTROL Sales Emails]** > **[!UICONTROL General Settings]** > **[!UICONTROL Asynchronous Sending]**.

## Configure indexers for update on schedule {#configure-indexers-for-update-on-schedule}

Set indexers to run in scheduled mode to avoid database locking and improve responsiveness during frequent catalog updates. For details, see [Best practices for indexer configuration](https://experienceleague.adobe.com/en/docs/commerce-operations/implementation-playbook/best-practices/maintenance/indexer-configuration).

An indexer can run in **[!UICONTROL Update on Save]** or **[!UICONTROL Update on Schedule]** mode.

* **[!UICONTROL Update on Save]** indexes immediately whenever catalog or other data changes. It assumes low update and browsing intensity, and can cause significant delays and data unavailability under high load.
* **[!UICONTROL Update on Schedule]** is recommended for production. It stores information about data updates and reindexes in the background through a dedicated cron job.

Set each indexer's update mode independently at **[!UICONTROL System]** > **[!UICONTROL Tools]** > **[!UICONTROL Index Management]**.

>[!IMPORTANT]
>
>The `customer_grid` indexer's supported modes depend on your Adobe Commerce version. On versions earlier than 2.4.8, Customer Grid supports **[!UICONTROL Update on Save]** only—do not set it to **[!UICONTROL Update on Schedule]**. On Adobe Commerce 2.4.8 and later, Customer Grid supports both modes and now defaults to **[!UICONTROL Update on Schedule]**.

## Disable and evaluate catalog flat table {#disable-and-evaluate-catalog-flat-table}

The use of flat tables for products and categories is not recommended. This deprecated feature can cause performance degradation and indexing issues. For details, see [Flat catalogs](https://experienceleague.adobe.com/en/docs/commerce-admin/catalog/catalog/catalog-flat).

To disable the flat catalog, go to **[!UICONTROL Stores]** > **[!UICONTROL Configuration]** > **[!UICONTROL Catalog]** > **[!UICONTROL Catalog]** > **[!UICONTROL Storefront]**, set **[!UICONTROL Use Flat Catalog Category]** to *[!UICONTROL No]*, set **[!UICONTROL Use Flat Catalog Product]** to *[!UICONTROL No]*, then click **[!UICONTROL Save Config]**.

Some third-party modules and customizations do require flat tables to function correctly. Evaluate the impact and risk of continuing to use those extensions before disabling flat tables.

## Consider scaled (split) architecture (Cloud only) {#consider-scaled-split-architecture}

If, after applying the preceding configuration and code-level optimizations, load testing or live infrastructure performance still shows CPU and other resources maxed out, consider moving to a scaled (split) architecture. For details, see [Scaled architecture](https://experienceleague.adobe.com/en/docs/commerce-on-cloud/user-guide/architecture/scaled-architecture).

>[!NOTE]
>
>Scaled architecture is available only for accounts with a Pro 48 cluster or greater.

Split-tier architecture uses a minimum of six nodes: three service nodes running [!DNL OpenSearch] or [!DNL Elasticsearch], [!DNL MariaDB], and [!DNL Redis] or [!DNL Valkey], and three web nodes running `php-fpm` and `NGINX`.

* Service nodes can scale vertically only, by increasing server size (CPU and memory). Because the database cluster is built for high availability, service nodes cannot scale horizontally in a reliable way.
* Web nodes can scale both vertically and horizontally, adding web servers to handle increased request volume.

This lets you expand infrastructure on demand for periods of high load, scaling each tier independently. To switch to split-tier architecture ahead of an expected heavy-load period, contact your Adobe Account Team.