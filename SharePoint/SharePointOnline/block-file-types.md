---
layout: Conceptual
title: Block syncing of specific file types - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/block-file-types
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2024-04-09T00:00:00.0000000Z
ms.reviewer: gacarini
ms.author: v-mactran
author: MachelleTranMSFT
manager: jtremper
audience: Admin
f1.keywords:
- CSH
ms.topic: how-to
ms.service: onedrive
ms.localizationpriority: medium
ms.collection:
- Strat_OD_admin
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
- onedrive-toc
search.appverid:
- ODB160
- ODB150
- MET150
ms.assetid: 7d7168dd-9015-4245-a971-61b504f834d6
description: In this article, you learn how to prevent users from uploading specific file types.
locale: en-us
document_id: 31fd97e0-7bfe-0d85-a52c-1ba28f3337c3
document_version_independent_id: 696ee19b-4364-d548-0dcb-afa6a9fff031
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/block-file-types.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: block-file-types
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/block-file-types.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 28c5feb5-ddff-6c86-0970-feba3598078c
---

# Block syncing of specific file types - SharePoint in Microsoft 365 | Microsoft Learn

You can prevent users from uploading specific file types when they sync their OneDrive files.

This setting prevents file types from being uploaded but not downloaded. If users already blocked file types in their OneDrive, the files sync to their computer, but any changes they make on their computer aren't uploaded.

Note

The OneDrive sync app doesn't sync .tmp and .ini files.

## To block uploading of specific file types

1. Go to [Settings in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185072), and sign in with an account that has [admin permissions](/en-us/sharepoint/sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the Sharing page.
2. Select **Sync**.

    ![Sync settings in the SharePoint admin center](sharepointonline/media/sp-sync-settings.png)
3. Select the **Block upload of specific file types** check box.
4. Enter the file name extensions you want to block, for example: **exe** or **mp3**.

    Important

    Don't include the periods with the extensions, or any other punctuation, spaces, or special characters.
5. Select **Save**.

    Note

    When you configure this setting, it takes approximately 8 hours for the OneDrive sync app to detect it and apply the change.

For info about setting this sync app restriction by using PowerShell, see [Set-SPOTenantSyncClientRestriction](/en-us/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction). For info about using a policy to block upload of specific files, see [Exclude specific kinds of files from being uploaded](use-group-policy#exclude-specific-kinds-of-files-from-being-uploaded).