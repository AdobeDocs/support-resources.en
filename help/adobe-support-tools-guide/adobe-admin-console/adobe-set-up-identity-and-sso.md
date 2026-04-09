---
title: Set up identity and Single Sign-On
description: Learn how organization system admins can set up user identity and Single Sign-On (SSO) in the Adobe Admin Console using Adobe ID, Enterprise ID, or Federated ID.
feature-set: Experience Cloud Services
solution: Admin Console
feature: Admin Console
---
# Set up identity and Single Sign-On

**Applies to:** Enterprise

Learn how to set up identity in the Adobe Admin Console. Compare Adobe ID, Enterprise ID, and Federated ID, and configure Single Sign-On (SSO) for secure access to Adobe apps.

Configure identity and set up Single Sign-On (SSO) so employees can [log in](https://adminconsole.adobe.com/settings/) with existing organizational credentials.

Here is the video tutorial of how to [Set up identity and SSO (YouTube)](https://youtu.be/V57lU4zaSBs).

## Key terms and concepts

### Directory

A directory in the Admin Console is an entity that holds resources such as users and policies like authentication. These directories are similar to LDAP or Active Directories.

### Identity provider (IdP)

An identity provider (IdP) is your organization’s identity provider, such as:

- Active Directory  
- Microsoft Azure  
- Ping  
- Okta  
- InCommon  
- Shibboleth  

### Personas involved

| Role | Responsibility |
|------|----------------|
| System admin | Works with IdP directory managers and DNS managers to set up identity in the Admin Console. |
| DNS Manager | Updates DNS tokens to validate domain ownership. |
| Identity Provider (IdP) directory manager | Handles the IdP portal and associated connectors. |

### Adobe ID

Created, owned, and managed by the end user. Adobe performs the authentication, and the end user manages the identity. Depending upon the [storage model](https://helpx.adobe.com/enterprise/using/storage-for-business.html), users or businesses retain control over files and data.

For organizations that have been updated to the Enterprise storage model, assets and data is controlled by the organization. For organizations that have not been updated, the individual owns and controls Adobe ID assets.  

### Enterprise ID

Created, owned, and managed by an organization. Adobe hosts the Enterprise ID and performs authentication, but the organization maintains the Enterprise ID. Admins create an Enterprise ID and issue it to a user. Admins can revoke access to products and services by taking over the account or deleting the Enterprise ID to permanently block access to associated data. To learn more, click [here](https://helpx.adobe.com/enterprise/using/setup-enterprise-id.html).

### Federated ID

Created and owned by an organization, and linked to the enterprise directory via federation. The organization manages credentials and processes Single Sign-On via a SAML2 Identity Provider (IdP).

The following are a few requirements and scenarios where Federated IDs are recommended:

- If you want to provision users based on your organization's enterprise directory.
- If you want to manage the authentication of users.
- If you need to maintain strict control over apps and services available to a user.  

## Set up identity without Single Sign-On

You may use Adobe ID or Enterprise ID if your organization is not currently using SSO on other applications.

## Using Adobe ID

Adobe is updating all organizations to the [Enterprise storage model](https://helpx.adobe.com/enterprise/using/storage-for-business.html). This gives your organization greater control over your users’ assets and data.

Get started with [adding users](https://helpx.adobe.com/enterprise/using/users.html) to the Admin Console.

## Set up identity with Enterprise ID

You can set up an Enterprise ID directory if you want more control over your users’ data without using SSO. Only admins create an Enterprise ID and issue it to a user.

See [Set up organization with Enterprise ID](https://helpx.adobe.com/enterprise/using/setup-enterprise-id.html) for requirements and steps to create Enterprise ID directories.

## Set up identity with Single Sign-On

You must set up user identity with Federated ID accounts to use SSO.

Federated IDs are recommended when:

- You need to maintain strict control over apps and services available to a user.  
- You want to manage the authentication of users.  
- You want to provision users based on your organization’s enterprise directory.  

## Set up a new SSO integration

You can use popular identity providers such as Microsoft Azure AD, Google, or use other SAML-based IdP to set up SSO between your organization and Adobe products.

**Azure AD** (Recommended) - [Set up SSO and user-sync with Azure AD Connector](https://helpx.adobe.com/enterprise/using/sso-setup-azure.html)

**Other SAML IdP** - [Set up SSO with other SAML-providers](https://helpx.adobe.com/enterprise/using/create-directory.html)

**Google** (Recommended) - [Set up SSO and user-sync using Google Connector](https://helpx.adobe.com/enterprise/using/setup-sso-google.html)

## Manage existing SSO setup

After SSO is set up between your organization and Adobe, use the following to manage and change your setup.

Learn how to manage your domains and directories:

- [Manage users](https://helpx.adobe.com/enterprise/using/users.html) and [groups](https://helpx.adobe.com/enterprise/using/user-groups..html)  
- [Link domains to directories](https://helpx.adobe.com/enterprise/using/add-domains-directories.html#link-domains-to-directoies) to control users’ access to apps, services, and settings  
- [Manage directory trust](https://helpx.adobe.com/enterprise/using/directory-trust.html) to use domains claimed by another organization  

Learn how to change your identity provider:

- [Change your IdP](https://helpx.adobe.com/enterprise/using/migrate-authentication-provider.html) without disrupting your users’ work  
- [Move domains across directories](https://helpx.adobe.com/enterprise/using/manage-domains-directories.html#move-domains-across-directories)  
- [Remove legacy directory users](https://helpx.adobe.com/enterprise/using/manage-directory-users.html)  
- [Delete old/unclaimed domains and empty directories](https://helpx.adobe.com/enterprise/using/manage-domains-directories.html#delete)  

## Errors and common questions

Solutions for common questions and errors when setting up and managing SSO:

### Azure AD - FAQs & Troubleshooting

#### FAQs

- [Azure AD connector FAQs](https://helpx.adobe.com/enterprise/using/azure-ad-connector-faq.html)  
- [How to delete directories and domains](https://helpx.adobe.com/enterprise/using/sso-setup-azure.html#Deletedirectoriesandremovedomains)  

#### Troubleshooting

- [Users denied access](https://helpx.adobe.com/enterprise/using/sso-setup-azure.html#sync-issues)  
- [Sync issues](https://helpx.adobe.com/enterprise/using/sso-setup-azure.html#sync-issues)  

### Other SAML IdP - FAQs & Troubleshooting

#### FAQs

[SAML integration FAQs](https://helpx.adobe.com/enterprise/using/sso-faq.html)  

#### Troubleshooting

- [General SSO troubleshooting](https://helpx.adobe.com/enterprise/kb/tshoot-fed-id.html)  
- [“Access denied” error](https://helpx.adobe.com/enterprise/kb/tshoot-fed-id.html#Error_Access_Denied_logging_in)  
- [“Another user is currently logged in” error](https://helpx.adobe.com/enterprise/kb/tshoot-fed-id.html#ErrorAnotheruseriscurrentlyloggedin)  
- [Perform a SAML trace](https://helpx.adobe.com/enterprise/kb/perform-a-saml-trace.html)  

### Google - FAQs

- [Google connector FAQs](https://helpx.adobe.com/enterprise/using/google-federation-faq.html)  
- [How to delete directories and domains](https://helpx.adobe.com/enterprise/using/setup-sso-google.html#Deletedirectoriesandremovedomains)  

## Join the conversation

To collaborate, ask questions, and chat with other administrators, use the [Enterprise and Teams Community](https://www.adobe.com/go/entcom).

## Legal and privacy

- [Legal Notices](https://helpx.adobe.com/legal/legal-notices.html)  
- [Online Privacy Policy](https://www.adobe.com/privacy.html)  
