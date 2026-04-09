---
title: Identity overview
description: Understand and choose identity types (Federated ID, Enterprise ID, Adobe ID, and Personal Adobe ID) for your organization and manage user access in the Admin Console.
Feature-set: Experience Cloud Services
Solution: Admin Console
Feature: Admin Console
exl-id: e53ded7c-1ba3-4d98-bc20-792a252618ac
---
# Identity overview

Applies to enterprise & teams.

Adobe's identity management system helps admins create and manage user's access to applications and services. Adobe offers these identity types or accounts to authenticate and authorize users.

## Identity types on Adobe Admin Console

Identity types allow the organization different levels of control over the users' accounts and data. Your choice of identity model has a considerable impact on how your organization stores and shares assets. While Federated ID and Enterprise ID models are created and managed by the organization, Adobe IDs are created and managed by the individual.

The following table guides you in choosing which identity model best suits your organization.

>[!NOTE]
>If your organization hasn't been updated to Adobe's enterprise storage model, and you're still using Adobe IDs for individuals, see the description in the [identity types table](https://helpx.adobe.com/enterprise/using/identity.html#using-personal-adobe-id) below.

<table>
<thead>
<tr>
<th scope="col">Identity types</th>

<th scope="col" style="text-align: center;">
  <img src="./assets/federated-id.png" alt="Federated ID icon"><br>
  Federated ID
</th>
<th scope="col" style="text-align: center;">
  <img src="./assets/enterprise-id.png" alt="Enterprise ID"><br>
  Enterprise ID
</th>
<th scope="col" style="text-align: center;">
  <img src="./assets/adobe-id.png" alt="Adobe ID"><br>
  Adobe ID
</th>
</tr>
</thead>
<tbody>
<tr>
<th scope="row"><strong>Key offerings</strong></th>
<td>Created, owned, and managed by the organization. The organization manages user-credentials and uses Single Sign-On (SSO) via a SAML2 identity provider (IdP).</td>
<td>Created, owned, and managed by the organization. The organization retains exclusive rights to create user accounts on verified domains.</td>
<td>Created, owned, and managed by the end user. Adobe performs the authentication, and the end user manages the identity. Depending upon the <a href="https://helpx.adobe.com/enterprise/using/storage-for-business.html">storage model</a>, users or businesses retain control over files and data. Adobe ID accounts are created on unverified, public, or trusted domains. Refer to the point 2 of the note section below.</td>
</tr>
<tr>
<th scope="row"><strong>Account &amp; data ownership</strong></th>
<td colspan="2">Organization-owned and controlled</td>
<td>Organization-owned for Enterprise storage and user-owned for User storage</td>
</tr>
<tr>
<th scope="row"><strong>Security &amp; monitoring</strong></th>
<td colspan="2">
  <ul>
    <li>Audit logs</li>
    <li>Content logs</li>
    <li>Sharing restrictions</li>
    <li>Organization's authentication settings</li>
  </ul>
</td>

<td>
  <ul>
    <li>Content logs</li>
    <li>Sharing restrictions</li>
    <li>Password policy</li>
  </ul>
</td>

</tr>
<tr>
<th scope="row"><strong>Reset password</strong></th>
<td colspan="2">Not supported</td>
<td><a href="https://helpx.adobe.com/manage-account/using/change-or-reset-password.html">Reset your account password</a></td>
</tr>
<tr>
<th scope="row"><strong>Creative Cloud for enterprise &amp; Document Cloud for enterprise</strong></th>
<td colspan="3">Supported</td>
</tr>
<tr>
<th scope="row"><strong>Creative Cloud for teams &amp; Document Cloud for teams</strong></th>
<td colspan="2">Not supported</td>
<td>Supported</td>
</tr>
<tr>
<th scope="row"><strong>Experience Cloud</strong></th>
<td colspan="3">Supported</td>
</tr>
<tr>
<th scope="row"><strong>Recommended for</strong></th>
<td>
  <ul>
    <li>Organizations already using SSO or SAML</li>
    <li>Existing directory services (e.g. Google and Azure AD)</li>
    <li>Require easy integration with non-Adobe services</li>
    <li>Can demonstrate ownership of domain</li>
  </ul>
</td>
<td>
  <ul>
    <li>Can demonstrate ownership of domain</li>
    <li>Don't require SSO</li>
  </ul>
