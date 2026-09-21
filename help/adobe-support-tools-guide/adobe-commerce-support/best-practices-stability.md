---
title: Best practices and stability
description: Best practices and stability recommendations to help Adobe Commerce merchants prepare their environments for high-traffic events such as the holiday season.
feature-set: Commerce
feature: Support
solution: Commerce
role: Developer, Admin, Leader
TQID: 'https://experienceleague.adobe.com/iA6ioGYYgQSotPrPqujDBdRcjBLUQXMGXfwlcSMGjkM'
product_v2:
  - id: eadea719-cf89-469b-a6fd-a236a7138047
    internal-label: Commerce
feature_v2:
  - id: cdfd3bc1-dc23-5cf0-b965-d3c0c55cde67
    internal-label: Best Practices
  - id: 5a951749-fac9-5bc7-9a98-ebe4ff066437
    internal-label: Cloud
  - id: dac87252-6066-4d6e-a9d2-f6d84c323de7
    internal-label: Configuration
subfeature_v2:
  - id: 3c398179-d35a-51ba-b317-6c5b95feef5e
    internal-label: Logs
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
---

# Best practices and stability

This section provides technical recommendations for preparing Adobe Commerce environments—both Commerce on cloud infrastructure and on-premises—for high-traffic events such as the holiday season.

>[!NOTE]
>
>Steps marked **(Cloud only)** apply to Commerce on cloud infrastructure. Most other recommendations also apply to on-premises deployments.

## Upgrade to the latest Adobe Commerce version {#upgrade-to-latest-adobe-commerce-version}

Ensure your site is not on an unsupported version, which can impact performance and increase vulnerability to security issues. The latest release includes critical security fixes and performance enhancements that benefit any project upgrading from a prior version. See [Adobe Commerce lifecycle policy](https://experienceleague.adobe.com/en/docs/commerce-operations/release/planning/lifecycle-policy) for details on unsupported versions.

## Install the latest ECE-Tools and Quality Patches Tool (QPT) {#install-latest-ece-tools-and-quality-patch-tool-qpt}

Keep tools and patches updated to apply Adobe-provided performance enhancements. See [Update the ECE-Tools package](https://experienceleague.adobe.com/en/docs/commerce-on-cloud/user-guide/dev-tools/ece-tools/update-package).

* **(Cloud only)** Ensure the latest `ece-tools` module and its dependent modules are installed (use the `--with-dependencies` switch) so required cloud patches are properly applied for your [!DNL Adobe Commerce] version.
* Review the patch list in the Quality Patches Tool (QPT) and confirm that applicable performance patches compatible with your version have been applied. QPT is available for both Commerce on cloud infrastructure and on-premises; for on cloud infrastructure it's included in ECE-Tools. For details, refer to [QPT installation and usage](https://experienceleague.adobe.com/en/docs/commerce-operations/tools/quality-patches-tool/usage)

## Review and clean log files {#review-and-clean-log-files}

Remove debug logs and monitor recurring errors to prevent disk overuse and improve log visibility. See [Log locations](https://experienceleague.adobe.com/en/docs/commerce-on-cloud/user-guide/develop/test/log-locations).

* Review default log files (`~/var/log`, `~/var/log/exception.log`, `~/var/log/support_report.log`, `~/var/log/system.log`, `~/var/report`) and fix recurring errors.
* Remove debug logs left over from past troubleshooting.
* These logs are also available in the [!DNL New Relic] Logs section.

## Monitor disk size growth {#monitor-disk-size-growth}

Keep disk usage under 70% to avoid outages. See [Manage disk space](https://experienceleague.adobe.com/en/docs/commerce-on-cloud/user-guide/develop/storage/manage-disk-space).

* On Commerce on cloud infrastructure, track the `/mnt/shared` (shared files, logs, media) and `/data/mysql` (database) volumes. Adobe Commerce provides a warning when either volume exceeds 70% usage.
* On-premises, monitor the equivalent application and database storage volumes for your hosting environment.

## Review slow database queries {#review-slow-database-queries}

Identify and optimize costly queries using an APM tool and `mysql-slow.log`. See [Resolve database performance issues](https://experienceleague.adobe.com/en/docs/commerce-operations/implementation-playbook/best-practices/maintenance/resolve-database-performance-issues). Commerce on cloud infrastructure includes a bundled [!DNL New Relic] subscription for this; on-premises environments need their own APM tooling.

1. Navigate to **[!UICONTROL [!DNL New Relic]]** > **[!UICONTROL APM & Services]** > **[!UICONTROL Environment]** > **[!UICONTROL Databases]** and sort by most time-consuming transactions.
1. Navigate to **[!UICONTROL [!DNL New Relic]]** > **[!UICONTROL Logs]** and filter by `filePath:"/var/log/mysql/mysql-slow.log"`.
1. Confirm slow queries are not being executed frequently.

## Configure cron jobs correctly {#configure-cron-jobs-correctly}

Verify cron jobs run every minute and under the proper to support queue and indexer processes. See [Configure cron jobs](https://experienceleague.adobe.com/en/docs/commerce-operations/configuration-guide/cli/configure-cron-jobs).

All asynchronous operations in Adobe Commerce depend on correctly configured Linux cron jobs, set up under the appropriate Unix user's crontab—failure to configure cron properly means Commerce will not function as expected.

>[!NOTE]
>
>The legacy `dev/tools/cron.sh` script has been removed and can no longer be used.

## Optimize client-side settings {#optimize-client-side-settings}

Enable JavaScript, CSS, and HTML minification and bundling for improved storefront load times. Configure at **[!UICONTROL Stores]** > **[!UICONTROL Settings]** > **[!UICONTROL Configuration]** > **[!UICONTROL Advanced]** > **[!UICONTROL Developer]**:

* [!UICONTROL Grid Settings] — **[!UICONTROL Asynchronous indexing]**: *Enable*
* CSS Settings — **[!UICONTROL Minify CSS Files]**: *Yes*
* JavaScript Settings — **[!UICONTROL Minify JavaScript Files]**: *Yes*
* JavaScript Settings — **[!UICONTROL Enable JavaScript Bundling]**: *Yes* (not on by default)
* Template Settings — **[!UICONTROL Minify HTML]**: *Yes*

Refer to [Optimize CSS/JS files](https://experienceleague.adobe.com/en/docs/commerce-operations/implementation-playbook/best-practices/development/optimize-css-js-files) for more details.
