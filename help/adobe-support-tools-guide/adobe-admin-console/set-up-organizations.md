---
title: Manage organization hierarchy
description: Learn how global administrators can manage the organization’s hierarchy in the Global Admin Console.
Feature-set: Experience Cloud Services
Solution: Admin Console
Feature: Admin Console
---
# Manage organization hierarchy

After you gain [access to the [!DNL Global Admin Console]](https://helpx.adobe.com/enterprise/global-admin-console/adopt-global-administration.html#request-access), you can create new organizations, add existing organizations to the hierarchy, delete organizations, and change a parent organization.
[Sign in to the Global Admin Console](https://global-admin-console.adobe.com/)

An organization is a structure used to manage Adobe products and users. The [[!DNL Adobe Admin Console]](https://helpx.adobe.com/enterprise/using/admin-console.html) lets administrators manage the deployment and configuration of products and users in their organization. The [[!DNL Global Admin Console]](https://helpx.adobe.com/enterprise/global-admin-console/overview.html) lets global administrators create, manage, and delete multiple orgs.

## Create a child organization

As a [global administrator](https://helpx.adobe.com/enterprise/global-admin-console/manage-administrators.html), you can create child organizations of any organization in the hierarchy and set the name, country, user groups, products, product profiles, administrators, and policies.

When a new child organization is created, the following are automatically inherited from the immediate parent:

- Organization's [policy](https://helpx.adobe.com/enterprise/global-admin-console/update-policies.html) settings (including locks if present).
- The list of system administrators (controlled by the **[!UICONTROL Inherit System Admins on creation]** [policy](https://helpx.adobe.com/enterprise/global-admin-console/update-policies.html)). 
The following can prevent system administrators from being inherited:
  - Lack of [domain trust](https://helpx.adobe.com/enterprise/using/directory-trust.html).
  - User type restrictions (Add Adobe ID/ Enterprise ID/ Federated ID users policies). Learn about the [policy details](https://helpx.adobe.com/enterprise/global-admin-console/update-policies.html).
- Access to [[!DNL Federated ID]] or [[!DNL Enterprise ID]] users from domains to which the parent org has access. This makes the domain users in the parent available in the child org. Inheritance of user access is controlled by **Inherit users from directories managed by the parent organization** [policy](https://helpx.adobe.com/enterprise/global-admin-console/update-policies.html).
- Sharing policy, password policy, and security contacts (controlled by **Inherit asset sharing settings when child organization is created** [policy](https://helpx.adobe.com/enterprise/global-admin-console/update-policies.html)).

1. Sign in to the [Global Admin Console](https://global-admin-console.adobe.com/). In the **[!UICONTROL Organizations]** tab, select the organization you want to add a child organization to.
2. Select the **[!UICONTROL Add+]** icon.
   ![Add Organization](/help/adobe-support-tools-guide/assets/add-an-organization-1.png)
3. Specify a **name** and the **country** of the organization.  
   The organization's simple name must be between 4 and 100 characters; maximum length for pathname is 255 characters.
   ![Add child Organization](/help/adobe-support-tools-guide/assets/add-an-child-organization.png)
4. Select **[!UICONTROL Save]**.
5. Select **[!UICONTROL Review Pending Changes]** after you are done editing the organizations. After reviewing, select **[!UICONTROL Submit Changes]** to [execute](https://helpx.adobe.com/enterprise/global-admin-console/execute-jobs.html) them.

## Delete a child organization

As a [global administrator](https://helpx.adobe.com/enterprise/global-admin-console/manage-administrators.html), you can delete child organizations. The delete operation cannot be undone, and the root organization cannot be deleted. The resources allocated to the deleted organization are returned to its parent organization. Before an organization is deleted, its parent automatically becomes the parent of any of its child organizations.

An organization can be deleted only if the following criteria are met:

- There are no Sign accounts, Adobe Stock purchases, or storage repositories in the organization.
- There are no claimed domains in the organization.
- There are no instantiated products in the organization.
- There are no Experience Cloud products that can include instantiations in the organization.

>[!WARNING]
>
>Deleting an organization impacts your users. Ensure that there is no access or information that will be lost when an organization is deleted.

1. Sign in to the [[!DNL Global Admin Console]](https://global-admin-console.adobe.com/). Go to the **[!UICONTROL Organizations]** tab and select the organization you want to delete.
1. Select the **[!UICONTROL Delete]** icon.
   ![Delete organization](/help/adobe-support-tools-guide/assets/delete-organization.png)
1. In the **[!UICONTROL Delete Organization]** dialog box, select **[!UICONTROL OK]**.
1. Select **[!UICONTROL Review Pending Changes]** after you are done editing the organizations. After reviewing, select **[!UICONTROL Submit Changes]** to [execute](https://helpx.adobe.com/enterprise/global-admin-console/execute-jobs.html) them.

## Rename an organization

The organization name is the official name of your company or institution, set during purchase. Users see this name when selecting a profile during sign-in, especially if they have access to Adobe products from multiple organizations or need to choose between a business and personal profile.

As a [global administrator](https://helpx.adobe.com/enterprise/global-admin-console/manage-administrators.html), you can edit the name of any parent or child organization to help users identify the correct profile when signing in to [[!DNL Creative Cloud]] products and services.

1. Sign in to the [Global Admin Console](https://global-admin-console.adobe.com/). In the **[!UICONTROL Organizations]** tab, select the organization you want to rename.
1. Sign in to the [[!DNL Global Admin Console]](https://global-admin-console.adobe.com/). Go to the **[!UICONTROL Organizations]** tab and select the organization you want to rename.
1. Select the **[!UICONTROL Edit]** icon.
   ![Rename organization](/help/adobe-support-tools-guide/assets/rename-organization.png)
1. Update your organization name and select **[!UICONTROL Save]**.

**Tip**  
Use a clear, recognizable organization name up to 255 characters to help users select the correct profile. Avoid using special characters, and consider including region, department, or entitlement. Also, avoid uncommon acronyms and vague or similar names across your organization hierarchy.

Changes are logged in the audit log, all users are notified by email, and the name cannot be updated again for 24 hours. [Learn how to view and download audit logs](https://helpx.adobe.com/enterprise/global-admin-console/insights.html).

## Change the parent of an organization

As a [!DNL Global Administrator](https://helpx.adobe.com/enterprise/global-admin-console/manage-administrators.html), you can reparent an organization in the organization hierarchy using the **[!UICONTROL Change hierarchy]** button.

Changing the parent of an organization has the following impact:

- Reparenting an organization moves the entire subtree rooted at the reparented organization with it. The pathnames of the reparented organization and its children are updated to reflect their new location.
- Organization [policies](https://helpx.adobe.com/enterprise/global-admin-console/update-policies.html) of moved organizations are updated so that any locks on policies are held by an organization in the new hierarchy.
- Changing the position of an organization in the hierarchy can change the global administrators for that organization. Global administration roles are inherited down the hierarchy so any global administrators of the new parent organization automatically become global administrators of the moved organization. Likewise, global administrators can lose their role in the moved organization if they had that role by virtue of being a global administrator of the old parent. The inherited global administration roles are not listed in the Admins pane of the organization.
- Reparenting also affects the available products in the moved organizations. When possible, [product allocations](https://helpx.adobe.com/enterprise/global-admin-console/allocate-products.html) are updated so they come via the new parent location.
- If product allocations cannot be updated to come from the new parent, the products are removed along with the product profiles of those products. Users can lose access as a result of this operation. For the product to be available in the new location, the closest common ancestor of the old and new locations must have the product available.

**Caution**: If products are removed as a result of reparenting, users lose access to those products.

1. Sign in to the [Global Admin Console](https://global-admin-console.adobe.com/). In the **[!UICONTROL Organizations]** tab, select **[!UICONTROL Change hierarchy]** to enable reparenting the organizations.
2. Select **[!UICONTROL  OK]** in the pop-up screen that appears.
3. To reparent, drag the child organization on top of the desired organization.
4. Select **[!UICONTROL Save]** when you are done reparenting your organizations.
5. Select **[!UICONTROL Review Pending Changes]** after you are done editing the organizations. After reviewing, select **[!UICONTROL Submit Changes]** to [execute](https://helpx.adobe.com/enterprise/global-admin-console/execute-jobs.html) them.

Once the job is complete, you can navigate to Product Allocation and [change the grant values](https://helpx.adobe.com/enterprise/global-admin-console/allocate-products.html) to reflect the change in allocation of product resources.

## Add existing organizations using the Organization Mapper

As a [Global Administrator](https://helpx.adobe.com/enterprise/global-admin-console/manage-administrators.html), you can add existing organizations that are not currently part of your Global Admin Console hierarchy to the organization hierarchy.

You can also add team organizations to the org hierarchy. Team orgs don't participate in product allocation or product usage rollup, and management of team organizations in the Global Admin Console is limited. You can add them to the org hierarchy to keep track of them and have visibility into the products they purchase. Team organizations cannot have child organizations under them and don't have many of the features of enterprise organizations.

Learn more about the [limitations on product allocation](https://helpx.adobe.com/enterprise/global-admin-console/allocate-products.html#limitations).

**Caution**  
You can only add child organizations to root organizations that are based on the same storage model. So, child organizations based on the user storage model can only be added to root organizations based on the user storage model. And, child organizations based on the enterprise storage model can only be added to root organizations based on the enterprise storage model.

The **[!UICONTROL Organization Mapper]** tab shows the following:

1. A dropdown with a list of possible parent organizations where you can add a child organization. These are organizations for which you are a global administrator.
1. A list of child organizations that can be added under the parent selected in step 1. These are organizations for which you are a system administrator and that are not already a child of another organization.

When an organization is added to global administration, products in the organizations that are added using Organization mapper remain as purchases; [Product Allocation](https://helpx.adobe.com/enterprise/global-admin-console/allocate-products.html) numbers stop rollup at these organizations.

1. Sign in to the [Global Admin Console](https://global-admin-console.adobe.com/), and navigate to **[!UICONTROL Organization Mapper]**.
2. Select a parent organization from the drop-down list.  
   These are the organizations for which you are directly added as a global administrator. In the drop-down list, if you don't see an organization you want to use as the parent, select one higher up in the hierarchy. Once the Organization mapper operation is complete, you can use Change hierarchy to move the new organization down in the tree to have the parent you want to use.
3. Select the organizations to be added as children of the organization selected in the previous step.
4. Select **[!UICONTROL Review Pending Changes]**. Then, select **[!UICONTROL Submit Changes]** to [execute](https://helpx.adobe.com/enterprise/global-admin-console/execute-jobs.html) them.
5. After executing the changes, you can repeat the above steps to add additional child organizations to your organization hierarchy.

Once an organization is in the hierarchy, you can adjust organization policies, administrators, or other settings by navigating to the **[!UICONTROL Organizations]** tab.
