---
title: Manage Product Profiles in the Global Admin Console
description: Learn how global administrators can add, edit, and delete Product Profiles in the Global Admin Console.
feature-set: Experience Cloud Services
solution: Admin Console
feature: Admin Console
product_v2:
  - id: f7bdf6be-dd3b-4d2d-ac52-0e62ed0d3102
    internal-label: Admin Console
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
exl-id: 6a0b2d9f-9e02-428c-a2be-bc457230f7e0
---
# Manage Product Profiles in the Global Admin Console

**Applies to:** Enterprise


## Overview

Global administrators can add, edit, and delete Product Profiles in the [Global Admin Console](https://global-admin-console.adobe.com/).

>[!NOTE]
>
>In the [Global Admin Console](https://helpx.adobe.com/enterprise/global-admin-console/adopt-global-administration.html#request-access), select an organization and navigate to **[!UICONTROL Products]**. You can activate all or selected services for a product using Product Profiles.

As in the standard Admin Console, Product Profiles allow you to fine-tune the usage of products within an organization. You can also assign administrators — called **[!UICONTROL Product Profile administrators]** — to Product Profiles. These administrators can add end users to the Product Profiles they manage.

To manage Product Profiles, select a product. The controls to add, edit, and delete Product Profiles will be displayed.

>[!NOTE]
>
>For some products, you can't create or edit Product Profiles in the Global Admin Console. In such cases, use the [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html) instead.

## Add a Product Profile

1. In the [Global Admin Console](https://global-admin-console.adobe.com/), select an organization to edit, then navigate to the **[!UICONTROL Products]** tab.
1. Select a product to add a Product Profile to.
1. Select **[!UICONTROL Add Profile]**.
1. In the **[!UICONTROL Add Profile]** dialog box, enter the following details:

   | Field | Description |
   |---|---|
   | **[!UICONTROL Name]** | A unique name for the Product Profile within the organization, distinct from other Product Profiles and user groups. |
   | **[!UICONTROL Quota]** | The target number of licenses allotted for this profile. |
   | **[!UICONTROL User Groups]** | Select from the dropdown or type a user group name. If the user group doesn't yet exist, create it first via the [**[!UICONTROL User Groups]**](https://helpx.adobe.com/enterprise/global-admin-console/manage-user-groups.html) tab. |
   | **[!UICONTROL Admins]** | Select from the dropdown or enter an admin's email address. If the admin doesn't yet exist, create them first via the [**[!UICONTROL Admins]**](https://helpx.adobe.com/enterprise/global-admin-console/manage-administrators.html) tab. |

   The [!UICONTROL User Groups] specified are assigned the Product Profile. The admins specified become the **[!UICONTROL Product Profile Admins]**, who can manage the profile via the Adobe Admin Console for the relevant organization.

   ![Add Profile](./assets/manage-product-profiles_add-profile.png)

1. Use the **[!UICONTROL Notifications]** toggle to enable or disable email notifications. When enabled, users are notified by email when they are added to or removed from the profile.
1. Use the individual **[!UICONTROL Services]** toggles to enable or disable specific services for the Product Profile. For more information, see [Enable/Disable Services for a Product Profile](https://helpx.adobe.com/enterprise/using/enable-disable-services.html).
1. Select **[!UICONTROL Save]**.
1. Select **[!UICONTROL Review Pending Changes]** once you have finished editing the organizations. After reviewing, select **[!UICONTROL Submit Changes]** to [execute](https://helpx.adobe.com/enterprise/global-admin-console/execute-jobs.html) them.

## Edit a Product Profile

1. Select an organization to edit, navigate to the **[!UICONTROL Products]** tab, and select a product.
1. Select the **[!UICONTROL More Options]** ![More Options](./assets/manage-product-profiles_more-options.png) icon for the relevant Product Profile, then select **[!UICONTROL Edit Profile]**.
1. Update the Product Profile details as needed and select **[!UICONTROL Save]**.
1. Select **[!UICONTROL Review Pending Changes]** once you have finished editing the organizations. After reviewing, select **[!UICONTROL Submit Changes]** to [execute](https://helpx.adobe.com/enterprise/global-admin-console/execute-jobs.html) them.

## Delete a Product Profile

>[!WARNING]
>
> Deleting a Product Profile removes product access for all users who were members of that profile, or belonged to user groups attached to that profile.

1. Select an organization to edit, navigate to the **[!UICONTROL Products]** tab, and select a product.
1. Select the **[!UICONTROL More Options]** ![More Options](./assets/manage-product-profiles_more-options.png) icon for the relevant Product Profile, then select **[!UICONTROL Delete Profile]**.
1. Select **[!UICONTROL OK]** in the confirmation dialog box.
1. Select **[!UICONTROL Review Pending Changes]** once you have finished editing the organizations. After reviewing, select **[!UICONTROL Submit Changes]** to [execute](https://helpx.adobe.com/enterprise/global-admin-console/execute-jobs.html) them.


## Related reading

- [Adopt Global Administration](https://helpx.adobe.com/enterprise/global-admin-console/adopt-global-administration.html)
- [Manage Administrators](https://helpx.adobe.com/enterprise/global-admin-console/manage-administrators.html)
- [Manage User Groups](https://helpx.adobe.com/enterprise/global-admin-console/manage-user-groups.html)
- [Allocate Products to Child Organizations](https://helpx.adobe.com/enterprise/global-admin-console/allocate-products.html)
- [Execute Pending Jobs](https://helpx.adobe.com/enterprise/global-admin-console/execute-jobs.html)
- [Enable/Disable Services](https://helpx.adobe.com/enterprise/using/enable-disable-services.html)
- [Admin Console Overview](https://helpx.adobe.com/enterprise/using/admin-console.html)
