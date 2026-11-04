---
layout: Conceptual
title: Set up a new group for term sets - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/set-up-new-group-for-term-sets
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2018-07-11T00:00:00.0000000Z
ms.reviewer: shrganguly
ms.author: ruihu
author: maggierui
manager: jtremper
audience: End User
f1.keywords: NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.collection: M365-collaboration
ms.custom: admindeeplinkSPO
ms.localizationpriority: medium
search.appverid:
- SPO160
- OSU150
- MET150
ms.assetid: 2b6d2e1b-6b1f-43db-80dc-51ca777b3d17
description: Learn how easy it is to create a group for a collection of terms in a term set. When you make groups for term sets, you can specify a hierarchy of terms.
locale: en-us
document_id: 7d4695d9-ddaa-ddbc-3e35-5b0fdfcb63e8
document_version_independent_id: fdb51136-30b0-9225-fbba-f747a5e2d1f8
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/set-up-new-group-for-term-sets.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: set-up-new-group-for-term-sets
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/set-up-new-group-for-term-sets.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 4a6b2f51-3c47-e93f-9b2f-5987f3adff9c
---

# Set up a new group for term sets - SharePoint in Microsoft 365 | Microsoft Learn

A term group is a set of term sets that all share common security requirements. Only users who are designated as contributors to a specific group can manage term sets that belong to the group or create new term sets within it. Organizations should create unique groups for term sets that will have unique access or security needs. For information about how to create a term set, see [Set up a new term set](set-up-new-term-set).

Important

To create a new term set group, you must be a term store admin.

To set up a new group for term sets, follow these steps.

1. In the SharePoint admin center, under **Content services**, select [**Term store**](https://go.microsoft.com/fwlink/?linkid=2185073).
2. In the right pane, click **Add term group**.

    ![Screenshot of navigation pane in Term Store Management Tool, showing the New Group menu item](sharepointonline/media/add-term-group.png)
3. Enter a name for your new group, and then press ENTER.
4. To edit the Term group **name** and **description**, select **Edit** next to the group name. The **Edit name and description** panel appears. Enter a description to help users understand the purpose of this term group. Select **Save**.
5. To edit the group managers or contributors, select **Edit** next to **Group managers**. The **Edit admins** panel appears. Enter the names or email addresses of the people you want to add, assign them to a role, and then click **Save**.
6. To copy the unique identifier for this term group, select **Copy**.