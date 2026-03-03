---
title: Unable to add user to Adobe Commerce cloud project
description: This article provides a solution for when you are unable to add a user to an Adobe Commerce cloud project.
feature: Cloud, Paas
solution: Commerce
feature-set: Commerce
role: Developer
exl-id: 2dc52d5e-0930-48c4-986e-ce3f9f6f8221
---
# Unable to add user to Adobe Commerce cloud project

This article provides a solution for when you are trying to add a user to a cloud project, but it fails with an error: *User XXX does not exist*.

## Affected products and versions

* Adobe Commerce on cloud infrastructure, [all supported versions](https://magento.com/sites/default/files/magento-software-lifecycle-policy.pdf)

## Issue

This article provides a solution for when you are unable to add a user to an Adobe Commerce cloud project.

## Cause

The user’s account must first be created at [https://accounts.magento.cloud](https://accounts.magento.cloud) and linked to their Adobe SSO before they can be added as a user to the project. If the user has an Adobe account but not a Commerce (magento.com) account, they must first create one.

## Solution

1. Ask the user to sign in at [https://accounts.magento.cloud](https://accounts.magento.cloud). The user must already be registered with Adobe using the same email address.
   > **NOTE**  
   > Creating or having an account at [https://account.adobe.com](https://account.adobe.com) doesn't automatically mean that the user has an account at [https://accounts.magento.cloud](https://accounts.magento.cloud). The user must first [create their Commerce account](https://experienceleague.adobe.com/en/docs/commerce-admin/start/commerce-account/commerce-account-create?lang=en#create-a-commerce-account).

1. If the user already has an Adobe account but is unable to sign in, ask them to submit a [support request](https://experienceleague.adobe.com/home#support) with [!UICONTROL Issue Reason] set to *User Management*.

1. After the user successfully signs in to [https://accounts.magento.cloud](https://accounts.magento.cloud), you can add the user to the project. For detailed steps, see [Add users and manage access](https://experienceleague.adobe.com/en/docs/commerce-cloud-service/user-guide/project/user-access#add-users-and-manage-access) in the Commerce on Cloud Infrastructure Guide.

## Related reading:

* [Manage user access](https://experienceleague.adobe.com/docs/commerce-cloud-service/user-guide/project/user-access.html) in our Commerce on Cloud Infrastructure Guide.
* [Unable to log in to Adobe Commerce support or cloud account](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/troubleshooting/miscellaneous/unable-to-log-in-to-support-or-cloud-project.html)
