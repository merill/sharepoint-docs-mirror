---
layout: Conceptual
title: Prevent users from installing the OneDrive sync app - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/prevent-installation
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: cagreen
ms.author: v-mactran
author: MachelleTranMSFT
manager: jtremper
ms.date: 2025-04-05T00:00:00.0000000Z
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: onedrive
ms.localizationpriority: medium
ms.collection: M365-collaboration
ms.custom:
- admindeeplinkSPO
- onedrive-toc
search.appverid:
- ODB160
- ODB150
- MET150
ms.assetid: b59cf952-f5a3-40ae-9159-36d5f869422c
description: Learn how to hide the Sync button to prevent users from downloading and installing the new OneDrive sync app.
locale: en-us
document_id: 6a85e485-26ac-05ee-8cb7-cb94ec5881c3
document_version_independent_id: 4d0a623b-20e3-7e6e-06a9-593d981278f1
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/prevent-installation.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: prevent-installation
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/prevent-installation.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: d5114362-365f-56d8-797e-66efc0ec6474
---

# Prevent users from installing the OneDrive sync app - SharePoint in Microsoft 365 | Microsoft Learn

The Sync button helps users install and set up the new OneDrive sync app. If you want to manage the rollout of the sync app to your organization, you can hide the Sync button on the OneDrive website to prevent your users from downloading the sync app themselves.

## To prevent users from downloading the OneDrive sync app

1. Go to [Settings in the new SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185072), and sign in with an account that has [admin permissions](/en-us/sharepoint/sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the Sharing page.
2. Select **Sync**.

    ![Sync settings in the SharePoint admin center](sharepointonline/media/sp-sync-settings.png)
3. Clear the **Show the Sync button on the OneDrive website** check box.
4. Select **Save**.