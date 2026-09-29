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

This section provides technical recommendations for scaling [!DNL Adobe Commerce] environments to prepare for high-traffic events such as the holiday season.

>[!NOTE]
>
>Steps marked **(Cloud only)** apply to Commerce on cloud infrastructure. Most other recommendations also apply to on-premises deployments.

## Plan cluster upsize early (Cloud only) {#plan-cluster-upsize-early}

For Commerce Cloud customers, a temporary cluster upsize allocates more computing resources to handle peak-season traffic surges. Raise a support ticket in advance with the date range and required cluster size, and coordinate with your dedicated Account Manager on current resource consumption and requirements. Submit the request at least 48 business hours before the capacity is needed—for the holiday season specifically, submit as early as possible, since capacity during Black Friday and Cyber Monday is limited. See [How to request a temporary upsize](https://experienceleague.adobe.com/en/docs/support-resources/adobe-support-tools-guide/adobe-commerce-support/how-to-request-temporary-adobe-commerce-on-cloud-infrastructure-upsize).

For example, a Pro-architecture customer with a daily baseline of 24 cores (24 vCPUs, 96 GB RAM) upsizing to 96 cores for 7 days would use roughly 4 times the resources (96 vCPUs, 384 GB RAM)—an incremental consumption of about 504 vCPU-days (96×7 − 24×7).

## Fastly origin shielding {#fastly-origin-shielding}

The purpose of Adobe Commerce [!DNL Fastly]'s origin shielding is to reduce traffic directly to the Adobe Commerce origin. When a request is received, a [!DNL Fastly] edge location (Point of Presence) checks for cached content and delivers it. If it isn't cached, it continues to the Shield POP to check if it's cached there—if the content has previously been requested even from another global POP, it will be cached. Finally, if it isn't cached on the Shield POP, it will only then proceed to the origin server.

[!DNL Fastly] origin shielding can be enabled in the Adobe Commerce Admin, in the [!DNL Fastly] configuration backend settings. Choose a shield location closest to your Adobe Commerce origin data center for the best performance. For details, see [Configure back ends and origin shielding](https://experienceleague.adobe.com/en/docs/commerce-on-cloud/user-guide/cdn/setup-fastly/fastly-custom-cache-configuration#configure-back-ends-and-origin-shielding).

By default, [!DNL Fastly] origin shielding is not enabled.

## Conduct load and failover tests {#conduct-load-and-failover-tests}

Perform load and recovery tests before major campaigns to validate scaling configurations and rollback plans.