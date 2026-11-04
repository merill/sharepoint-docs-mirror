---
layout: Conceptual
title: Review your recent changes to SharePoint site properties - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/recent-actions-panel
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-05-14T00:00:00.0000000Z
ms.reviewer: daminasy
manager: dansimp
ms.author: deniseb
author: denisebmsft
audience: admin
customer-intent: As a SharePoint administrator, I want to review my recent changes to site properties to ensure compliance and governance.
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- ContentEnagagementFY24
- M365-collaboration
- M365-sam
- Highpri
- Tier2
- trust-pod
description: Learn how to review your recent changes to SharePoint site properties.
locale: en-us
document_id: 9ef1b620-0a97-5677-fe80-3129f2103024
document_version_independent_id: 4f253654-152f-c5bd-056d-8fc188de7850
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/recent-actions-panel.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: recent-actions-panel
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/recent-actions-panel.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 55f620b0-d2dd-4186-a177-4072ac7a2c57
---

# Review your recent changes to SharePoint site properties - SharePoint in Microsoft 365 | Microsoft Learn

The recent actions panel lets you review and monitor the last 30 changes you've made to a SharePoint site's properties (such as renaming a site, deleting a site, changing storage quota) within the last 30 days in the [SharePoint admin center](/en-us/sharepoint/get-started-new-admin-center). This feature only shows changes made by you and not other administrators. Also, changes made to site properties at the organization-level don't show in the panel.

[![Screenshot of restricted access control for SharePoint sites.](sharepointonline/media/sam-overview/5-recent-admin-actions-panel.png)](sharepointonline/media/sam-overview/5-recent-admin-actions-panel.png#lightbox)

Note

Recent actions panel isn't available for global readers. [GDAP administrators](/en-us/partner-center/gdap-introduction) can't see the previous and current values of the administrator actions.

## Prerequisites to review your recent changes to SharePoint site properties

See [Prerequisites for SharePoint Advanced Management](sharepoint-advanced-management-prerequisites).

Important

Without Microsoft SharePoint Advanced Management, you can only view actions made in the current session. Once you close the browser or sign out, the recent actions panel clears the history.

## View recent actions of a site

1. In the SharePoint admin center, expand **Sites** and select **Active sites**.
2. Select **Your recent actions**. The recent actions panel appears and lists your most recent 30 actions made within the last 30 days.
3. Select **Export** to download the list as a CSV file.
4. Select **View site details** to open the site info panel. From here, you can make changes to site properties like site name, site address, hub association, and aliases.

![Screenshot of .csv file of recent admin actions](sharepointonline/media/exported_csv.png)

Note

If you close the browser while actions are in-progress, they aren't recorded in the panel or the CSV file. Failed actions are recorded in the panel, but are removed once you exit the current session. The exported CSV file doesn't contain failed actions.

## Bulk site edits

Here's an example of how bulk edits are grouped as one action in the recent actions panel:

Suppose that you deleted four SharePoint sites on May 21 at 12:10 AM. The bulk edit shows as one item named **Deleted 4 sites** on the recent actions panel. Select that action and the list of deleted SharePoint sites appears.

![screenshot of recent actions panel with successful and failed actions](sharepointonline/media/rac_panel_bulk_edit_successful_and_failed_actions.png)

![screenshot of recent actions panel with bulk edit action expanded to show sites affected](sharepointonline/media/rac_panel_bulk_edit_delete_sites_selected_4_sites_expanded.png)