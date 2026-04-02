---
title: Download audit logs and export reports
description: Learn how global administrators view, filter, and export audit logs and reports in the Global Admin Console.
feature-set: Experience Cloud Services
solution: Admin Console
feature: Admin Console
exl-id: 4b562a4d-14e5-4687-a1ae-6a435f087627
---
# Download audit logs and export reports

Applies to enterprise.

Learn how global administrators view, filter, and export audit logs and reports using the Global Admin Console.

To get started, sign in to the [Global Admin Console](https://global-admin-console.adobe.com/). Then go to the **[!UICONTROL Insights]** tab and select **[!UICONTROL Audit Logs]** to track all changes made across organizations.

## View and download audit logs

As a global administrator, you have full visibility into changes made in the Global Admin Console. You can search audit logs across all organizations for actions taken in the last 90 days, including when they occurred and who performed them.
- Audit logs help ensure continued compliance by safeguarding against inappropriate system access and by auditing suspicious behavior within your organization.
- The logs available in the Global Admin Console include only events that a global administrator can access. They do not include user assignments or user events. [Learn more](https://experienceleague.adobe.com/en/docs/support-resources/adobe-support-tools-guide/adobe-admin-console/admin-console-overview) about the different capabilities each console offers.
- The logs cover events for all organizations in the hierarchy, allowing you to search audit logs across all organizations at once.

>[!NOTE]
>
> As a system administrator in an [Adobe Admin Console](https://adminconsole.adobe.com) organization, you can use the [Audit Log](https://helpx.adobe.com/enterprise/using/audit-logs.html) to review user assignments and user events. Actions performed by system administrators in child organizations of the selected organization are also included in the audit logs. Learn more about how system administrators can [track changes](https://helpx.adobe.com/enterprise/using/audit-logs.html) made in the Admin Console.

To view or download audit logs for your organization:

1. As a global administrator, sign in to the [Global Admin Console](https://global-admin-console.adobe.com/insights).
1. Select **[!UICONTROL Insights]** > **[!UICONTROL Audit Logs]**. 

The audit logs display the following information for filtered events:

   | Field | Description |
   |------ |-------------|
   | Date | Date and time of the event, shown in the local time zone. |
   | Event Name | Description of the action performed. |
   | Event Detail | Additional event details, if available. |
   | Object Name | Name of the product, product profile, or user group involved in the event, as applicable. |
   | Affected User | Email address of the affected user, if applicable. |
   | Admin | Email address of the admin who performed the action. *System* is displayed if the action was performed by an Adobe backend system. |
   | IP Address | IP address of the machine where the action was taken. This usually reflects the physical location but can be a proxy server or VPN address. |
   | Organization | Name of the organization affected by the event. |

1. You can filter audit logs using the following options:

   - Search by affected user or admin.
   - Select one or more organizations.
   - Define a date range.
   - Filter by event name.
   - Combine filters to narrow results, such as viewing events from the last seven days for a specific organization.

   ![audit-logs](assets/audit-logs.png)

   *Filter the audit logs based on the event name, affected organization, or date range.*

   ![select-organization](assets/select-organizations.png)

   *Select organizations to filter the audit logs.*

1. To export audit logs, select **[!UICONTROL Export CSV]** to export filtered results. The results are downloaded in CSV format.

For details about the fields included in the export, see [Log Schema](#log-schema).

>[!NOTE]
>
>Exported audit log reports are retained for 90 days after they are generated.


## Understand your audit log report {#log-schema}

The exported audit log report includes the following fields for each organization:

| Field | Description |
|------|------------|
| id | Event ID |
| eventTime | Date and time of the event (local time zone) |
| eventType | Name of the event |
| eventSubType | Additional event details, if available |
| actorEmail | Email address of the admin who performed the event. *System* is displayed if the event was performed by an Adobe back-end system. |
| targetUserEmail | Email of the affected user, if applicable |
| targetGroupName | Affected user group, if applicable |
| targetProductName | Affected product, if applicable |
| targetProfileName | Affected product profile, if applicable |
| ipAddress | IP address of the machine where the action was taken. Usually reflects the physical location, but could be a proxy server or VPN address. |
| organizationName | Name of the affected organization |

## Download export reports

When any global administrator exports organization data from the [Global Admin Console](https://global-admin-console.adobe.com/insights), the report is processed and made available under the **[!UICONTROL Insights]** tab in **[!UICONTROL Export Reports]**.

All reports generated by any global admin are available in one place. The export reports capability is helpful in the following scenarios:

- If you have a large hierarchy with many organizations, you no longer have to wait for the export file to be processed. You can use the reports generated by your fellow admins.
- You no longer need to keep or save these reports to compare later. The reports are retained for 90 days, and you can download them at any time to compare reports.


To download an export report:

1. Sign in to the [Global Admin Console](https://global-admin-console.adobe.com/insights) and navigate to **[!UICONTROL Insights]** > **[!UICONTROL Export Reports]**.

   Reports generated within the last 90 days are displayed. After 90 days, you can generate the report again. Learn how you can generate reports for [Organization structure](https://experienceleague.adobe.com/en/docs/support-resources/adobe-support-tools-guide/adobe-admin-console/export-or-import-organization-structure-and-product-allocations#export-the-organization-structure).


   | Field | Description |
   |------|------------|
   | Report | Date and time the report was generated (local time zone) |
   | Format | File format (CSV, JSON, XLSX) |
   | Size | File size |
   | Created By | Email address of the admin who generated the report |
   | Action | Link to download the report |

1. To download a report, select **[!UICONTROL Download]**.

   If the report you just generated isn't appearing on the list, select **[!UICONTROL Refresh]**.

   ![export-reports](assets/export-reports.png)

*Download any report generated in the last 90 days.*
