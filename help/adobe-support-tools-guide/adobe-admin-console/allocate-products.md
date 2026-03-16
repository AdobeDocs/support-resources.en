---
title: Allocate products to child organizations using the Global Admin Console
description: Learn how global administrators can distribute resources to child organizations, enabling effective resource management and user assignment within each organization.
Feature-set: Experience Cloud Services
Solution: Admin Console
Feature: Admin Console
---
# Allocate products to child organizations using the Global Admin Console

Applies to enterprise.

Learn how global administrators can distribute resources to child organizations, enabling effective resource management and user assignment within each organization.

In the [Global Admin Console](https://helpx.adobe.com/enterprise/global-admin-console/adopt-global-administration.html), go to the **[!UICONTROL Product Allocation]** tab and select a product to allocate to child organizations.

Sign in to the [Global Admin Console](https://adminconsole.adobe.com/support).

>[!NOTE]
>
>**[!UICONTROL Product Allocation]** is available only for Enterprise Term License Agreement (ETLA) contracts.

Part of distributing and administering Adobe products across organizations is partitioning purchased resources into resource allocations across the organizations to be managed. You can distribute administration of product resources to other organizations by giving all or some of the resource. Not all resources of all products can be allocated; some products are not distributable to other organizations. Such products appear in the **[!UICONTROL Product Allocation]** tab but have no controls to add them to other organizations.

>[!WARNING]
>
>You cannot allocate products to a child organization from a contract that has **expired** or if the organization is in an **inactive** state. Learn more about [contract expiry](https://helpx.adobe.com/enterprise/using/contract-expiry.html), or contact your company's administrator for assistance to prevent users in the child organization from losing access to their Adobe apps and services.

## Pooled storage

We are in the process of migrating customers to the [pooled storage model](https://helpx.adobe.com/enterprise/using/manage-adobe-storage.html). Once your organization is migrated, you will see the following changes:

- Global administrators gain access to storage quota and usage across the hierarchy and can allocate storage to organizations using the **[!UICONTROL Product Allocation]** tab in the [Global Admin Console](https://adminconsole.adobe.com/).
- System administrators and storage administrators have full control and visibility of storage across the organization. They can track and manage storage using the **[!UICONTROL Storage]** tab in the [Adobe Admin Console](https://adminconsole.adobe.com/).

With the updates to Adobe Creative Cloud storage, storage quotas are flexible for end users, up to the amount of storage purchased by the organization. [Learn more](https://helpx.adobe.com/enterprise/using/manage-adobe-storage.html).

## Allocate products

The **[!UICONTROL Product Allocation]** tab in the Global Admin Console shows allocation units for products purchased across the organization hierarchy. As a [global administrator](https://helpx.adobe.com/enterprise/global-admin-console/manage-administrators.html#admins), you can allocate these product resources to another organization in the organization tree and specify the quantity to allocate. As a [global viewer](https://helpx.adobe.com/enterprise/global-admin-console/manage-administrators.html#admins), you can view and export the data but cannot make any updates.

To allocate products to an organization, follow these steps:

1. Sign in to the [Global Admin Console](https://global-admin-console.adobe.com) and go to **[!UICONTROL Product Allocation]**.
1. Select a product from the drop-down list to see how it is allocated to different organizations.  
   If an organization does not currently have the product, the **[!UICONTROL Add +]** icon appears.

   >[!Note]
   >
   >If the child organization already has a purchase contract, product allocation from the parent to that child organization may be limited. [Learn more](https://helpx.adobe.com/enterprise/global-admin-console/allocate-products.html#limited-product-allocation).

1. To allocate the product, select the **[!UICONTROL Add +]** icon for the relevant organization.  
   Some products include more than one allocatable resource; in that case, several resources are listed in the dialog box, and you must provide values for each. For example, [!DNL Adobe Stock] can include [!DNL Adobe Stock Image] credits and premium credits.
   ![Adobe Stock Images](/help/adobe-support-tools-guide/assets/adobe-stock-images.png)
1. In the dialog box that appears, specify the product quantity.
1. Select **[!UICONTROL Save]**.
1. To allow or disallow overallocation of a resource, select the relevant toggle.
   ![Overallocation](/help/adobe-support-tools-guide/assets/overallocation.png)
1. Select **[!UICONTROL Review Pending Changes]** after you are done allocating resources. After reviewing, select **[!UICONTROL Submit Changes]** to [execute](https://helpx.adobe.com/enterprise/global-admin-console/execute-jobs.html) them.

## Allocate and distribute Adobe Acrobat Sign user licenses or transactions

The Global Admin Console lets you allocate and distribute Acrobat Sign user licenses or transactions across the organizational hierarchy. Each organization in the hierarchy that has Acrobat Sign licenses or transactions allocated to it creates its own separate Acrobat Sign account.

- Each Acrobat Sign account created is independent and siloed in terms of administration and content.
- Each Acrobat Sign account is unaware of other Acrobat Sign accounts (for example, in parent or sister organizations).

Learn more about [managing Adobe Acrobat Sign in the Admin Console](https://helpx.adobe.com/enterprise/using/adobe-sign-for-enterprise.html).

To manage authentication add-ons such as Knowledge-based Authentication (KBA) and Phone Authentication (PA), contact your Adobe representative or Customer Success Manager.


## Limitations on product allocation

Allocation from a parent organization to a child organization is limited in these cases:

- If both organizations have different contracts and the product you are trying to allocate exists in both, mixing the same offer between contracts is not allowed.
- If both organizations have the same contract, you can request permission to allocate the product by contacting your Adobe representative or by [submitting a support](https://helpx.adobe.com/enterprise/using/support-for-enterprise.html) case specifying that **[!UICONTROL Product Allocation]** in Global Admin Console is blocked.

## Overallocation

As a [global administrator](https://helpx.adobe.com/enterprise/global-admin-console/manage-administrators.html#admins) you can allow overallocation of resources.

An allocation [policy](https://helpx.adobe.com/enterprise/global-admin-console/update-policies.html#update-policies) associated with the product and organization indicates whether overallocation is allowed.

Overallocation allows granting more product resources to a child organization than are available in the parent organization. It is useful when allocations are approximate, and the administrator does not want to be burdened with keeping the resource allocations adding up.
If overallocation is disabled for a product resource in an organization, then the sum of child grants cannot exceed the parent grant. Requests to overallocate a resource marked with overallocation disabled are not executed.
When the overallocation toggle is switched from enabled to disabled, the grant values must be adjusted to eliminate overallocation before grant updates can be executed, if an overallocation situation is present in the grant quantities of a resource.

![Overallocation](/help/adobe-support-tools-guide/assets/overallocation.png)

## Expired contracts in the hierarchy

You cannot allocate products to a child organization from an ETLA contract that has expired. In‑app banners and notifications, such as the following, on the **[!UICONTROL Overview]** and **[!UICONTROL Product Allocation]** pages clearly indicate when the contract on one or more child organizations is going to expire, has expired, or is inactive.

![Product allocation](/help/adobe-support-tools-guide/assets/product-allocation.png)

>[!Important]
>
>Once an ETLA contract that is part of the hierarchy is inactive, the products are removed from the **[!UICONTROL Overview]** and **[!UICONTROL Product Allocation]** pages.

[Learn more about contract expiry](https://helpx.adobe.com/enterprise/using/contract-expiry.html), or contact your company's administrator for assistance to prevent users in the child organization from losing access to their Adobe apps and services.
