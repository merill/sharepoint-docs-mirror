---
layout: Conceptual
title: Change the external sharing setting for a user's OneDrive - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/user-external-sharing-settings
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
- OneDrive sharing
- external sharing
- user settings
ms.topic: how-to
ms.service: onedrive
ms.localizationpriority: medium
ms.collection:
- Strat_OD_admin
- M365-collaboration
ms.custom: onedrive-toc
search.appverid:
- ODB160
- MET150
ms.assetid: 64aa1f56-d7f6-4500-a408-1fde8fe6db36
description: Learn how to change the OneDrive external sharing setting for a user in the Microsoft 365 admin center.
customer-intent: As a SharePoint Administrator, I want to change the external sharing settings for a specific user's OneDrive so that I can control who they can share content with.
locale: en-us
document_id: 9ec52357-8785-615f-e52f-cc9e38c8989f
document_version_independent_id: 405f0ace-09c2-0f33-5078-dc657c9dec24
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/user-external-sharing-settings.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: user-external-sharing-settings
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/user-external-sharing-settings.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: a2417330-30a8-10d7-479a-8fb26d65ece2
---

# Change the external sharing setting for a user's OneDrive - SharePoint in Microsoft 365 | Microsoft Learn

After you set the organization-wide sharing settings for Microsoft SharePoint and Microsoft OneDrive, you can further restrict the external sharing for a specific OneDrive user.

Tip

Instead of changing the external sharing setting for an individual user's OneDrive, consider blocking external sharing of sensitive information by using [Microsoft Purview data loss prevention](/en-us/purview/dlp-learn-about-dlp).

## How do I change the external sharing setting?

1. Sign in to https://admin.microsoft.com.
2. In the left pane, select **Users** &gt; **Active users**.
3. Select the user.
4. Select the **OneDrive** tab. Under **Sharing**, select **Manage external sharing**.
5. Select a new external sharing level, and then select **Save**.

## How do I change the external sharing setting by using PowerShell?

You can also change the external sharing setting for a specific OneDrive user by using PowerShell. Use the [Set-SPOSite](/en-us/powershell/module/sharepoint-online/set-sposite) cmdlet with the `-SharingCapability` parameter.