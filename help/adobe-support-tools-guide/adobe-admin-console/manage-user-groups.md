---
title: Manage User Groups in the Global Admin Console
description: Learn how to create, share, edit, and delete user groups in the Global Admin Console to streamline user management across organizations.
feature-set: Experience Cloud Services
solution: Admin Console
feature: Admin Console
---

# Manage User Groups in the Global Admin Console

Create, manage, and share user groups in the [!DNL Global Admin Console] to streamline user management by grouping users with the same permissions, saving time, and ensuring consistency.

In the [Global Admin Console](https://helpx.adobe.com/enterprise/global-admin-console/adopt-global-administration.html), select an organization, and navigate to **[!UICONTROL User Groups]**. Share groups across multiple organizations using a single user management source to sync users and groups.

[Sign in to the Global Admin Console](https://global-admin-console.adobe.com)



## Create User Groups

You can either [create user groups](https://helpx.adobe.com/enterprise/using/user-groups.html) individually, in bulk, or [directly sync them from an established Azure AD](https://helpx.adobe.com/enterprise/using/add-azure-sync.html) to a federated directory in the [!DNL Adobe Admin Console]. In the [!DNL Global Admin Console], you can define user groups with relevant product profiles assigned, to which the user group admins can later add users using the [!DNL Admin Console].

1. Sign in to the [Global Admin Console](https://global-admin-console.adobe.com/), select an organization to edit, and then navigate to the **[!UICONTROL User Groups]** tab.

2. Select **[!UICONTROL Add User Group]**.

   ![Organizations tab in the Global Admin Console with the user Groups tab selected.](assets/add-user-group.png "Add user group")

   _Add user groups to an organization to streamline user management._

3. Enter the following in the **[!UICONTROL Add User Group]** dialog box that appears:
   - **[!UICONTROL Name]**: Specify a name for the user group.
   - **[!UICONTROL Product Profiles]**: If you want to grant product access to the current or future members in the user group, click the drop-down arrow to select a Product Profile from the list, or enter the Product Profile name and select it from the drop-down list that displays. If you want to add a product profile that hasn't already been created, you must first do that using the [Product Profiles](https://helpx.adobe.com/enterprise/using/global-admin-edit-organizations.html#profiles) tab.
   - **[!UICONTROL Admins]**: Click the drop-down arrow to select an admin from the list, or enter the admin's email address and select it from the drop-down list that displays. If you want to add a new admin that hasn't already been created, you must first do that using the [Admins](#share-user-groups) tab.

   The product profiles you specify are assigned to the User Group, and the admins you specify become the user group admins for the group. The user group admins can use the [!DNL Adobe Admin Console] for the relevant organization to manage the group.

4. Select **[!UICONTROL Save]**.

5. Select **[!UICONTROL Review pending changes]** to review the updates. Then, select **[!UICONTROL Submit changes]** to [execute](https://helpx.adobe.com/enterprise/global-admin-console/set-up-organizations.html#execute-jobs) them.

>[!NOTE]
>
>Global admins can [assign product profiles and user group admins](#review-user-groups) to the user groups using the [!DNL Global Admin Console]. Using the [!DNL Adobe Admin Console], system admins and user group admins can [add users and assign admins and product profiles](https://helpx.adobe.com/enterprise/using/user-groups.html) to the user group.



## Share User Groups

Group projection allows you to sync user groups and their associated users from a single management source to multiple [!DNL Admin Consoles]. Global administrators can share user groups with hierarchical descendants of the source organization, working downward, not upward or side-to-side.

1. Sign in to the [Global Admin Console](https://global-admin-console.adobe.com/), select an organization, and navigate to the **[!UICONTROL User Groups]** tab.

2. Select the checkboxes for the user groups you want to share.

   Groups might be disabled for sharing in the following cases:
   - The user group is shared from another organization. To share or edit the group, select the organization that owns it from the organization hierarchy.
   - The organization isn't using [Adobe storage for business](https://helpx.adobe.com/in/enterprise/using/storage-for-business.html), which is being rolled out globally in phases.
   - The organization policy is disabled. Go to the **[!UICONTROL Policies]** tab to turn on the **[!UICONTROL Manage shared user groups]** policy.
   - The organization doesn't have any child organizations to share user groups with.

3. Select **[!UICONTROL Share user group]**.

4. <a id="review-user-groups"></a>Review the user groups to share with other organizations. If you are also a system admin in the selected organization, select the **[!UICONTROL Open in Admin Console]** <img src="assets/icon-open-in-admin-console.png" alt="Open in Admin Console icon" width="14" height="14"> icon to review the list of the user group members in the [!DNL Adobe Admin Console].

   >[!NOTE]
   >
   >To prevent conflicts, ensure that the organizations with which you plan to share user groups don't already have groups with the same name.

5. Select **[!UICONTROL Next]**.

6. Select the organizations to share user groups with and select **[!UICONTROL Next]**.

7. If there are no conflicts, select **[!UICONTROL Share User Groups]**.

   If there are conflicts (where user groups with the same name exist in the target organization), choose one of the following options and then select **[!UICONTROL Share User Groups]**:
   - **[!UICONTROL Ignore (default)]**: Skip the groups in the target orgs with the same name.
   - **[!UICONTROL Add only]**: Merge the user groups by adding new users to the existing user groups without removing any users.
   - **[!UICONTROL Mirror group]**: Adjust the target organization's groups to match the shared group by adding or removing users.

8. Select **[!UICONTROL Review pending changes]** to review the updates. Then, select **[!UICONTROL Submit changes]** to [execute](https://helpx.adobe.com/enterprise/global-admin-console/set-up-organizations.html#execute-jobs) them.

   Group projection events are logged for your reference. Learn to [view and download audit logs](https://helpx.adobe.com/enterprise/global-admin-console/insights.html).


When you share a user group, the group and its users are added to the target organization. However, the *source user group controls* the shared user groups and their users. Admin and product profile assignments are *not* synchronized between organizations.

Changes in the projected user group's name or associated users in the source user group are automatically updated in the target organization. While the shared user group cannot be managed directly, an admin within the target organization can assign product profiles to a shared group, giving license access to the group's users.



## Revoke access to Shared Groups

1. Sign in to the [Global Admin Console](https://global-admin-console.adobe.com/), select an organization, and navigate to the **[!UICONTROL User Groups]** tab.

2. Select **[!UICONTROL Manage shared access]** for the relevant user group.

3. Select the organizations you want to revoke access from.

4. Select **[!UICONTROL Revoke access]**.

5. While revoking access, you can choose to either delete the user group and users or leave a copy in the target organizations:
   - On deleting, the user group is removed from the target organizations. Users who are not members of other shared groups are also removed, losing access to all products, services, and assets.
   - On leaving a copy, the user group and users remain in the target organizations keeping all assignments intact. However, the user group will no longer be synced and can be managed by the administrators of the target organizations.

6. Select **[!UICONTROL Revoke access]**.

7. Select **[!UICONTROL Review pending changes]** to review the updates. Then, select **[!UICONTROL Submit changes]** to [execute](https://helpx.adobe.com/enterprise/global-admin-console/set-up-organizations.html#execute-jobs) them.



## Edit User Groups

1. Sign in to the [Global Admin Console](https://global-admin-console.adobe.com/), select an organization, and navigate to the **[!UICONTROL User Groups]** tab.

2. Select the **[!UICONTROL More Options]** icon for the relevant user group, and select **[!UICONTROL Edit User Group]**.

   >[!NOTE]
   >
   >You can't edit user groups that the selected organization doesn't own.

   ![An organization selected with the edit user group option highlighted under user groups tab.](assets/edit-user-group.png "Edit user group")

   _Edit the user groups to update the user group name, product profiles, or admins._

3. Update the user group name, product profiles, or admins. Then, select **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >In the **[!UICONTROL Edit User Group]** wizard, you can assign admin roles only to users who already have an admin role assigned in this organization. Learn how to [add new administrators](https://helpx.adobe.com/enterprise/global-admin-console/manage-admins.html).

4. Select **[!UICONTROL Review pending changes]** to review the updates. Then, select **[!UICONTROL Submit changes]** to [execute](https://helpx.adobe.com/enterprise/using/global-admin-set-up-organizations.html#execute-jobs) them.

>[!NOTE]
>
>If you change the name of a shared user group, the changes are automatically updated in the target organization.



## Delete User Groups

1. Sign in to the [Global Admin Console](https://global-admin-console.adobe.com/), select an organization, and navigate to the **[!UICONTROL User Groups]** tab.

2. Select the **[!UICONTROL More Options]** <img src="assets/icon-more-options.png" alt="More Options icon" width="14" height="14" style="vertical-align:middle"> icon for the relevant user group, and select **[!UICONTROL Delete User Group]**.

   >[!NOTE]
   >
   >You can't delete user groups that the selected organization doesn't own.

3. Select **[!UICONTROL Ok]** in the dialog box that appears.

   >[!CAUTION]
   >
   >Deleting a user group can impact your users. Ensure that there is no access or information that will be lost when the user group is deleted.

4. After you have edited the organizations, select **[!UICONTROL Review pending changes]** to review them. Then, select **[!UICONTROL Submit changes]** to [execute](https://helpx.adobe.com/enterprise/using/global-admin-set-up-organizations.html#execute-jobs) them.
