---
layout: Conceptual
title: Data access governance reports - get site permission report for given users - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/data-access-governance-site-permissions-users-report
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-07-01T00:00:00.0000000Z
ms.reviewer: pullabhk
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
customer-intent: As a SharePoint administrator, I want to determine which sites are accessible by the given user and determine the extent of their access so that I can take necessary actions to modify permissions for sensitive content.
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
description: In this article, you learn how to get a snapshot report to view the list of sites accessible by a given user.
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
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: b9b98e36-5d05-86f6-9d2e-e54d1d327042
---

# Data access governance reports - get site permission report for given users - SharePoint in Microsoft 365 | Microsoft Learn

The **Site permissions for users** report is one of the [Data access governance snapshot reports](/en-us/sharepoint/data-access-governance-reports#what-are-snapshot-reports) available with [SharePoint Advanced Management](advanced-management). This report lists all sites a user can access and helps admins determine whether they can access the entire site or specific sections, granted directly to the user or indirectly through groups. This approach helps you quickly assess your overall security posture and identify sites that need immediate attention.

## What does the site permissions for users report show me?

The site permissions for users report captures the permission state of given users at a specific point in time. It gives you a complete overview of sites accessible to these users along with the extent of access. You can determine whether the entire site is shared with the user or only a few files or items are shared. For the complete list of metrics captured in the report, see the Download the site permissions for users section.

## When should I use the site permissions for users report?

Use the report when you want to review permissions for users before assigning them a Copilot license. Use it if you want to clean up permissions when the user is about to leave the organization or changed departments.

## Run the site permissions for users report

Important

Review these important details before creating your first report:

- Make sure that the site permissions for your organization report is generated at least once.
- Reports capture data from up to 48 hours before generation.
- You can have up to five reports.
- You can run reports again every 30 days.

Here's how to run the site permissions for users report:

1. From the Data access governance landing page, select **View reports** under **Site permissions for users**.
2. Select **Create report** to generate your report.
3. Select **Add users to report** to select the users for whom you want to generate the report. Select **Save** to save the selections. You can also edit the selection and remove users or add new users, if required.
4. Specify the **Scope** - either SharePoint or OneDrive.
5. Provide the **Report name** - a unique name to identify this report.
6. Select **Create and run** to trigger the creation of report.
7. Check the **Status** column to see if a report is ready or when it was last updated.

### How do I view the site permissions for users report?

1. From the Data access governance landing page, select **View reports** under **Site permissions for users**.
2. Review all the available reports and their corresponding status, the list of users for whom the report is generated, how many sites are present in the report, and a button to download the entire report.
3. Select the relevant **Report name**.
4. You see all the users as a list to the left. The right side shows the list of sites accessible to the selected user. The right side also displays whether the user can access the entire site or has access to specific items directly or indirectly.

![Report to list all sites accessible to the selected user](sharepointonline/media/data-access-governance/user-permission-report.png)

## Download the site permissions for users report

You can download the report for a specific user or for all users by using one of the following options:

1. Select **Download report for** the selected user option to download the report as a CSV file. The file has a limit of 1 million sites.
2. Select **Download detailed report** to get CSV files for all the users given as input, as a ZIP file.
3. On the previous page where all the reports are listed, select **Download report** to get CSV files for all the users given as input, as a ZIP file.

The downloaded report contains the following information:

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
| Is site shared | Specifies if the user is part of one or more SharePoint groups with site-level access. Yes or No. |
| Items with direct access count | Number of files or folders shared directly with the user |
| Items with indirect access count | Number of files or folders the user can access by being part of a group. |
| Microsoft Entra object ID | GUID identifying the user in Microsoft Entra |
| User principle name | Unique name identifying the user in Microsoft Entra |
| Display name | Name as displayed in people selection/search related experiences |
| Report Date | Time of generation of report. It might take up to 48 hours to reflect any changes in the report |