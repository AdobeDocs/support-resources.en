---
title: Limit product access by IP addresses
description: Use IP-based access to control user access to Adobe products and restrict use to approved public IP ranges.
feature-set: Experience Cloud Services
solution: Admin Console
feature: Admin Console
---

# Limit product access by IP addresses

Applies to enterprise.

Use IP-based access to control your users' access to Adobe products and prevent unauthorized use from unlisted public IP addresses.

Go to [Admin Console](https://adminconsole.adobe.com/settings/identity) to add trusted public IP addresses to the **IP-based access** allowlist for secured use of Adobe apps and services.

## Benefits of IP-based access

IP-based access control uses an IP address allowlist to limit the use of Adobe products from random public IP addresses. IP-based access applies to all directories and the associated products in your Adobe Admin Console.

You can add trusted public IPs to the **Allowed IP addresses** list to stop users from:

- Accessing products from public IPs that are outside the allowed IP ranges
- Signing in to Adobe [user profiles](https://helpx.adobe.com/enterprise/using/manage-adobe-profiles.html) from public IPs outside the allowed IP ranges
- Switching user profiles on web apps outside the allowed IP ranges

    ![Export organization structure](./assets/ip-based-access.avif)

## Enable IP-based access

### Important considerations

>[!Important considerations]
>
>- Admins must start by adding their own public IP address and only then add other IP ranges. You might face an error otherwise.
>- IP-based access doesn't apply to private IP addresses.

You can add up to 150 different public IP ranges in CIDR format only.

Follow these steps to enable IP-based access in your Adobe Admin Console:

1. Go to the **[!UICONTROL Adobe Admin Console Settings](https://adminconsole.adobe.com/settings/identity)** section.
2. Select and expand **[!UICONTROL Privacy and security]** in the selection menu, then select **[!UICONTROL Authentication settings]**.
3. In the **[!UICONTROL IP-based access]** section, select the **[!UICONTROL Add IP address]** button.
4. In the **[!UICONTROL Add IP address]** window:
   - Enter the public IP addresses or CIDR block to add to your allowlist.
   - Use a comma to separate multiple IP addresses.
   - Select **[!UICONTROL Save]**.

    We only support the IPv4 format currently. Here are a few examples:
    - IP v4 address: 1.3.4.6
    - IP v4 subnet address: 1.2.0.0/24

Your IP addresses are added within a few minutes. Associated users will see the restriction the next time they try to sign in or switch profiles outside the allowed public IP addresses. We recommend that you inform your users in advance of this change.

You can edit or remove any listed IP address by selecting the edit or delete options next to each entry.

>[!NOTE]
>
>- When IP-based access is enabled, **no forced logout occurs**. Users are only impacted when they try to select the restricted profile when signing in or switching profile on web.
>- If you're using a secured web gateway, ensure all traffic is routed through it. View the [list of domains to be allowed](https://helpx.adobe.com/enterprise/kb/network-endpoints.html) for Adobe apps and services to function correctly.
>- If you're locked out of the Admin Console because you entered an invalid IP address, contact [Adobe Customer Care](https://helpx.adobe.com/enterprise/using/support-for-enterprise.html).

## Join the conversation

To collaborate, ask questions, and chat with other administrators, visit our [Enterprise and Teams Community](https://www.adobe.com/go/entcom).
