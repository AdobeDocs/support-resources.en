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

## Upgrade to latest version of Adobe Commerce {#upgrade-to-latest-version-of-adobe-commerce}

Ensure your site is not on an unsupported version of Adobe Commerce, which may affect your site's performance and increase vulnerability to security issues. Upgrade to the latest version of Adobe Commerce to be secure and ready for the holiday season.

The [latest release](https://experienceleague.adobe.com/en/docs/commerce-operations/release/notes/overview) of Adobe Commerce includes many [critical security fixes](https://experienceleague.adobe.com/en/docs/commerce-operations/release/notes/security-patches/overview), including enhancements and mitigated issues, that will benefit your project when upgrading from a prior version.

For more information on unsupported versions of Adobe Commerce, review the [Adobe Commerce Life Cycle Policy](https://experienceleague.adobe.com/en/docs/commerce-operations/release/planning/lifecycle-policy).

## Install latest ECE-Tools and Quality Patch Tool (QPT) {#install-latest-ece-tools-and-quality-patch-tool-qpt}

Ensure that the latest `ece-tools` module and its dependent modules are installed, using the `--with-dependencies` switch, so that all required cloud patches are properly installed for your Adobe Commerce version. For steps, see [Update the ECE-Tools package](https://experienceleague.adobe.com/en/docs/commerce-on-cloud/user-guide/dev-tools/ece-tools/update-package).

Review the patch list available in the Quality Patches Tool and ensure the performance patches compatible with your Adobe Commerce version have been applied. See [Quality Patches Tool: Search for patches](https://experienceleague.adobe.com/en/docs/commerce-operations/tools/quality-patches-tool/patches-available-in-qpt/patches-available-in-qpt-tool-overview).

>[!NOTE]
>
>QPT is available for both Adobe Commerce on cloud infrastructure and on-premises installations. Installation and usage commands differ between the two—for Cloud, QPT is included with the ECE-Tools package.

## Review and clean log files {#review-and-clean-log-files}

Review the log files in the cloud environment (for example, application log files under `~/var/log`) and identify any frequently logged records being written to the default or custom log files. For details, see [View and manage logs](https://experienceleague.adobe.com/en/docs/commerce-on-cloud/user-guide/develop/test/log-locations).

* Review the following default log files and fix recurring errors: `~/var/log`, `~/var/log/exception.log`, `~/var/log/support_report.log`, `~/var/log/system.log`, `~/var/report`.
* Remove debug logs that were previously added for troubleshooting past issues.

These logs are also available in [!DNL New Relic], see [New Relic log management](https://experienceleague.adobe.com/en/docs/commerce-on-cloud/user-guide/monitor/new-relic/log-management).

## Monitor disk size growth {#monitor-disk-size-growth}

Your Adobe Commerce on cloud infrastructure has two main disk volumes. Monitor these volumes to ensure they have sufficient free space when there is heavy traffic. Adobe Commerce provides a warning when either volume reaches above 70% usage.

* `/mnt/shared` (shared files, including logs and media files)
* `/data/mysql` (database volume)

For details, see [Manage disk space](https://experienceleague.adobe.com/en/docs/commerce-on-cloud/user-guide/develop/storage/manage-disk-space).

## Review slowest database requests {#review-slowest-database-requests}

It is important to regularly monitor and review the most time-consuming database transactions in [!DNL New Relic]. Investigate significantly slow queries and components.

* **Check the most time-consuming transactions:** Go to **[!UICONTROL New Relic]** > **[!UICONTROL APM & Services]** > select environment > **[!UICONTROL Databases]**, then sort by Most time consuming transactions.

* **Check the MySQL slow query log:** Review `mysql-slow.log` for slow queries recorded by the system. These logs are also available in [!DNL New Relic]: go to **[!UICONTROL New Relic]** > **[!UICONTROL Logs]**, and filter by `filePath:"/var/log/mysql/mysql-slow.log"`.

Review the [!DNL MySQL] slow query logs regularly to confirm slow queries aren't running frequently. For steps to resolve queries you identify as problematic, see [Resolve database performance issues](https://experienceleague.adobe.com/en/docs/commerce-operations/implementation-playbook/best-practices/maintenance/resolve-database-performance-issues).

## Configure cron jobs {#configure-cron-jobs}

All asynchronous operations in Commerce are performed using the Linux cron command.

Commerce depends on proper cron job configuration for important system functions, including indexing and queue consumer operations. Failure to set it up properly means Commerce will not function as expected.

It is critical that Commerce cron is set up and configured correctly, using the appropriate Unix user in the Unix crontab file. Each Unix user has its own crontab file, which is the configuration used to run cron jobs for that user. For steps, see [Configure and run cron jobs](https://experienceleague.adobe.com/en/docs/commerce-operations/configuration-guide/cli/configure-cron-jobs).

The script `dev/tools/cron.sh` can no longer be executed, because it has been removed.

## Optimize client-side settings {#optimize-client-side-settings}

To improve the storefront responsiveness of your Commerce instance, configure the following settings under **[!UICONTROL Stores]** > **[!UICONTROL Configuration]** > **[!UICONTROL Advanced]** > **[!UICONTROL Developer]**, which is available only in Developer mode:

* **[!UICONTROL Grid Settings]** > **[!UICONTROL Asynchronous indexing]**: *Enable*
* **[!UICONTROL CSS Settings]** — **[!UICONTROL Minify CSS Files]**: *Yes*
* **[!UICONTROL JavaScript Settings]** — **[!UICONTROL Minify JavaScript Files]**: *Yes*
* **[!UICONTROL JavaScript Settings]** — **[!UICONTROL Enable JavaScript Bundling]**: *Yes* (not enabled by default)
* **[!UICONTROL Template Settings]** — **[!UICONTROL Minify HTML]**: *Yes*

Since Adobe Commerce on Cloud always runs in Production mode, set each option from the command line instead—for example, `bin/magento config:set --lock-config dev/css/minify_files 1`—then commit the resulting `app/etc/config.php` change and redeploy. For the full list of CLI paths, see [Optimize resource files](https://experienceleague.adobe.com/en/docs/commerce-operations/implementation-playbook/best-practices/development/optimize-css-js-files).
