---
title: Scalability and capacity planning
description: Scalability and capacity planning recommendations to help Adobe Commerce merchants prepare their environments for high-traffic events such as the holiday season.
feature-set: Commerce
feature: Support
solution: Commerce
role: Developer, Admin, Leader
product_v2:
  - id: eadea719-cf89-469b-a6fd-a236a7138047
    internal-label: Commerce
feature_v2:
  - id: dac87252-6066-4d6e-a9d2-f6d84c323de7
    internal-label: Configuration
  - id: 5a951749-fac9-5bc7-9a98-ebe4ff066437
    internal-label: Cloud
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

# Scalability and capacity planning

This section provides technical recommendations for preparing [!DNL Adobe Commerce] environments—both Commerce on cloud infrastructure and on-premises—for high-traffic events such as the holiday season.

>[!NOTE]
>
>Steps marked **(Cloud only)** apply to Commerce on cloud infrastructure. On-premises environments should plan equivalent capacity increases with their own hosting provider or infrastructure team.

## Plan cluster upsize early (Cloud only) {#plan-cluster-upsize-early}

Coordinate with Adobe Support to temporarily scale compute resources during promotions. Plan at least 10 business days in advance. See [How to request a temporary upsize](https://experienceleague.adobe.com/en/docs/commerce-knowledge-base/kb/how-to/how-to-request-temporary-magento-upsize).

* For Commerce on cloud infrastructure customers, implementing a planned upsize requires raising a support ticket in advance with the date range and required cluster size, coordinated with your dedicated Account Manager based on current resource consumption. For example: a Pro-architecture customer with a daily baseline of 24 cores (24 vCPUs, 96 GB RAM) upsizing to 96 cores for 7 days would use roughly 4x the resources (96 vCPUs, 384 GB RAM)—an incremental consumption of about 504 vCPU-days (96×7 − 24×7).

## Enable Fastly origin shielding (Cloud only) {#enable-fastly-origin-shielding}

Configure a Shield POP close to your origin to reduce direct hits and latency for uncached requests. See [Fastly custom cache configuration](https://experienceleague.adobe.com/en/docs/commerce-on-cloud/user-guide/cdn/setup-fastly/fastly-custom-cache-configuration). For details on how origin shielding works, see [Performance optimization](performance-optimization.md).

## Conduct load and failover tests {#conduct-load-and-failover-tests}

Perform load and recovery tests before major campaigns to validate scaling configurations and rollback plans.

