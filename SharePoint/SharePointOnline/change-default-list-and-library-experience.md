---
layout: Conceptual
title: Change the default list and library experience - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/change-default-list-and-library-experience
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-06-25T00:00:00.0000000Z
ms.reviewer: jdemaris
manager: jtremper
ms.author: ruihu
author: maggierui
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.service: sharepoint-online
ms.subservice: lists
ms.localizationpriority: medium
ms.collection:
- Strat_SP_admin
- M365-collaboration
search.appverid:
- SPO160
- BSA160
- GSP150
- MET150
ms.assetid: a0d90eaf-5755-4b8d-96ee-9e25bdf9114e
description: 'How to select the new or classic list and library experience for a site. '
locale: en-us
document_id: 4f1bd4ab-c640-1db8-05bb-e249129dfa46
document_version_independent_id: 4ceb7bc8-39c0-61fb-b31c-381cb7a5018b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/change-default-list-and-library-experience.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: change-default-list-and-library-experience
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/change-default-list-and-library-experience.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: b2e1611e-82c1-7815-be33-a741d2e343a4
---

# Change the default list and library experience - SharePoint in Microsoft 365 | Microsoft Learn

The new SharePoint list and library experience is faster, simpler, and responsive on mobile devices. It also supports many new capabilities that are not available in the classic experience, including Power Apps and Power Automate integration, the Filters pane, and column formatting. Many sites that have features or customizations that don't work in the new experience will automatically switch back to the classic experience. For more information about this behavior, see [Differences between the new and classic experiences for lists and libraries](https://support.office.com/article/30e1aab0-a5cc-4363-b7f2-09e2ae07d4dc). To detect lists that won't work well with the new experience, run the [SharePoint Modernization scanner](/en-us/sharepoint/dev/transform/modernize-scanner).

It's no longer possible to select the classic experience as the default for all sites in your organization. Instead, we recommend setting it for only the specific sites that need it. You can activate the site collection feature *SharePoint Lists and Libraries experience* to turn off the new list and library experience for a site collection. To learn how, see [Enable or disable site collection features](https://support.office.com/article/a2f2a5c2-093d-4897-8b7f-37f86d83df04). For info about changing this setting using PowerShell, see [Opting out of the modern list and library experience](/en-us/sharepoint/dev/transform/modernize-userinterface-lists-and-libraries-optout).

Note

Users can select the default experience for an individual list or library, overriding what you set. For info, see [Switch the default experience for lists or document libraries from new or classic](https://support.office.com/article/66dac24b-4177-4775-bf50-3d267318caa9).