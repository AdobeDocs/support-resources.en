---
title: How to apply a composer patch provided by Adobe
description: This article instructs how to apply a composer patch for Adobe Commerce on-premises, Adobe Commerce on cloud infrastructure, and Magento Open Source.
feature: Best Practices, Compliance, Console
solution: Commerce
feature-set: Commerce
exl-id: 66d8df60-4c4a-49ef-8107-986e10d6e289
product_v2:
  - id: eadea719-cf89-469b-a6fd-a236a7138047
    internal-label: Commerce
feature_v2:
  - id: cdfd3bc1-dc23-5cf0-b965-d3c0c55cde67
    internal-label: Best Practices
  - id: b5f00040-57a0-4a6d-a39e-383b1936c2c9
    internal-label: Compliance
  - id: 125c1f49-aefd-5f34-a252-288937f95f6b
    internal-label: Marketing Tools
subfeature_v2:
  - id: c4af0798-d497-5e6b-8380-19812c26d00a
    internal-label: Console
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# How to apply a composer patch provided by Adobe

This article instructs how to apply a composer patch for Adobe Commerce on-premises, Adobe Commerce on cloud infrastructure, and Magento Open Source.

>[!WARNING]
>
>We strongly recommend applying and testing the patch on the Staging/Integration environment before applying it to Production. We also recommend you have a recent backup before any manipulations.

## How to apply a composer patch for Adobe Commerce on cloud infrastructure {#cloud}

1. If you do not have a directory named `m2-hotfixes` in the project root, please create one.
1. Copy the `%patch_name%.composer.patch` file(s) to the `m2-hotfixes` directory.
1. Add, commit, and push your code changes:

    ```git
    git add -A
    ```

    ```git
    git commit -m "Apply %patch_name%.composer.patch patch"
    ```

    ```git
    git push origin
    ```

For additional information about applying patches to Cloud projects, see [Apply patches](https://experienceleague.adobe.com/en/docs/commerce-cloud-service/user-guide/develop/upgrade/apply-patches) in our developer documentation.

## How to apply a composer patch for Adobe Commerce on-premises and Magento Open Source {#commerce}

1. Upload the patch to your Adobe Commerce on-premises or Magento Open Source root directory.
1. Run the following SSH command:

    ```bash
    patch -p1 < %patch_name%.composer.patch
    ```

   (If the above command does not work, try using `-p2` instead of `-p1` )

1. For the changes to be reflected, refresh the cache in the Admin under **[!UICONTROL System]** > **[!UICONTROL Cache Management]**.
