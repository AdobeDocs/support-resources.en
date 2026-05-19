---
title: How to obtain and apply [!UICONTROL security patch]
description: This article provides instructions on how to obtain and apply a [!UICONTROL security patch] that has been released, but instructions are unavailable.
exl-id: 6764d60e-5088-4a85-90fa-4372570b065b
---
# How to obtain and apply a [!UICONTROL security patch]

>[!NOTE]
>If you have an On-Premise installation and aren't using version control systems like [!DNL CVS] or GitHub to manage your code, your web host might be able to assist with applying the patch. Feel free to reach out to them for support.

This article provides instructions on how to obtain and apply a [!UICONTROL security patch] that has been released, but instructions are unavailable.

## Affected products and versions 

Adobe Commerce on-premise and cloud infrastructure - all supported versions


## Cause

For Adobe Commerce security bulletins, Adobe only provides a separate isolated patch file or hotfix when that artifact is explicitly released as part of the bulletin. If no isolated patch or hotfix is published or referenced in the bulletin materials, Adobe does not create a separate standalone patch afterward.

This is because the security fixes are engineered, validated, and released together as part of the supported security release for the applicable version line. 

Accordingly, the supported remediation path is to apply the official security update for the affected version line, or upgrade to a version that already contains the fix.

## Solution


### Case I:

* If an isolated patch file/hotfix is mentioned in the [Release Notes](https://experienceleague.adobe.com/en/docs/commerce-on-cloud/user-guide/release-notes/cloud-tools-suite), download the file from the download section of [https://account.magento.com](https://account.magento.com/downloads/view/). Shared access users must first be given download privileges by the account owner/license holder.

**Caveats:**

* Adobe Commerce 2.4.6 remains supported under Extended Support through August 30, 2027.

* Adobe Commerce 2.4.5 remains under Extended Support through August 11, 2026. After this date, Adobe provides security fixes only through May 31, 2027.

* Adobe Commerce 2.4.4 is no longer under Extended Support. Adobe provides security fixes only through May 31, 2027.

* For Adobe Commerce 2.4.4 and 2.4.5, Adobe provides security patch files only. These updates do not include:

    * Adobe Commerce Support or engineering assistance
    * Quality patches
    * Platform or operating system dependency updates

Unsupported versions (2.3.x and 2.4.0–2.4.3) are not eligible for support. You can upgrade to a supported version to receive the latest security fixes.

### Case II:

Isolated patches are provided only in exceptional cases and are not the preferred method for implementing security fixes.

If an isolated patch file or hotfix is not mentioned in the Release Notes, follow these guidelines:

>[!IMPORTANT]
>
>If an isolated patch file or hotfix is not explicitly released for a security issue, upgrade the full Adobe Commerce application to the latest applicable patch version for the affected release line.

**Cloud:**

1. Some [!UICONTROL security patches] might be included/released in the latest version of Cloud Tools Suite (ECE Tools) under Cloud Patches for Commerce - check the [Release Notes](https://experienceleague.adobe.com/en/docs/commerce-cloud-service/user-guide/release-notes/cloud-tools-suite), and if a security fix is mentioned in the release, upgrade the package to that version.
1. If the Release Notes do not mention a security fix, continue reading.

**Cloud infrastructure or On-Premise:**

* If an isolated patch file/hotfix is not available, [upgrade the Adobe Commerce version on cloud infrastructure](https://experienceleague.adobe.com/en/docs/commerce-cloud-service/user-guide/develop/upgrade/commerce-version) 2.4.X to the latest patch version 2.4.X-pY. 
* If an isolated patch file/hotfix is not available, [upgrade the Adobe Commerce version On-Premise](https://experienceleague.adobe.com/en/docs/commerce-operations/upgrade-guide/implementation/perform-upgrade) 2.4.X to the latest patch version 2.4.X-pY.

## Related reading

* See [Release notes for Commerce Cloud Tools Suite](https://experienceleague.adobe.com/en/docs/commerce-cloud-service/user-guide/release-notes/cloud-tools-suite) in the *Adobe Commerce on Cloud Infrastructure Guide*.
* See [Upgrade the Adobe Commerce version](https://experienceleague.adobe.com/en/docs/commerce-cloud-service/user-guide/develop/upgrade/commerce-version) in the *Adobe Commerce on Cloud Infrastructure Guide*.
