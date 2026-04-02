---
title: Update organization policies in the Global Admin Console
description: Learn how a global administrator can set and modify policies for an organization and its children in the Global Admin Console.
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
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Update organization policies in the Global Admin Console

Learn how a global administrator can set and modify policies for an organization and its children in the Global Admin Console.

>[!NOTE]
>
>In the [Global Admin Console](https://helpx.adobe.com/enterprise/global-admin-console/adopt-global-administration.html), select an organization from the hierarchy, and navigate to the **Policies** tab to allow or disallow, or lock the policies.
>
> [Sign in to the Global Admin Console](https://global-admin-console.adobe.com/)

Policies are associated with an organization and restrict operations that can be performed on that organization. When a policy value is set, it restricts or enables actions from that point forward.
For example, if the **Claim Domains** policy is set to *not allowed*, no additional domains can be claimed, but any domains claimed before setting the policy value aren't affected.

## Configure Policies

To modify the policies of an organization, do the following:

1. In the Global Admin Console, [select an organization](https://helpx.adobe.com/enterprise/global-admin-console/overview.html) to edit, then navigate to the **[!UICONTROL Policies]** tab.
1. Select the toggle for the relevant policy to allow or disallow it. You can also lock a policy so no one except a global administrator of the [selected organization](https://helpx.adobe.com/enterprise/global-admin-console/overview.html) or its parent organization can change or unlock it.
1. To lock a policy, select the **[!UICONTROL Lock]** ![Lock](./assets/lock.png) icon. Hovering on the lock displays the name of the selected organization. Learn more about [policy locks](#policy-locks).
1. Select **[!UICONTROL Review Pending Changes]** after you're done editing the organizations. After reviewing, select **[!UICONTROL Submit Changes]** to [execute](https://helpx.adobe.com/enterprise/global-admin-console/execute-jobs.html) them.

## Policy Locks {#policy-locks}

When a policy is locked, its value can't be changed until the policy is unlocked. The Global Admin Console remembers the [selected organization](https://helpx.adobe.com/enterprise/global-admin-console/overview.html) in the organization picker as being the organization from which the policy was locked. Any global administrator of that selected organization or of any organization higher in the tree has the permission to unlock the policy. Global administrators whose scope is lower than that organization don't have the permission to unlock and change policy values.

To create a locked-down environment, set desired policy values on your child organizations and then lock them. Global administrators of those child organizations won't be able to edit the policy values.

### Example: Locked-Down Environment

If Elissa, the global administrator of *Acme Division*, creates child orgs *Marketing* and *Engineering*, then adds Robert as a global admin of *Marketing* and Sarah as global admin of *Engineering*. Next, she sets several policies to *Not Allowed* and *locks* them. Elissa can later unlock and change the policy values when she chooses *Acme Division* as the selected organization, but Robert and Sarah can't unlock the policies on the organizations they're global admins of because the policies are locked by the organization *Acme Division*.

## Policy Details

### Organization Management

| Policy Name | Description |
| --- | --- |
| **Create Child Orgs** | Allows global admin(s) to create child orgs. If *off*, no child orgs can be created. |
| **Rename Org** | If allowed, a global or system admin can rename the org. It also controls changing the country/region of the org. The pathname of an organization can also be changed independently of this policy setting if a parent organization is renamed, or the organization or an ancestor of the organization is reparented. |
| **Delete Orgs** | Allows global admin(s) to delete child organizations. This becomes more important when organizations with Enterprise Storage are enabled due to the risk of deleting user assets. |

### Administrator Management

| Policy Name | Description |
| --- | --- |
| **Add or Delete Admins** | Allows global admin(s) to add new admins to an organization. If *off*, new admins can't be added. |
| **Inherit System Admins from Parent when Child Org is Created** | When global admin(s) create new child organizations, system admins of the parent become system admins of the new organization automatically. This policy is *off* by default. |
| **Manage Admins** | Allows global admin(s) to change or remove/edit admin permissions. |

### User Management

| Policy Name | Description |
| --- | --- |
| **Inherit Users from Directories Managed by the Parent Org** | This policy must be toggled *on* and active prior to creating the new child org. When a child organization is created, users in the parent organization are made available as users in the child org. In other words, this policy automatically sets up a trust relationship between the parent and the child when the new child is created within the GAC. For existing orgs, any trust relationships prior to being added to the GAC will remain once brought into the GAC. If there were no trust relationships in place, the usual trust request process must be followed. For this policy to be successful, the global admin who creates the new organization must also be a system admin of the parent organization with the claimed domain. If not, the domain trust relationship won't be inherited into the newly created org. |
| **Add Adobe ID Users** | If set, the organization can't add Adobe ID type users via the Admin Console, User Management API (UMAPI), nor sync mechanism. |
| **Manage User Groups** | If allowed, Global, System, and user group admins can create, edit, and delete User Groups. |

### Directory and Domain Enforcement

| Policy Name | Description |
| --- | --- |
| **Claim Domains** | If set, system admins can claim domains on the Admin Console. |
| **Change Identity Configuration** | If set, system admins can change the setup of user identity configuration on the Admin Console. |

### Product Allocation

| Policy Name | Description |
| --- | --- |
| **Manage Products** | Allows global admin(s) to add or remove products and change product resource grants. |

### Asset Sharing

| Policy Name | Description |
| --- | --- |
| **System or Storage admin can change asset sharing settings** | If allowed, storage and system admins can change asset sharing settings, including security contacts, password policy, and storage policy. |
| **Inherit sharing policy from a parent when an organization is created** | If allowed, asset sharing settings are inherited from the parent when a child organization is created. Asset sharing settings include security contacts, password policy, and storage policy. This only applies to newly created orgs at the time of creation. It is set on a parent and affects the creation of child orgs under that parent. |
