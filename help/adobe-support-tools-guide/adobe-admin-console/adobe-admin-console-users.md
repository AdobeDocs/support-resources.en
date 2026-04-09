---
title: Adobe Admin Console users
description: Plan your strategy for managing users on Adobe Admin Console — add admins and end users, choose a user management method, and assign licenses.
feature-set: Experience Cloud Services
solution: Admin Console
feature: Admin Console
---
# Adobe Admin Console users

Applies to enterprise & teams.

Facing one of these issues? Select an issue to view the resolution.

- [Manage Administrator roles](https://helpx.adobe.com/enterprise/using/admin-roles.html)
- [Download-install issues](https://helpx.adobe.com/download-install.html)
- [Reset Enterprise ID user password](https://helpx.adobe.com/enterprise/kb/enterprise-id-faq.html#faq)
- [Resolve Federated ID errors](https://helpx.adobe.com/enterprise/kb/tshoot-fed-id.html)
- [Delete user or restore deleted user](https://helpx.adobe.com/enterprise/using/manage-directory-users.html)

**Adobe Admin Console - Users** — [Watch on YouTube](https://youtu.be/w8b36YX2TEM)

## Why to add users to Adobe Admin Console

>[!NOTE]
>
>As an admin on the Adobe Admin Console, after you've chosen your [identity type](https://helpx.adobe.com/enterprise/using/identity.html) and [set up identity](https://helpx.adobe.com/enterprise/using/set-up-identity.html), your next task is to add users to the Admin Console.

Adobe enterprise and teams broadly defines two types of users:

### Administrators (admins)

Enterprise or teams admins perform administrative tasks on the Admin Console. You add admins to define a flexible administrative hierarchy that enables fine-grained management of Adobe product access, usage, and other administrative tasks.

All admins must be added to the Admin Console. When adding them, administrative privileges are based on their [administrative roles](https://helpx.adobe.com/enterprise/using/admin-roles.html).

### End users

End users are the users in your organization or institution who use the Adobe products and services that your organization or institution has obtained as part of the agreement with Adobe.

## Decide your user management strategy

Depending on your requirements, you add, remove, or update users *individually* or use one of the available *bulk upload methods*. Use the following matrix as a guide to plan your user management.

>[!NOTE]
>
>If you're a new Adobe enterprise or teams customer, we recommend that you go through this table before you start managing your users on the Admin Console. Existing customers can use this, especially if they're planning to migrate from one identity type to another (see [Edit identity type](https://helpx.adobe.com/enterprise/using/switch-user-identity.html)).

<table>
<thead>
<tr>
<th scope="col"></th>
<th scope="col"><strong>Individually (Admin Console)</strong></th>
<th scope="col"><strong>CSV Bulk upload (Admin Console)</strong></th>
<th scope="col"><strong>Azure / Google connectors</strong></th>
<th scope="col"><strong>User Sync Tool</strong></th>
<th scope="col"><strong>User Management REST API</strong></th>
</tr>
</thead>
<tbody>
<tr>
<th scope="row"><strong>Applies to</strong></th>
<td colspan="2">Adobe teams and enterprise customers</td>
<td colspan="3">Adobe enterprise customers</td>
</tr>
<tr>
<th scope="row"><strong>Description</strong></th>
<td>Manage users individually in the Admin Console.</td>
<td>Manage users with CSV file upload in the Admin Console.</td>
<td>Manage users (and groups) based on your existing Azure AD portal or Google federation.</td>
<td colspan="2">Manage users (and groups) based on your organization's LDAP.</td>
</tr>
<tr>
<th scope="row"><strong>Add users</strong></th>
<td><strong>Users</strong> tab in <strong>Admin Console</strong>. <a href="https://helpx.adobe.com/enterprise/using/manage-users-individually.html#add-users">Read more</a>.</td>
<td>Use <strong>Add users by CSV</strong> in <strong>Admin Console</strong>. <a href="https://helpx.adobe.com/enterprise/using/bulk-upload-users.html">Read more</a>. <em>(Use default CSV template.)</em></td>
<td>Add users in <a href="https://helpx.adobe.com/enterprise/using/sso-setup-azure.html">Azure</a> or <a href="https://helpx.adobe.com/enterprise/using/setup-sso-google.html">Google</a>. Or via <strong>Admin Console</strong>.</td>
<td colspan="2">Users should be added in your organization's LDAP.</td>
</tr>
<tr>
<th scope="row"><strong>Remove users</strong></th>
<td>Select and remove user in <strong>Admin Console</strong>. <a href="https://helpx.adobe.com/enterprise/using/manage-users-individually.html#remove-users">Read more</a>.</td>
<td>Choose <strong>Remove users by CSV</strong> in the <strong>Users</strong> tab of <strong>Admin Console</strong>. <a href="https://helpx.adobe.com/enterprise/using/bulk-upload-users.html#remove-users">Read more</a>. <em>(Use default CSV template.)</em></td>
<td>Users must be removed in <a href="https://helpx.adobe.com/enterprise/using/sso-setup-azure.html">Azure</a> or <a href="https://helpx.adobe.com/enterprise/using/setup-sso-google.html">Google</a>.</td>
<td colspan="2">Ensure that user information is in sync. <strong>Caution:</strong> Users not in your organization's LDAP are removed from Admin Console.</td>
</tr>
<tr>
<th scope="row"><strong>Edit user details</strong></th>
<td>Select the user and then <strong>Edit User Details</strong> in Admin Console. <a href="https://helpx.adobe.com/enterprise/using/manage-users-individually.html#edit-user-details">Read more</a>.</td>
<td>Choose <strong>Edit user details by CSV</strong> in the <strong>Users</strong> tab of <strong>Admin Console</strong>. <a href="https://helpx.adobe.com/enterprise/using/bulk-upload-users.html#edit-user-details">Read more</a>. <em>(Use default CSV template.)</em></td>
<td>All user information must be changed in <a href="https://helpx.adobe.com/enterprise/using/sso-setup-azure.html">Azure</a> or <a href="https://helpx.adobe.com/enterprise/using/setup-sso-google.html">Google</a>.</td>
<td colspan="2">Ensure that user information is in sync.</td>
</tr>
<tr>
<th scope="row"><strong>Supported Identity types</strong></th>
<td colspan="2">All</td>
<td>Federated ID</td>
<td colspan="2">Federated ID and Enterprise ID</td>
</tr>
<tr>
<th scope="row"><strong>Max. updates per operation</strong></th>
<td>10</td>
<td>25,000 (<em>5,000 for optimal performance</em>)</td>
<td colspan="3">Unlimited (Maps to your organization's LDAP)</td>
</tr>
<tr>
<th scope="row"><strong>Requires</strong></th>
<td>Adobe Admin Console</td>
<td>Creating and updating .csv file formats, preferably using Microsoft Excel</td>
<td>You must set up Azure AD or Google federation</td>

<td>
  <ul>
    <li>macOS Terminal or Windows Command Prompt</li>
    <li>Understanding of LDAP</li>
  </ul>
</td>

<td>Working knowledge of a programming language (such as Python) to consume REST APIs</td>
</tr>
<tr>
<th scope="row"><strong>Read more</strong></th>
<td><a href="https://helpx.adobe.com/enterprise/using/manage-users-individually.html">Manage individual users</a></td>

<td>
  <ul>
    <li>
      <a href="https://helpx.adobe.com/enterprise/using/bulk-upload-users.html">
        Manage users &#124; Bulk upload CSV
      </a>
    </li>
    <li>
      <a href="https://helpx.adobe.com/enterprise/kb/troubleshoot-bulk-user-csv-upload.html">
        Troubleshoot bulk user CSV upload
      </a>
    </li>
  </ul>
</td>

<td>
  <ul>
    <li>
      <a href="https://helpx.adobe.com/enterprise/using/sso-setup-azure.html">
        Azure AD Connector
      </a>
    </li>
    <li>
      <a href="https://helpx.adobe.com/enterprise/using/setup-sso-google.html">
        Google federation connector
      </a>
    </li>
  </ul>
</td>

<td>
  <ul>
    <li>
      <a href="https://adobe-apiplatform.github.io/user-sync.py/en/">
        About User Sync
      </a>
    </li>
    <li>
      <a href="https://github.com/adobe-apiplatform/user-sync.py">
        Git Repository
      </a>
    </li>
    <li>
      <a href="https://helpx.adobe.com/enterprise/using/user-sync.html">
        Step-by-step guide
      </a>
    </li>
  </ul>
</td>
<td><a href="https://developer.adobe.com/umapi/">About UMAPI</a></td>
</tr>
</tbody>
</table>

## Next steps

### Create packages

Once added, your users are ready to be assigned their designated apps and services.

Assign licenses to end users based on your licensing method:

- **Named User Licensing:** Add these users to **products** ([for teams](https://helpx.adobe.com/enterprise/using/assign-licenses-to-teams-users.html)) or **product profiles** ([for enterprises](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html)) to give them Adobe product and service entitlements. For more details, see how to [create Named User Licensing packages](https://helpx.adobe.com/enterprise/using/create-nul-packages.html) and [product profiles](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html#create-product-profile).
- **Shared Device Licensing:** [Added users](https://helpx.adobe.com/enterprise/using/sdl-deployment-guide.html#add-users-admin-console) can use the configured shared devices which are accessible by **Organization users only**. For more details, see [Create SDL Packages](https://helpx.adobe.com/enterprise/using/create-sdl-packages.html).

### Deploy packages

After you've created your package, deploy it to your client machines using one of these methods:

- Go to the client machine and double-click the package file (Windows or macOS).
- Use the Windows command prompt or macOS terminal.
- Use third-party tools:
  - [Microsoft Intune](https://helpx.adobe.com/enterprise/kb/deploy-packages-using-ms-intune.html)
  - [Microsoft System Center Configuration Manager (SCCM)](https://helpx.adobe.com/enterprise/kb/deploy-packages-using-sccm.html)
  - [Apple Remote Desktop (ARD)](https://helpx.adobe.com/enterprise/kb/deploy-packages-using-ard.html)
  - [JAMF Pro](https://helpx.adobe.com/enterprise/kb/deploy-packages-using-jamf-pro.html)
  - [Munki](https://helpx.adobe.com/enterprise/kb/deploy-packages-using-munki.html)

## Related reading

- [Manage users | Individually](https://helpx.adobe.com/enterprise/using/manage-users-individually.html)
- [Manage users | Bulk CSV upload](https://helpx.adobe.com/enterprise/using/bulk-upload-users.html)
- [Manage Directory users](https://helpx.adobe.com/enterprise/using/manage-directory-users.html)
- [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html)
- [Assign users to product profiles (for enterprises and institutions)](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html#assign-users)
- [Assign licenses to teams users](https://helpx.adobe.com/enterprise/using/assign-licenses-to-teams-users.html)
- [Business Storage model](https://helpx.adobe.com/enterprise/kb/business-storage-model-introduction.html)