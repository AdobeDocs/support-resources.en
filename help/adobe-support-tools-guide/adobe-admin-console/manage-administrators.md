---
title: Manage administrators
description: How Adobe customers can set up and manage administrators in the Global Admin Console to control user access, product licenses, and organizational resources.
feature-set: Experience Cloud Services
solution: Admin Console
feature: Admin Console
---

# Manage administrators  

*Applies to enterprise.*

Explore global administrator capabilities and learn how to delegate and distribute the administration of users, product licenses, and groups to admins for each individual organization.

In the **Global Admin Console**, select an organization and navigate to the **Admins** tab to add, edit, or remove admin rights.  
https://global-admin-console.adobe.com/

The Global Admin Console introduces a role—the **global administrator**—that is distinct from a system administrator and allows you to:

- View the global landscape of total Adobe investment across Admin Consoles in the hierarchy.
- Monitor Adobe license and resource assignments and usage across multiple Admin Consoles.
- Create Admin Consoles or organizations.
- Allocate product licenses from a root or parent Admin Console to child Admin Consoles.
- Maintain day-to-day operations while system admins continue managing their Admin Consoles.
  - For example, a global admin can allocate a product to a child Admin Console but cannot assign it to users. The system admin assigns products to users.
- Optionally apply organizational policies to Admin Consoles in the hierarchy.

## Fundamental administrative tasks

The Global Admin Console is designed to work across multiple organizations and Admin Consoles. The following table outlines where administrative tasks can be completed.

<table>
  <tr>
    <th>Task</th>
    <th>Scope</th>
  </tr>
  <tr>
    <td rowspan="2">Manage administrators</td>
    <td>For one or more organizations</td>
  </tr>
  <tr>
    <td>For one organization</td>
  </tr>
</table>

<table>
  <thead>
    <tr>
      <th>Task</th>
      <th>Global Admin Console</th>
      <th>Admin Console</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Create, reparent, and delete child organizations</td>
      <td>Yes</td>
      <td>No</td>
    </tr>
   <tr>
     <td>Work with multiple organizations</td>
     <td></td>
   </tr><tr><td rowspan="2">Manage administrators</td>
     <td>For one or more organizations</td>
    <tr>
      <td>Manage Product Profiles and user groups</td>
      <td>Yes</td>
      <td>No</td>
    </tr>
    <tr>
      <td>Define and manage policies</td>
      <td>Yes</td>
      <td>No</td>
    </tr>
    <tr>
      <td>Allocate products across organizations</td>
      <td>Yes</td>
      <td>No</td>
    </tr>
    <tr>
      <td>Allocate products to users</td>
      <td>No</td>
      <td>Yes</td>
    </tr>
    <tr>
      <td>Manage users</td>
      <td>No</td>
      <td>Yes</td>
    </tr>
    <tr>
      <td>Manage packages</td>
      <td>No</td>
      <td>Yes</td>
    </tr>
    <tr>
      <td>Set up domains and directories</td>
      <td>No</td>
      <td>Yes</td>
    </tr>
    <tr>
      <td>Manage enterprise storage and encryption</td>
      <td>No</td>
      <td>Yes</td>
    </tr>
  </tbody>
</table>

## Administrator roles

You can create a flexible administrative hierarchy for fine-grained management of Adobe product access and usage.

The Global Admin Console allows you to add:

- System admins
- Product admins
- Product profile admins
- User group admins
- Deployment admins
- Support admins
- Storage admins

These admins can perform administrative tasks only within the organizations they administer.

Two additional roles are available for global administration:

- **Global Admin**
- **Global Viewer**

## Global Admin role

The **Global Admin** role is transitive:

- Assigning a user as a global admin of an organization automatically assigns them to all child organizations.
- When a new organization is created, global admins of parent organizations automatically gain access.

### Global Admin capabilities

- Create and delete child organizations
- Set and edit policies
- Set and modify administrative roles
- Add and remove products in child organizations
- Set or change resource allocations for child organizations
- Manage Product Profiles and User Groups

## Global Viewer role

### Global Viewer capabilities

- View user groups, products, product profiles, administrators, policies, and resources in the organization and its child organizations

## Distributed administration

By managing administrators, a global admin can delegate administration of users, product licenses, and groups to individual organizations.

- Admins manage their organizations independently.
- They have no visibility into other organizations.
- User and resource data remains isolated.

A global admin can:

- Create organizations
- Distribute products and storage
- Manage identity setup
- Create and apply organization policy templates

A system admin added by a global admin can:

- Assign products to users
- Onboard users
- Create and manage product profiles
- Perform other organization-level administrative tasks

## Add an admin

1. In the Global Admin Console, select an organization and navigate to the **Admins** tab.
2. Select **Add Admin**.
3. In the **Add Admin** dialog box, enter:
   - Email
   - First Name
   - Last Name
   - Account Type
   - Country Code


   > [!NOTE]
   >
   > When adding an existing user, select the same account type as the existing user or the operation fails.

   Organizations cannot contain both **AdobeID** and **BusinessID** users simultaneously.  
   https://helpx.adobe.com/enterprise/global-admin-console/update-policies.html

4. Select one or more roles under **Admin Rights**.
   - For product, product profile, or user group admin roles, select the relevant products, profiles, or groups.
5. Select **Save**.
6. Select **Review Pending Changes**, then **Submit Changes**.  
   https://helpx.adobe.com/enterprise/global-admin-console/execute-jobs.html

After the admin is added:

- The user receives an email notification.
- The user receives an invitation to accept the role.
- If assigned both global admin and another role, two invitations are sent.

## Edit an admin

1. Select an organization and go to the **Admins** tab.
2. Select **More Options** for the admin and choose **Edit Admin**.
3. Update the admin details and select **Save**.
4. Select **Review Pending Changes**, then **Submit Changes**.

Each role change appears as a separate pending item.

## Remove admin rights

1. Select an organization and navigate to the **Admins** tab.
2. Select **More Options** for the admin and choose **Remove Admin Rights**.
3. Select **OK** to confirm.
4. Select **Review Pending Changes**, then **Submit Changes**.

After removal, the admin receives an email notification that access has been revoked.
