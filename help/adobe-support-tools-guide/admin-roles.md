---
title: Administrative Roles
description: Using the Adobe Admin Console, organizations can define a flexible administrative hierarchy that enables fine-grained management of Adobe product access and usage.
---
# Administrative Roles

Using the [!DNL Adobe Admin Console], organizations can define a flexible administrative hierarchy that enables fine-grained management of Adobe product access and usage. One or more System admins, provisioned during the enterprise onboarding process, sit at the top of the hierarchy. These System admins can delegate responsibilities to other admins, while still retaining overall control.

Administrative Roles provide the following key benefits to enterprises:

* Controlled decentralization of administrative responsibilities
* Quick view of product assignments—by user and by product
* Functionality to assign quotas to Product admins

## Administrative hierarchy

Applies to: Adobe enterprise customers.

The administrative hierarchy can be used to suit the unique requirements of your enterprise. For example, an enterprise can appoint different admins to manage entitlements to [!DNL Adobe Creative Cloud] and [!DNL Adobe Marketing Cloud] offerings. Alternatively, an enterprise can have different admins to manage entitlements of users belonging to different business units.

>[!NOTE]
>
>The administrative hierarchy doesn't apply to teams customers. Teams customers have a single **System admin** role. The contract owner (_previously referred to as **Primary admin**_) is the system administrator with access to the contract details and the billing history. If you are the current contract owner, you can nominate an existing system administrator (_previously referred to as **secondary admin**_) as the contract owner.

![admin image](assets/storage_admin.png)

_Admin roles hierarchy_

|Role | Description |
|--- |--- |
|**System Admin**| Super user for the organization; allowed to perform all administrative tasks in the [!DNL Admin Console].<br>Also, has permissions to delegate the following administrative functionality to other users: Product admin, Product Profile admin, User Group admin, Deployment admin, and Support admin.|
|**Product Admin**| Administers the products assigned to that admin and all associated administrative functions, which include:<ul><li>Create product profiles</li><li>Add users and user groups to the organization but not remove these</li><li>Add or remove users and user groups from product profiles</li><li>Add or remove Product Profile admins from product profiles</li><li>Add or remove other product admins from the product</li><li>Add or remove Group admins from groups</li></ul>|
|**Product Profile Admin**| Administers the Product Profile descriptions assigned to that admin and all associated administrative functions, which include:<ul><li>Add users and user groups to the organization but not remove these</li><li>Add or remove users and user groups from product profiles</li><li>Assign or revoke product permissions to users and user groups from product profiles</li><li>Manage product roles of users and user groups for product profiles|
|**User Group Admin**| Administers the user group descriptions assigned to that admin and all associated administrative functions, which include:<ul><li>Add or remove users from groups</li><li>Add or remove User Group admins from groups|
|**Deployment Admin**| Creates, manages, and deploys software packages and updates to end users.|
|**Support Admin**| Non-administrative role that has access to support-related information, such as customer-reported issue reports.|
|**Storage Admin**| Manages the storage administration of the organization. The administrator can view storage consumption of both active and inactive users and transfer contents to other recipients.|