</td>
<td>
  <ul>
    <li>Creative Cloud for teams</li>
    <li>Organization prefers to use domains they don't own</li>
    <li>Public domains (e.g. Hotmail, Gmail)</li>
    <li>Access apps like Adobe Experience Manager Mobile</li>
  </ul>
</td>
</tr>
<tr>
<th scope="row"><strong>Get started</strong></th>
<td><a href="https://helpx.adobe.com/enterprise/using/set-up-identity.html">Set up identity</a></td>
<td><a href="https://helpx.adobe.com/enterprise/using/add-domains-directories.html#claim-domains">Claim domains</a></td>
<td><a href="https://helpx.adobe.com/enterprise/using/users.html#add-users">Add User</a></td>
</tr>
</tbody>
</table>

>[!NOTE]  
>
>1. Password policy for Creative Cloud for teams is the same as that for Creative Cloud for individuals.
>1. Adobe ID users authenticate with their Adobe ID credentials or by their owning organization's authentication model (SSO, 2FA, etc.). In such scenarios, users are redirected to the owning organization's SSO page. After authentication, users may need to [choose a business profile](https://helpx.adobe.com/enterprise/kb/enterprise-id-faq.html#choose-profile).

## Using Personal Adobe IDs

Adobe is updating all teams and enterprise customers to use Adobe's Enterprise storage model. See the following table if your organization has users who are using personal Adobe IDs to access their company or school Adobe apps and services.

### Personal Adobe ID

<table>
<thead>
<tr>
<th scope="col">Identity type</th>
</th>
<th scope="col" style="text-align: center;">
  <img src="./assets/personal-adobe-id.png" alt="Adobe ID"><br>
  Personal Adobe ID
</th>
</tr>
</thead>
<tbody>
<tr>
<th scope="row"><strong>Key offerings</strong></th>
<td>Created, owned, and managed by the end user. Adobe performs the authentication, and the end user manages the identity.</td>
</tr>
<tr>
<th scope="row"><strong>Account &amp; data ownership</strong></th>
<td>User-controlled</td>
</tr>
<tr>
<th scope="row"><strong>Security &amp; monitoring</strong></th>
<td>Password policy. Refer to the point 1 in the note section below.</td>
</tr>
<tr>
<th scope="row"><strong>Reset password</strong></th>
<td><a href="https://helpx.adobe.com/manage-account/using/change-or-reset-password.html">Reset your account password.</a>  Refer to the point 2 in the note section below.</td>
</tr>
<tr>
<th scope="row"><strong>Creative Cloud for enterprise &amp; Document Cloud for enterprise</strong></th>
<td>Supported</td>
</tr>
<tr>
<th scope="row"><strong>Experience Cloud</strong></th>
<td>Supported</td>
</tr>
<tr>
<th scope="row"><strong>Only available to / Recommended for</strong></th>
<td>
  <ul>
    <li>Enterprise and teams customers onboarded before migration</li>
    <li>Creative Cloud for teams</li>
    <li>Want control in user's hand</li>
    <li>Access apps like Digital Publishing Suite</li>
    <li>Users own assets after separation from organization</li>
  </ul>
</td>
</tr>
<tr>
<th scope="row"><strong>Get started</strong></th>
<td><a href="https://helpx.adobe.com/enterprise/using/users.html#add-users">Add User</a></td>
</tr>
</tbody>
</table>

>[!NOTE]
>
>1. Password policy for Creative Cloud for teams is the same as that for Creative Cloud for individuals.
>1. For Creative Cloud for enterprise customers using [enterprise storage](https://helpx.adobe.com/enterprise/using/manage-adobe-storage.html), admins can add Adobe ID users to the Admin Console but can't add them to product profiles. Admins must migrate Adobe ID users to another identity type.
>1. There are some products and services, such as **Adobe Licensing Website, that only supports** Adobe ID.

## More like this

- [Set up identity](https://helpx.adobe.com/enterprise/using/set-up-identity.html)
- [Switch user identity](https://helpx.adobe.com/enterprise/using/switch-user-identity.html)
- [Admin Console overview](https://helpx.adobe.com/enterprise/using/admin-console-overview.html)
- [Education FAQ](https://helpx.adobe.com/enterprise/using/education-faq.html)
- [Add and manage users](https://helpx.adobe.com/enterprise/using/users.html)
