---
layout: Conceptual
title: Data access governance reports - get site permissions for users or groups - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/data-access-governance-site-permissions-users-report
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-11-03T00:00:00.0000000Z
ms.reviewer: pullabhk
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
customer-intent: As a SharePoint administrator, I want to determine which sites are accessible by a given user or group and the extent of their access so that I can modify permissions for sensitive content.
f1.keywords: NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Strat_SP_admin
- Highpri
- Tier2
- M365-sam
- M365-collaboration
- trust-pod
ms.custom:
- admindeeplinkSPO
search.appverid: 
description: Learn how to get a snapshot report of sites accessible by a given user, Microsoft 365 group, or Microsoft Entra security group.
ai-usage: ai-assisted
locale: en-us
document_id: ead40917-f425-c932-5618-92141bdd6a34
document_version_independent_id: 4be03822-1f99-244e-e91f-b52b35d4741b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/data-access-governance-site-permissions-users-report.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: data-access-governance-site-permissions-users-report
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/data-access-governance-site-permissions-users-report.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: b9b98e36-5d05-86f6-9d2e-e54d1d327042
---

# Data access governance reports - get site permissions for users or groups - SharePoint in Microsoft 365 | Microsoft Learn

The **Site permissions for users or groups** report is one of the [Data access governance snapshot reports](data-access-governance-reports#what-are-snapshot-reports) available with [SharePoint Advanced Management](advanced-management). This report lists all sites a specified user or group can access and helps you determine the extent of that access. Use it to assess your security posture and identify sites that need attention.

You can select users, Microsoft 365 groups, or Microsoft Entra security groups. Groups must be identifiable in Microsoft Entra ID. SharePoint groups and distribution lists aren't supported as report inputs. Each report contains either users or groups, not both.

## What does the site permissions for users or groups report show me?

The report captures the permission state of the selected users or groups at a specific point in time. For each user or group, it lists all accessible sites and shows whether the entire site is shared or access is limited to specific files or folders.

- For users, the report includes counts of items shared directly with the user and items accessible indirectly through group membership.
- For groups, the report shows whether the entire site is shared with the group and the count of items shared directly with the group. It doesn't include a count of items with indirect permissions.

Note

Group reports don't expand nested-group permissions. If a security group is a member of another group, access granted to the parent group isn't included in the nested group's report.

For the complete list of metrics, see Download the site permissions for users or groups report.

## When should I use the site permissions for users or groups report?

Use the report when you want to review permissions for users before assigning them a Copilot license. Use it if you want to clean up permissions when the user is about to leave the organization or changed departments.

Select groups when you want to review which sites and items are accessible to a Microsoft 365 group or Microsoft Entra security group. Use the results to identify access that needs review.

## Run the site permissions for users or groups report

Important

Review these important details before creating your first report:

- Make sure that the site permissions for your organization report is generated at least once.
- Reports capture data from up to 48 hours before generation.
- You can have up to five reports.
- You can run reports again every 30 days.
- You can include up to 100 groups in a group report.

Here's how to run the site permissions for users or groups report:

1. From the Data access governance landing page, select **View reports** under **Site permissions for users or groups**.
2. Select **Create report** to generate your report.
3. Under **Create report for**, select **Users** or **Groups**, then select **Next**. A single report can't include both recipient types.

    [![Screenshot of the Create a report pane with Users and Groups options under Create report for.](sharepointonline/media/data-access-governance/users-groups-report-recipient-selection.png)](sharepointonline/media/data-access-governance/users-groups-report-recipient-selection.png#lightbox)
4. Add the users or groups for whom you want to generate the report, then select **Save**. For groups, select Microsoft 365 groups or Microsoft Entra security groups. You can edit the selection to add or remove users or groups of the selected recipient type.
5. Specify the **Scope** - either SharePoint or OneDrive.
6. Provide the **Report name** - a unique name to identify this report.
7. Select **Create and run** to trigger the creation of report.
8. Check the **Status** column to see if a report is ready or when it was last updated.

### How do I view the site permissions for users or groups report?

1. From the Data access governance landing page, select **View reports** under **Site permissions for users or groups**.
2. Review the available reports, their status, the users or groups included in each report, and the number of sites. You can also download the entire report.
3. Select the relevant **Report name**.
4. Select a user or group from the list on the left. The right side shows the sites accessible to that user or group and whether the entire site is shared. For users, it also shows counts of items with direct and indirect access. For groups, it shows only the count of items with direct access.

The following example shows a user report:

![Screenshot of a user report listing sites accessible to the selected user.](sharepointonline/media/data-access-governance/user-permission-report.png)

The following example shows a group report. **Site shared** indicates whether the entire site is shared with the selected group, and **Direct access items** shows the count of items shared directly with it. There's no indirect-access count.

[![Screenshot of a group report listing sites accessible to the selected group, with Site shared and Direct access items columns.](sharepointonline/media/data-access-governance/group-permission-report.png)](sharepointonline/media/data-access-governance/group-permission-report.png#lightbox)

## Download the site permissions for users or groups report

You can download the report for a specific user or group, or for all users or groups included in the report, by using one of the following options:

1. To download a CSV file for a specific user or group, select that recipient and use the download link above the site list. For example, a SharePoint group report shows **Download SharePoint report for** followed by the selected group's name. Each CSV file has a limit of 1 million sites.
2. Select **Download report for all groups** in a group report, or **Download detailed report** in a user report, to get a ZIP file containing CSV files for all recipients included in the report.
3. On the previous page where all reports are listed, select **Download report** to get a ZIP file containing CSV files for all users or groups included in the report.

The downloaded report contains the following information. The **Items with indirect access count** column is included only in user reports.

| Column | Description |
| --- | --- |
| TenantID | GUID identifying the organization |
| Site ID | GUID identifying the organization |
| Site Name | Name of the site |
| Site URL | URL of the site |
| Site Template | Specifies the type of site. Has values such as Communication site, Team site, Team site (no Microsoft 365 Groups), Other sites |
| Primary admin | Site administrator marked as Primary in Active sites page |
| Primary admin email | Email of primary site administrator |
| ExternalSharing | Specifies whether content can be shared with external guests. Yes or No. |
| Site Privacy | Applicable in Microsoft 365 connected team sites. Specifies the privacy setting of the group. Has values Public or Private |
| Site Sensitivity | Specifies the sensitivity label applied to the site |
| Files | Approximate number of all files in the site |
| Is site shared | Specifies whether the entire site is shared with the user or group. Yes or No. This indicates membership in one or more SharePoint groups with site-level access. |
| Items with direct access count | Number of files or folders shared directly with the user or group. |
| Items with indirect access count | User reports only. Number of files or folders the user can access through group membership. This column isn't included in group reports. |
| Microsoft Entra object ID | GUID identifying the user or group in Microsoft Entra ID. |
| User principle name | Unique name identifying the user in Microsoft Entra |
| Display name | Name as displayed in people selection/search related experiences |
| Report Date | Time of generation of report. It might take up to 48 hours to reflect any changes in the report |