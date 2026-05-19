---
title: How to include a team member in Support notifications
description: This article provides an explanation of how to include a team member in Support notifications.
feature: Cloud, Support, Admin Workspace
role: Admin, Developer
solution: Commerce
feature-set: Commerce
exl-id: 392ef795-f710-401f-8b0e-3c8dfec7bb3a
TQID: 'https://experienceleague.adobe.com/fWRfvDT8NCwPfzmAx1Zowo4T8KvKLKWqhDkZDfX8stU'
product_v2:
  - id: eadea719-cf89-469b-a6fd-a236a7138047
    internal-label: Commerce
feature_v2:
  - id: e7dae43f-215c-4cdf-90d3-c5a461a6e669
    internal-label: Admin tools and workspace
subfeature_v2:
  - id: bb2df8be-afdd-4818-b6b5-95ca1dd3bc3a
    internal-label: Admin workspace
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
---

# How to include a team member in Support notifications

This article provides an explanation of how to include a team member to automatically receive Support updates via email notifications.

## Affected products and versions

* Adobe Commerce on cloud infrastructure, all [supported versions](https://www.adobe.com/content/dam/cc/en/legal/terms/enterprise/pdfs/Adobe-Commerce-Software-Lifecycle-Policy.pdf).

## Cause

* The team member has not been added to the [!DNL cloud project] with the necessary privileges.
* The team member doesn't have a Support account.

## Solution

1. Go to the **[!DNL Cloud Project URL]** (Example: `https://us-3.magento.cloud/projects/xxxxxx/edit`).
1. Verify whether the team member has been added to the project and is a [!DNL Project Admin].

If they have not been added to the project, you will need to add them as a [!DNL Project Admin] and grant [!DNL Shared Access]:

* [Manage user access](https://experienceleague.adobe.com/docs/commerce-cloud-service/user-guide/project/user-access.html) in our user guide.
* [Unable to add user to Adobe Commerce cloud project](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/troubleshooting/miscellaneous/unable-add-user-adobe-commerce-cloud-project.html) in our Commerce Knowledge Base.
* [Adobe Commerce Help Center User Guide: Shared Access](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/help-center-guide/magento-help-center-user-guide.html#shared-access) in our Commerce Knowledge Base.

If they have been added to the [!DNL cloud project], but don't have the [!DNL Project Admin role], update their [!DNL role] accordingly in [Manage user access](https://experienceleague.adobe.com/docs/commerce-cloud-service/user-guide/project/user-access.html).

If you wish to enable a team member to be a watcher on all cases opened for your organization, submit a [Support ticket](https://experienceleague.adobe.com/home?lang=en&support-tab=home#support).

## Related reading

[Former team members receive Adobe Commerce cloud notification emails](https://experienceleague.adobe.com/docs/commerce-knowledge-base/kb/troubleshooting/miscellaneous/former-teammembers-receive-cloud-notification-emails.html)
