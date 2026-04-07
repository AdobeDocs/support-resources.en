---
title: Manage policy templates in the Global Admin Console
description: Learn how global administrators can apply policy templates to any child organization, directly or indirectly from the organization where they are stored in the Global Admin Console.
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
exl-id: e4dc5c35-1323-4894-bd47-b31c61a864bc
---
# Manage policy templates in the Global Admin Console

**Applies to:** Enterprise

Learn how global administrators can apply policy templates to any child organization, directly or indirectly from the organization where they are stored in the Global Admin Console.

>[!NOTE]
>
>In the [Global Admin Console](https://helpx.adobe.com/enterprise/global-admin-console/adopt-global-administration.html), select an organization to edit, and navigate to the **Policy Templates** tab to streamline setup and facilitate consistent policy management across organizations.
>
> [Sign in to the Global Admin Console](https://global-admin-console.adobe.com/)

## How policy templates work

Policy Templates are stored with an organization and are visible to all global administrators of that organization. Once applied, the entries from the policy template are individually set in each organization. When a policy template is applied to an organization, each of the entries in the policy template are applied to the organization's policies, replacing existing policy values.

### Locked policy behavior

Updates to locked policies are only performed if the user applying the update is a global administrator of the organization indicated by the **[!UICONTROL Locked By]** icon of the policy being updated.

If the user applying the template has permission to unlock the policy, the policy locks take the values from the template applied (locked or unlocked). If the template indicates that the lock should be left as is, the value of the lock in the policy stays same as before.

### Important Note on saving

>[!NOTE]
>
>Unlike other changes made in the Global Admin Console, edits to policy templates take effect immediately without needing to go through the **[!UICONTROL Review Pending Changes - Submit]** process. However, to implement pending changes in organizations where the policy template is applied, [submission](https://helpx.adobe.com/enterprise/global-admin-console/execute-jobs.html) is required.

## Create a policy template

1. In the [Global Admin Console](https://global-admin-console.adobe.com/), select an organization to edit, then navigate to the **[!UICONTROL Policy Templates]** tab.
1. Select **[!UICONTROL Create Template]**.<br>
    ![Pic1](./assets/DXSKB-3209-1-ga_14.png)
    <br>
1. In the **[!UICONTROL Create Policy Template]** dialog box, enter the **name** and **description** for the policy template.<br>The name of the policy template can be a maximum of 100 characters.
1. Select the policies to include in the template.
1. Set values for the selected policies (see [Setting Policy Values](#setting-policy-values) below).
1. Select **Save**.

### Setting policy values {#setting-policy-values}

For each policy included in the template, configure two settings:

* **Allowed / Not Allowed:** Set the slider to the desired value. Learn about [policy details](https://helpx.adobe.com/enterprise/global-admin-console/update-policies.html#policy-details).
* **Lock value:** Modify the lock state of the policy using one of the following options:
  * **Lock** — The policy will be locked after application of the template.
  * **Unlock** — The policy will be unlocked after application of the template.
  * **Keep as is** — The lock state of the policy will be left the same as before the template was applied.<br>
    ![Pic2](./assets/DXSKB-3209-2-policy-template.png)
<br>

## Apply a template to organizations

1. In the [Global Admin Console](https://global-admin-console.adobe.com/), select an organization to edit, then navigate to the **[!UICONTROL Policy Templates]** tab.
1. Select the **[!UICONTROL More Options]** ![More Options](./assets/manage-product-profiles_more-options.png) icon for the relevant policy template, and select **[!UICONTROL Apply template to organization]**.<br>
    ![Pic3](./assets/DXSKB-3209-3-ga_15.png)
    <br>
1. Select the organizations to which you want to apply the template. You can select multiple organizations.<br>
    ![Pic4](./assets/DXSKB-3209-4-bulk-apply-template.png)
    <br>
1. Select **[!UICONTROL Apply template]**.
1. To implement pending changes in organizations where the policy template is applied, select **[!UICONTROL Review Pending Changes]**. After reviewing, select **[!UICONTROL Submit Changes]** to [execute](https://helpx.adobe.com/enterprise/global-admin-console/execute-jobs.html) them.

If all the policy values in the organizations you select already match the values in the template, a message appears notifying that no changes were made. Also, **[!UICONTROL Review Pending Changes]** isn't enabled if there are no other pending edits.

## Edit a template

1. In the [Global Admin Console](https://global-admin-console.adobe.com/), select an organization to edit, then navigate to the **[!UICONTROL Policy Templates]** tab.
1. Select the **[!UICONTROL More Options]** icon ![More Options](./assets/manage-product-profiles_more-options.png) for the relevant template, and select **[!UICONTROL Edit template]**.<br>
    ![Pic5](./assets/DXSKB-3209-5-ga_15-1.png)
    <br>
1. Update the policy template and select **[!UICONTROL Update Now]**.
1. To implement pending changes in organizations where the policy template is applied, select **[!UICONTROL Review Pending Changes]**. After reviewing, select **[!UICONTROL Submit Changes]** to [execute](https://helpx.adobe.com/enterprise/global-admin-console/execute-jobs.html) them.

## Delete a template

1. In the [Global Admin Console](https://global-admin-console.adobe.com/), select an organization to edit, then navigate to the **[!UICONTROL Policy Templates]** tab.
1. Select the **[!UICONTROL More Options]** ![More Options](./assets/manage-product-profiles_more-options.png) icon for the relevant template, and select **[!UICONTROL Delete Template]**.<br>
    ![Pic6](./assets/DXSKB-3209-6-ga_15-2.png)
    <br>
1. Select *Yes* in the dialog box that appears.
