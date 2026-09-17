---
description: Scalability and capacity planning recommendations to help Adobe Commerce merchants prepare their environments for high-traffic events such as the holiday season.
feature: Support, Configuration, Performance
role: Admin, Developer
type: Tutorial
---

# Scalability & capacity planning

This section provides technical recommendations for preparing [!DNL Adobe Commerce] environments—both Commerce on cloud infrastructure and on-premises—for high-traffic events such as the holiday season.

>[!NOTE]
>
>Steps marked **(Cloud only)** apply to Commerce on cloud infrastructure. On-premises environments should plan equivalent capacity increases with their own hosting provider or infrastructure team.

## Plan cluster upsize early (Cloud only) {#plan-cluster-upsize-early}

Coordinate with Adobe Support to temporarily scale compute resources during promotions. Plan at least 10 business days in advance. See [How to request a temporary upsize](https://experienceleague.adobe.com/en/docs/commerce-knowledge-base/kb/how-to/how-to-request-temporary-magento-upsize).

* For Commerce on cloud infrastructure customers, implementing a planned upsize requires raising a support ticket in advance with the date range and required cluster size, coordinated with your dedicated Account Manager based on current resource consumption.
* **Example:** a Pro-architecture customer with a daily baseline of 24 cores (24 vCPUs, 96 GB RAM) upsizing to 96 cores for 7 days would use roughly 4x the resources (96 vCPUs, 384 GB RAM)—an incremental consumption of about 504 vCPU-days (96×7 − 24×7).

## Enable Fastly origin shielding (Cloud only) {#enable-fastly-origin-shielding}

Configure a Shield POP close to your origin to reduce direct hits and latency for uncached requests. See [Fastly custom cache configuration](https://experienceleague.adobe.com/en/docs/commerce-on-cloud/user-guide/cdn/setup-fastly/fastly-custom-cache-configuration). For details on how origin shielding works, see [Performance optimization](performance-optimization.md).

## Conduct load and failover tests {#conduct-load-and-failover-tests}

Perform load and recovery tests before major campaigns to validate scaling configurations and rollback plans.

