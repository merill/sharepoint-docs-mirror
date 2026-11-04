---
layout: Conceptual
title: SharePoint authentication - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/authentication
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: 
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 2026-01-26T00:00:00.0000000Z
audience: Admin
f1.keywords:
- CSH
ms.topic: article
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- M365-collaboration
- M365-sam
ms.custom:
- Adm_O365
search.appverid:
- MET150
- SPO160
- MOE150
- MED150
- MBS150
- BSA160
- BCS160
ms.assetid: 77965e8d-48ad-47bd-a656-57f17d6d1cc7
description: Explains how sessions and cookies work in SharePoint in Microsoft 365.
locale: en-us
document_id: 351d4d9a-7c97-ee21-fe87-1071ae099717
document_version_independent_id: 818f8e43-033e-868c-6c66-39fc7840f65d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/authentication.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: authentication
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/authentication.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: dd0ca9fc-64ac-9d42-1a06-0177795578fd
---

# SharePoint authentication - SharePoint in Microsoft 365 | Microsoft Learn

SharePoint in Microsoft 365 serves a wide range of customers with a variety of usability and security needs. Some customers don't mind asking users to reauthenticate if it means their data will be more secure. Other customers want to minimize the number of sign-in screens that users see, especially in situations where it seems as though SharePoint should already know who the user is. Luckily, customers don't have to choose usability or security because they work together in a lot of great ways.

The following diagram outlines the SharePoint authentication process. It walks through how the scenario works using either your own Identity Provider (IdP) or the default Microsoft Entra IdP.

The Federation Authentication (FedAuth) cookie is for each top-level site in SharePoint such as the root site, OneDrive, and the admin center site. The root Federation Authentication (rtFA) cookie is used across all of SharePoint. When a user visits a new top-level site or another company's page, the rtFA cookie is used to authenticate them silently without a prompt. When a user signs out of SharePoint, the rtFA cookie is deleted.

![SharePoint Authentication Process](sharepointonline/media/sharepoint-entra-authentication.png)

Note

For information about SharePoint authentication in hybrid scenarios, see [The building blocks of Microsoft 365 hybrid](/en-us/sharepoint/hybrid/the-building-blocks-of-office-365-hybrid).

## Session and persistent cookies

By default, all SharePoint cookies are **session** cookies. These cookies are not saved to the browser's cookie cache and instead are deleted whenever the browser is closed. Microsoft Entra ID provides a **Keep Me Signed In** button during login that passes a signal to Microsoft 365 to enable **persistent** cookies. These cookies are saved to the browser's cache and will persist even if the browser is closed or the computer is restarted.

Persistent cookies have a huge impact on the sign-in experience by reducing the number of authentication prompts users see. Persistent cookies are also required for some SharePoint features, such as **Open with Explorer** and **Mapped Drives**.

For more info about session timeouts, see [Session timeouts for Microsoft 365](/en-us/office365/enterprise/session-timeouts).