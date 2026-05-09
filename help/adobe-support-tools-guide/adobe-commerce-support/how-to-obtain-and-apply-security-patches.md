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

If you are on an older version of Adobe Commerce (2.4.4), you will have automatically received Extended Support. Your version must be one of the following unsupported versions to be able to apply the latest available Security Patches:

2.4.4 - 2.4.4-p11

Unsupported versions (2.3.x, 2.4.0 - 2.4.3) are ineligible for support and you must first upgrade to a supported version to take advantage of the latest security fixes.

If you don't have Extended Support, you may request Support to share the patches with you, but they won't be able to resolve any issues/errors you may encounter when applying them.

### Case II:

Isolated patches are only provided in exceptional cases, and it isn't the preferred form of implementing security fixes.

If an isolated patch file/hotfix is not mentioned in the Release Notes:

* **Cloud:**

1. Some [!UICONTROL security patches] might be included/released in the latest version of Cloud Tools Suite (ECE Tools) under Cloud Patches for Commerce - check the [Release Notes](https://experienceleague.adobe.com/en/docs/commerce-cloud-service/user-guide/release-notes/cloud-tools-suite), and if a security fix is mentioned in the release, upgrade the package to that version.
1. If the Release Notes do not mention a security fix, continue reading.

* **Cloud infrastructure or On-Premise:**

* If an isolated patch file/hotfix is not available, [upgrade the Adobe Commerce version on cloud infrastructure](https://experienceleague.adobe.com/en/docs/commerce-cloud-service/user-guide/develop/upgrade/commerce-version) 2.4.X to the latest patch version 2.4.X-pY. 
* If an isolated patch file/hotfix is not available, [upgrade the Adobe Commerce version On-Premise](https://experienceleague.adobe.com/en/docs/commerce-operations/upgrade-guide/implementation/perform-upgrade) 2.4.X to the latest patch version 2.4.X-pY.

## Related reading

* See [Release notes for Commerce Cloud Tools Suite](https://experienceleague.adobe.com/en/docs/commerce-cloud-service/user-guide/release-notes/cloud-tools-suite) in the *Adobe Commerce on Cloud Infrastructure Guide*.
* See [Upgrade the Adobe Commerce version](https://experienceleague.adobe.com/en/docs/commerce-cloud-service/user-guide/develop/upgrade/commerce-version) in the *Adobe Commerce on Cloud Infrastructure Guide*.
