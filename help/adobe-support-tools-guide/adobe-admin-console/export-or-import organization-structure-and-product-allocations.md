---
title: Export or import organization structure and product allocations
description: Learn how global administrators export and import organization hierarchy and product allocation data in the Global Admin Console using JSON, CSV, or XLSX. Applies to Enterprise.
---

# Export or import organization structure and product allocations

**Applies to:** Enterprise

Learn how global administrators can streamline organization and product management with export and import features in the Global Admin Console.

>[!NOTE]
>

> Access the **[!UICONTROL Organizations]** tab in the [Global Admin Console](https://helpx.adobe.com/enterprise/global-admin-console/adopt-global-administration.html) to export or import the organization structure, and go to the **[!UICONTROL Product Allocation]** tab for allocation data. Use the **[!UICONTROL More Options]** ⋯ icon to select export or import.
> [Sign in to the Global Admin Console](https://helpx.adobe.com/enterprise/global-admin-console/export-and-import-data.html).

## Export the organization structure

As a [global administrator](https://helpx.adobe.com/enterprise/global-admin-console/manage-administrators.html), you can export the organization hierarchy. You can download a JSON, CSV, or XLSX representation of the entire organization hierarchy, or a subset of it. You can then use this data to analyze or make modifications.

The export format chosen impacts the structure of the exported data:

- CSV format — Allows exporting only one kind of data at a time. When exporting product profiles in CSV format, the profiles and resources are combined into one table. There are multiple entries for the product profile, one for each resource.
- XLSX format — Results in each organization detail displaying in a separate sheet. Records are connected between the different object types by a reference id. In some cases, there may be multiple rows for a particular object (e.g., Resource objects when there are a set of values associated with a given resource).
- JSON format — The most flexible. It can take advantage of structural relationships between exported objects (e.g., products in an organization appear directly in the organization element). The same fields are exported in all three formats but some values are redundant in the JSON format.

### Steps to export

1. Sign in to the [Global Admin Console](https://global-admin-console.adobe.com/). In the **[!UICONTROL Organizations]** tab, use the organization picker to select the organization hierarchy where you want to perform the export. Data for all organizations in the hierarchy is exported.
1. Select the **[!UICONTROL More Options]** icon and choose **[!UICONTROL Export]**.

![Export organization structure](../assets/export-org-structure.png)

1. In the **[!UICONTROL Export]** dialog box, select what to export and a format to export the data in.

![Admin Console export dialog box](../assets/admin-console-export-dialog-box.png)

1. Select **[!UICONTROL Export]**. The export file can take several minutes to generate. Once complete, to download the report, navigate to **[!UICONTROL Global Admin Console]** > **[!UICONTROL Insights]** > **[!UICONTROL Export Reports]**. Learn more about the [Export Reports feature](https://helpx.adobe.com/enterprise/global-admin-console/export-and-import-data.html).

>[!NOTE]
>
>JSON files are exported in a zip format. You can open them using a zip utility or the operating system's zip features.

After downloading the file, you can manipulate the data and then import it back. The updates imported appear in the Global Admin Console as though you have manually edited the data.

## Import the organization structure

As a [global administrator](https://helpx.adobe.com/enterprise/global-admin-console/manage-administrators.html), you can import potentially modified data. When uploaded, the new data is compared with current data and any changes are applied to the organization hierarchy. All import operations are performed on the updated copy of the organization hierarchy. If you have any pending changes, the import changes will be added on top of the pending changes in the hierarchy.

### Steps to import

1. Sign in to the [Global Admin Console](https://global-admin-console.adobe.com). In the **[!UICONTROL Organizations]** tab, use the organization picker to select the organization hierarchy where you want to perform the import.
1. Select the **[!UICONTROL More Options]** icon and select **[!UICONTROL Import]**. Depending on the size and complexity of the import file, processing can take from a few seconds to several minutes.
1. Select **[!UICONTROL Select a file]**, and choose a JSON, CSV, or XLSX file to be uploaded. For CSV, only one organization detail can be imported at a time and it does not support importing Products. The imported changes appear as though you have manually edited the data.
1. Select **[!UICONTROL Close]**.
1. Select **[!UICONTROL Review Pending Changes]**. Then, select **[!UICONTROL Submit Changes]** to [execute](https://helpx.adobe.com/enterprise/global-admin-console/execute-jobs.html) them. Before executing the changes, the pending actions are displayed in the same manner as when edits are made manually in the Global Admin Console.
