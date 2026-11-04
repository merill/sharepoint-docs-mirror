---
layout: Conceptual
title: Report on file and folder sharing in a SharePoint site - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/sharing-reports
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-05-07T00:00:00.0000000Z
ms.reviewer: srice
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Strat_OD_share
- M365-collaboration
- Tier2
search.appverid:
- SPO160
- MET150
ms.custom:
- seo-marvel-apr2020
description: Learn how to create a report on file and folder sharing on a SharePoint site.
locale: en-us
document_id: d6b3a83b-6891-2c36-671b-e3d634aa051c
document_version_independent_id: 705c5543-5e3c-d16d-8014-63739c88483b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/sharing-reports.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: sharing-reports
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/sharing-reports.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
platformId: f0306940-168a-da4b-6f5c-cf660da923b5
---

# Report on file and folder sharing in a SharePoint site - SharePoint in Microsoft 365 | Microsoft Learn

You can create a CSV file of every unique file, user, permission, and link on a given SharePoint site or OneDrive. This report helps you understand how sharing is used and if any files or folders are shared with guests. You must be a site admin to run the report. For more reporting options, see [Microsoft Graph Data Connect](/en-us/graph/data-connect-datasets#onedrive-and-sharepoint-online).

When you run the report, you save the CSV file to a location you choose on the site. If you don't want site members to see the report, consider creating a folder with different permissions where only site owners can access the report.

The report might take some time to run depending on the size of the site. When the report finishes running, you receive an email with a link to the report.

## Run the report for a SharePoint site

1. Open the site where you want to run the report.
2. On the **Settings** menu, select **Site usage**.
3. In the **Shared with external users** section, select **Run report**.
4. Choose a location to save the report, and then select **Save**.

## Run the report for OneDrive

1. From the Microsoft 365 app launcher, select the OneDrive tile.
2. On the **Settings** menu, select **OneDrive settings**.
3. Select **More settings**, and then select **Run sharing report**.
4. Choose a location to save the report, and then select **Save**.

## CSV format

For items shared with direct access, the report contains one row for each user and item combination. The report shows SharePoint groups, but not individual users inside them.

For items shared with a link, the report contains a row for each signed-in user who uses the link or receives the link through the sharing dialog. The report doesn't include links that are emailed directly but aren't clicked, or *Anyone* links.

The report contains the following columns:

| Column | Description |
| --- | --- |
| Resource Path | The relative URL of the item |
| Item Type | The type of item (web, folder, file, and so on) |
| Permission | The permission level the user has on this item |
| User Name | Friendly name of the user or group that has access to this item. If this is a sharing link, the user name is *SharingLink* |
| User E-mail | The email address of the user who has access to this item. This is blank for SharePoint groups. |
| User or Group Type | The type of user or group: Member (internal), Guest (external), SharePoint group, Security group, or Microsoft 365 group. (*Member* refers to a member in the directory, not a member of the site.) |
| Link ID | The GUID of the sharing link if user name is *Sharing Link* |
| Link Type | The type of link (Anonymous, Organization, Specific People) if user name is *Sharing Link* |
| AccessViaLinkID | The **Link ID** used to access the item if a user's permission to an item is via a link. |