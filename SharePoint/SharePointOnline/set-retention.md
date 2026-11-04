---
layout: Conceptual
title: Set the OneDrive retention for deleted users - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/set-retention
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-04-05T00:00:00.0000000Z
ms.reviewer: jmcdowe
ms.author: v-mactran
author: MachelleTranMSFT
manager: jtremper
audience: Admin
f1.keywords:
- CSH
ms.topic: how-to
ms.custom:
- O365E_ODACStorage
- seo-marvel-apr2020
- admindeeplinkSPO
- onedrive-toc
ms.service: onedrive
ms.localizationpriority: medium
ms.collection:
- Strat_OD_admin
- M365-collaboration
- Essentials-manage
search.appverid:
- ODB160
- ODB150
- MET150
ms.assetid: fa1641ea-9f03-4f34-a826-dbd8697e76fe
description: Learn how to specify how long the OneDrive files of deleted users are preserved.
locale: en-us
document_id: 74b17db8-5758-8315-6765-aae7cbfb1b61
document_version_independent_id: 9d5ebe6b-e026-3e90-62d6-b10cb09258d3
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/set-retention.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: set-retention
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/set-retention.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 9baf2afa-202a-bf87-7f49-f11b790102be
---

# Set the OneDrive retention for deleted users - SharePoint in Microsoft 365 | Microsoft Learn

If a user's Microsoft 365 account is deleted, their OneDrive files are preserved for a period of time. You can set this time period.

## Set the retention time for OneDrive accounts

1. Go to [**Settings** in the new SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185072), and sign in with an account that has [admin permissions](/en-us/sharepoint/sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the Sharing page.
2. Select the **Retention** setting.

    ![Retention setting in the SharePoint admin center](sharepointonline/media/sp-retention.png)
3. Enter a value from 30 through 3650 in the **Days to retain files a deleted user's OneDrive** box.

    The setting is activated for the next user that is deleted as well as any users that are in the process of being deleted. The count begins as soon as the user account was deleted in the Microsoft 365 admin center, even though the deletion process takes time.
4. Select **Save**.