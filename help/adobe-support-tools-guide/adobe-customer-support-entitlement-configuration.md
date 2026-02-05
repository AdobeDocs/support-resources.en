---
title: Adobe customer support entitlement configuration
description: How Adobe customers can set up and manage support entitlements in the Admin Console so users can access support resources, submit issues, and manage case activity.
feature-set: Experience Cloud Services
solution: Admin Console
feature: Admin Console
exl-id: 75b0e812-da38-46af-94b6-7b7db8954be3
---
# Adobe customer support entitlement configuration

To configure support entitlements for your organization, first add or invite the user through the Admin Console.

## Adding support entitlement roles to an organization

The **[!UICONTROL Support administrator]** role is a non-administrative role that has access to support-related information. A **[!UICONTROL Support administrator]** can view, create, and manage issue reports.

To add or invite an admin:

1. In the Admin Console, choose **[!UICONTROL Users]** > **[!UICONTROL Administrators]**.
1. Click **[!UICONTROL Add Admin]**.
1. Enter a name or email address.

   You can search for existing users or add a new user by specifying a valid email address and filling the information on the screen.

   ![Add admin](assets/admin-console-add-admin.png)

1. Click **[!UICONTROL Next]**. A list of admin roles appears.

To assign a **[!UICONTROL Support administrator]** role to a user (enable a user to be able to contact support):

1. Select the **[!UICONTROL Support administrator]** option.

   ![Edit admin rights](assets/edit-admin-rights.png)

1. Choose one of the following two options:

   * Option 1: **[!UICONTROL Basic support administrator]**. Select this option if you would like to give the user support access for all solutions (except Marketo Engage).
   * Option 2: **[!UICONTROL Product support administrator]**: Select this option for Marketo Engage support. Select which Marketo Engage instances to give the user support access.

   ![Edit admin rights Marketo](assets/edit-admin-rights-advanced.png)

1. Once you have made the selections, click **[!UICONTROL Save]**.

The user receives an email invitation regarding the new administrative privileges from `message@adobe.com`.

Users must click **[!UICONTROL Get started]** in the email to join the organization. If new admins do not use the **[!UICONTROL Get started]** link in the email invitation, they would not be able to sign into the Admin Console.

As part of the sign-in process, users may be asked to set up an Adobe profile if they do not have one already. If users have multiple profiles associated with their email address, users must choose **[!UICONTROL Join Team]** (if prompted) and then select the profile associated with the new organization.

![Admin rights confirmation](assets/admin-rights-confirmation.png)

For more details refer to [Edit enterprise admin role](admin-roles.md#edit-enterprise-admin-role) instructions in the administrative roles documentation. Note that only a system administrator for your organization can assign this role. For more information on administrative hierarchy, visit the [Administrative roles](admin-roles.md) documentation.
