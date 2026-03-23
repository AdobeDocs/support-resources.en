---
title: Migrate existing users to the Adobe Admin Console
description: Guidance for organizations that use Adobe subscription licenses and need to migrate existing users in Admin Console to a different buying program or license type.
feature-set: Experience Cloud Services
solution: Admin Console
feature: Admin Console
---
# Migrate existing users to the Adobe Admin Console

Applies to enterprise & teams.

This document is for organizations with existing Creative Cloud, Document Cloud, and Acrobat licenses through an Enterprise Term License Agreement (ETLA) or Value Incentive Plan (VIP) subscription that are migrating to a different buying program or license type.

>[!NOTE]
>
>If you're in North America and need help with your Annual Adobe VIP contract renewal from your Account Manager, email **renewalhelp@adobe.com**, and we'll contact you shortly.

To help avoid a lapse in end-user product access, assign licenses in the Adobe Admin Console before the existing VIP subscription term ends.

* For ETLA customers, allow at least 30 days of product overlap. Complete the migration prior to the anniversary date so users keep access to Adobe apps and services. For ETLA contract expiry details, see [Automated expiration stages for ETLA contracts](https://helpx.adobe.com/enterprise/using/contract-expiry.html).
* For VIP customers, purchase licenses before your anniversary date and assign licenses before the renewal window closes on your current VIP term.
* CLP or TLP customers can migrate from serialized Acrobat or Creative Suite to named-user licenses using the migration instructions in [Licensing](https://helpx.adobe.com/enterprise/using/licensing.html).

>[!NOTE]
>
>If your organization's license type changes, end users must sign out of any Adobe product or service and sign back in with the same credentials.
>
>For desktop products such as Photoshop, Acrobat, and Illustrator, use Sign out and Sign in options in the Help menu. On Adobe.com, use the icon in the upper-right corner to sign out, then sign back in.

## Quick License Assignment (VIP to VIP)

Current VIP members who purchased Creative Cloud for enterprise or Acrobat (for enterprise) through VIP may be able to assign licenses quickly during their renewal window using Quick License Assignment. Eligible customers meet criteria such as the following.

* Products are the same

   1. The renewal window is open (30 days before or after the VIP agreement anniversary date).
   2. The enterprise products on the order are new SKUs equivalent to the team versions in the current term.
   3. The enterprise license order quantity is greater than or equal to the existing team license quantity.

* Products are higher value

   1. The renewal window is open.
   2. The enterprise products on the order are new SKUs that are higher-value products than the team products in the current term.
   3. The enterprise license order quantity is greater than or equal to the existing team license quantity.

* Quick License Assignment is not available when

   * The quantity of enterprise licenses on the order is less than the number of existing team licenses.
   * The order is for higher-value enterprise products but the ordered enterprise license quantity is less than the existing team license quantity.
   * The order mixes team and enterprise products, regardless of quantity.
   * The customer already purchased team and enterprise products before the renewal period.
   * Enterprise renewal SKUs are used for the new enterprise order.
   * The enterprise product order is for a different VIP agreement number.
   * Current team products include items that have no enterprise versions.

After Adobe processes your enterprise purchase order, you receive a confirmation email with instructions, including the day you must transfer users from team licenses to enterprise licenses in the Admin Console before they lose access.

In the Admin Console, you are prompted to assign licenses using Quick License Assignment:

1. Confirm the number of licenses for assignment.

   ![Transfer licenses](assets/migrate-transfer-licenses.png)

2. Confirm that the team product licenses being unassigned match the enterprise licenses being assigned.

3. You receive an email when the process is complete.

   ![License assignment confirmation](assets/migrate-license-assignment.png)

Download the [results report](https://helpx.adobe.com/enterprise/using/users.html#main-pars_header_1346350355) in the Admin Console to confirm all licenses were assigned. If you finish before the date in your confirmation email, end users should not experience a lapse in service.

Schedule a 1:1 onboarding call with an Adobe Onboarding Specialist (if you have not already) to learn more about the Admin Console, including [Administrative roles](https://helpx.adobe.com/enterprise/using/admin-roles.html) and [Identity](https://helpx.adobe.com/enterprise/using/identity.html).

>[!NOTE]
>
>Quick License Assignment does not migrate users with pending invitations in the Team Admin Console.

## Bulk license assignment (VIP to VIP)

Assign licenses with a bulk operation using a CSV template from the [!DNL Admin Console]. Use this approach when:

* You are a VIP customer who does not meet Quick License Assignment requirements, or
* You need to assign licenses outside your renewal window.

1. After you have access to the [Adobe Admin Console](https://adminconsole.adobe.com/enterprise) and your licenses are added, go to **[!UICONTROL Users]** > **[!UICONTROL Users]**.
2. Click ![More options menu](assets/migrate-more-options.png) in the upper-right corner of the **[!UICONTROL Users]** page, then choose **[!UICONTROL Edit User Details by CSV]**.
3. In the **[!UICONTROL Edit Users by CSV]** dialog, click **[!UICONTROL Download CSV template]** and choose **[!UICONTROL Current user list]**.

   ![Edit Users by CSV](assets/migrate-edit-users-by-csv.png)

   For field descriptions in the downloaded file, see [CSV file format](https://helpx.adobe.com/enterprise/using/users.html#main-pars_header).
4. Add license assignments to the CSV, then drag the updated file into the **[!UICONTROL Edit Users by CSV]** dialog and click **[!UICONTROL Upload]**. You receive an email when the operation completes.

   ![User edit complete](assets/migrate-user-edit-complete.png)

Download the [results report](https://helpx.adobe.com/enterprise/using/users.html#main-pars_header_1346350355) to validate assignments. Then schedule onboarding with an Adobe Onboarding Specialist to learn about [administrative roles](https://helpx.adobe.com/enterprise/using/admin-roles.html) and [identity](https://helpx.adobe.com/enterprise/using/identity.html).

## Bulk license assignment (VIP to ETLA)

If you have a VIP subscription and are moving users to ETLA, use this bulk flow:

1. Sign in to the [Adobe Admin Console](https://adminconsole.adobe.com/enterprise) and open the organization that contains your VIP users.
2. Go to **[!UICONTROL Users]** > **[!UICONTROL Users]**.
3. Click ![More options menu](assets/migrate-more-options.png) in the upper-right corner, then choose **[!UICONTROL Export users list to CSV]**.
4. Open the ETLA organization where you want those users.
5. Go to **[!UICONTROL Users]** > **[!UICONTROL Users]**.
6. Click **[!UICONTROL Add Users by CSV]**.
7. Click **[!UICONTROL Download CSV template]**, then add the VIP users from the CSV you exported in step 3.
8. Upload the updated CSV.

You receive an email when users are added to the ETLA organization.

![Users added after VIP to ETLA migration](assets/migrate-users-added-vip-etla.png)

Download the [results report](https://helpx.adobe.com/enterprise/using/users.html#main-pars_header_1346350355) to validate assignments. Schedule onboarding with an Adobe Onboarding Specialist for [administrative roles](https://helpx.adobe.com/enterprise/using/admin-roles.html) and [identity](https://helpx.adobe.com/enterprise/using/identity.html).

For bulk upload issues, see [Troubleshoot bulk user upload](https://helpx.adobe.com/enterprise/kb/troubleshoot-bulk-user-csv-upload.html).

## Bulk license assignment (ETLA to VIP)

If you have an ETLA subscription and are moving users to VIP:

1. Sign in to the [Adobe Admin Console](https://adminconsole.adobe.com/enterprise) and open the organization that contains your ETLA users.
2. Go to **[!UICONTROL Users]** > **[!UICONTROL Users]**.
3. Click ![More options menu](assets/migrate-more-options.png) in the upper-right corner, then choose **[!UICONTROL Export users list to CSV]**.

   ![Export user list menu](assets/migrate-export-user-list.png)

4. Open the VIP organization where you want those users.
5. Go to **[!UICONTROL Users]** > **[!UICONTROL Users]**.
6. Click **[!UICONTROL Add Users by CSV]**.
7. Click **[!UICONTROL Download CSV template]**, then add the ETLA users from the CSV you exported in step 3.
8. Upload the updated CSV.

You receive an email when users are added to the VIP organization.

![Users added after ETLA to VIP migration](assets/migrate-users-added-etla-vip.png)

Download the [results report](https://helpx.adobe.com/enterprise/using/users.html#main-pars_header_1346350355) to validate assignments. Schedule onboarding with an Adobe Onboarding Specialist for [administrative roles](https://helpx.adobe.com/enterprise/using/admin-roles.html) and [identity](https://helpx.adobe.com/enterprise/using/identity.html).

For bulk upload issues, see [Troubleshoot bulk user upload](https://helpx.adobe.com/enterprise/kb/troubleshoot-bulk-user-csv-upload.html).