For a detailed list of permissions and privileges for each admin role, see [Permissions](#enterprise-admins-permissions-matrix).

## Add an enterprise admin role {#add-enterprise-role}

Applies to: Adobe enterprise customers.

As an admin, you can assign an admin role to other users, giving them the same privileges as you have, or privileges for a role under your admin role in the hierarchy as described [above](#administrative-hierarchy). For example, as a Product admin you can give Product admin privileges or Product Profile admin privileges to a user, but not Deployment admin privileges. For the permissions on the Admin Console, see the [Permissions matrix](#enterprise-admins-permissions-matrix).

To add or invite an admin:

1. In the **[!UICONTROL [!DNL Admin Console]](https://adminconsole.adobe.com/)**, choose **[!UICONTROL Users]** > **[!UICONTROL Administrators]**.
 
   Alternatively, go to the relevant Product, Product Profile, or User Group and navigate to the **[!UICONTROL Admins]** tab.

1. Click **[!UICONTROL Add Admin]**.
1. Enter a name or email address. You can search for existing users or add a new user by specifying a valid email address, and filling the information on the screen.
1. Click **[!UICONTROL Next]**. A list of admin roles appears.

    >[!NOTE]
    >
    >* The options on this screen depend on your account and admin role. You can either give the same privileges as you have, or privileges for a role under yours in the hierarchy.
    >* As the System Admin of a team, you can assign only one admin role: System Admin.

1. Select one or more admin roles.
1. For Admin types like Product Administrator, Product Profile Administrator, and User Group Administrator, select the specific products, profiles, and groups respectively.

    >[!NOTE]
    >
    >For a Product Profile Administrator, you can include profiles for more than one product.

    ![add admin](assets/add-admin.png)

1. Review the admin roles assign to the user and click **Save**.

The user receives an email invitation regarding the new administrative privileges from `message@adobe.com`.

Users must click **[!UICONTROL Get started]** in the email to join the organization. If new admins don't use the **[!UICONTROL Get started]** link in the email invitation, they would not be able to sign into the Admin Console. 

As part of the sign-in process, users may be asked to set up an Adobe profile if they do not have one already. If users have multiple profiles associated with their email address, users must choose "Join Team" (if prompted) and then select the profile associated with the new organization.

![admin rights image](assets/admin-get-started-email.png)

## Add a teams admin {#add-admin-teams}

Applies to: Adobe teams customers.

As an admin, you can assign the System admin role to other users, giving them the same privileges as you have. 

To add or invite a System admin:

1. In the **[!UICONTROL [!DNL Adobe Admin Console]]**, choose **[!UICONTROL Users]** > **[!UICONTROL Administrators]**.

   A list of existing admins displays.

1. Click **[!UICONTROL Add Admin]**.

   The **[!UICONTROL Add an Administrator]** screen displays.

1. Enter a name or email address. You can search for existing users or add a new user by specifying a valid email address, and filling the information on the screen.

   By default, System Administrator is selected. 

1. Click **[!UICONTROL Save]**.

![teams admin image](assets/teams-admin.png)

Since all users in a teams organization are Business ID users, they receive an email invitation regarding the new adminstrative privileges from `message@adobe.com`.
Users must click Get started in the email to join the organization.

As part of the sign-in process, users may be asked to set up an Adobe profile if they do not have one already. If users have multiple profiles associated with their email address, users must choose "Join Team" (if prompted) and then select the profile associated with the new organization.

![admin rights image](assets/admin-get-started-email.png)

## Edit enterprise admin role

Applies to: Adobe enterprise customers.

As an admin, you can edit the admin role to other admin that are below you in the Administrative hierarchy. For example, you can remove admin privileges of other admins.

To edit admin roles:

1. In the **[!UICONTROL [!DNL Adobe Admin Console]]**, choose **[!UICONTROL Users]** > **[!UICONTROL Administrators]**. The list of existing admins displays.

   Alternatively, go to the relevant Product, Product Profile, or User Group and navigate to the **[!UICONTROL Admins]** tab.

1. Click the name of the admin to edit.
1. In the **[!UICONTROL User Details]**, click ![icon](assets/one-console-ellipses.png) for the **Administrative Rights** section and choose **[!UICONTROL Edit admin rights]**.

   ![edit admin rights](assets/admin-rights-section.png)

1. Edit the administrative rights and save your changes.

## Edit teams admin role

Applies to: Adobe teams customers.

As a teams System admin, you can remove the System admin privileges of other admins.

To revoke System admin privileges:

1. In the **[!UICONTROL [!DNL Adobe Admin Console]]**, choose **[!UICONTROL Users]** > **[!UICONTROL Administrators]**.

   The list of existing admins displays.

1. In the **[!UICONTROL User Details]**, click ![icon](assets/one-console-ellipses.png) to the right of the **[!UICONTROL Administrative Rights]** section and choose **[!UICONTROL Edit admin rights]**.

   ![edit admin rights](assets/admin-rights-section.png)

1. Edit the administrative rights and save your changes.

## Remove an admin

Applies to: Adobe teams enterprise customers.

To revoke admin permissions, select a user and then click **[!UICONTROL Remove Admin]**.

![remove admin image](assets/remove-admin.png)

>[!NOTE]
>
>Removing an admin does not delete the user from the Admin Console, but only removes the privileges associated with the admin role.

## Enterprise admins permissions matrix

Applies to: Adobe enterprise customers.

The following table lists all the permissions for the different types of admins, categorized by the following areas of functionality:

### Identity management

|Permission | System admin | Support admin |
|--- |--- |--- |
|Add domain (request/claim a domain) | ✔ | |
|View domain and domain listing | ✔ | |
|Manage domain encryption keys | ✔ | |
|Manage default org password policy | ✔ | |
|View default org password policy | ✔ | |

### User management

|Permission | System admin | Support admin |
|--- |--- |--- |
|Add user to org | ✔ | |
|Remove user from org | ✔ | |
|View user details and listing | ✔ | |
|Edit user profile | ✔ | |
|Add Product Profile to user or group | ✔ | |
|Remove Product Profile to user or group | ✔ | |
|Add Product Profile to multiple users | ✔ | |
|View product profiles for a user | ✔ | |
|View product user listing | ✔ | |
|Bulk add users to org | ✔ | |

### Administrator management

|Permission | System admin | Support admin |
|--- |--- |--- |
|Grant Org Admin to a user | ✔ | |
|Revoke Org Admin from a user | ✔ | |
|Grant Product License Admin to a user | ✔ | |
|Revoke Product License Admin from a user | ✔ | |
|Grant Deployment Admin to a user | ✔ | |
|Revoke Deployment Admin from a user | ✔ | |
|Grant user group admin to a user | ✔ | |
|Revoke user group admin from a user | ✔ | |
|Grant product owner admin to a user | ✔ | |
|Revoke product owner admin from a user | ✔ | |

### Product license configuration management

|Permission | System admin | Support admin |
|--- |--- |--- |
|Grant product entitlement to org | | |
|Remove product entitlement from org | | |
|View total number of licenses owned by the org | ✔ | |
|View available products and product families | ✔ | |
|Edit product license descriptions/data | ✔ | |
|Provision product license to a user | ✔ | |
|Deprovision product license from a user | ✔ | |
|Add new product license configuration | ✔ | |
|Edit product license service configuration | ✔ | |
|Delete product license service configuration | ✔ | |
|Remove product access from a user (strip from all configs) | ✔ | |

### Storage management

|Permission | System admin | Support admin |
|--- |--- |--- |
|View Active and Inactive user folders | ✔ | |
|Delete Inactive user folders and transfer content | ✔ | |

### Deployment

|Permission | System admin | Support admin |
|--- |--- |--- |
|View/use Packages tab | ✔ | |

### Support

|Permission | System admin | Support admin |
|--- |--- |--- |
|View support tab | ✔ | |
|Manage support cases | ✔ | ✔ |

### User group management

|Permission | System admin | Support admin |
|--- |--- |--- |
|Create user group | ✔ | |
|Remove user group | ✔ | |
|Add user to user group | ✔ | |
|Remove user from user group | ✔ | |
|Assign user group to product license | ✔ | |
|Remove user group from product license | ✔ | |
|View member of user group | ✔ | ✔ |
|View list of user groups | ✔ | ✔ |