---
title: How to apply a Isolated patch provided by Adobe
description: This article instructs how to apply a Isolated patch for Adobe Commerce on-premises, Adobe Commerce on Cloud infrastructure, and Magento Open Source.
feature: Best Practices, Compliance, Console
solution: Commerce
feature-set: Commerce
autotag-review: '2026-08-19T13:22:21.768Z'
TQID: 'https://experienceleague.adobe.com/tmaNqB6uOX2ukmfxQvcqFvYwm2UyO6USzb7t8hFQM1A'
product_v2:
  - id: eadea719-cf89-469b-a6fd-a236a7138047
    internal-label: Commerce
  - id: eadea719-cf89-469b-a6fd-a236a7138047
    internal-label: Commerce
feature_v2:
  - id: b5f00040-57a0-4a6d-a39e-383b1936c2c9
    internal-label: Compliance
---
# How to apply a Isolated patch provided by Adobe

This article instructs how to apply a Isolated patch for Adobe Commerce on-premises, Adobe Commerce on Cloud infrastructure, and Magento Open Source.

>[!WARNING]
>
>We strongly recommend applying and testing the patch on the Staging/Integration environment before applying it to Production. We also recommend you have a recent backup before any manipulations.

## How to apply a Isolated patch for Adobe Commerce on Cloud infrastructure {#cloud}

1. If you don't have a directory named `m2-hotfixes` in the project root, please create one.
1. Copy the `%patch_name%.patch` file(s) to the `m2-hotfixes` directory.
1. Add, commit, and push your code changes:

    ```git
    git add -A
    ```

    ```git
    git commit -m "Apply %patch_name%.patch patch"
    ```

    ```git
    git push origin
    ```

For additional information about applying patches to Cloud projects, see [Apply patches](https://experienceleague.adobe.com/en/docs/commerce-on-cloud/user-guide/develop/upgrade/apply-patches).

## How to apply a Isolated patch for Adobe Commerce on-premises and Magento Open Source {#commerce}

1. Upload the patch to your Adobe Commerce on-premises or Magento Open Source root directory.
1. Run the following SSH command:

    ```bash
    patch -p1 < %patch_name%.patch
    ```

   (If the above command doesn't work, try using `-p2` instead of `-p1`)

1. For the changes to be reflected, refresh the cache in the [!UICONTROL Admin] under **[!UICONTROL System]** > **[!UICONTROL Cache Management]**.
