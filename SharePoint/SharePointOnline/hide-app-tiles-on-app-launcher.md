---
layout: Conceptual
title: Hide the OneDrive and SharePoint app tiles - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/hide-app-tiles-on-app-launcher
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2018-07-11T00:00:00.0000000Z
ms.reviewer: trgreen
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords:
- CSH
ms.topic: how-to
ms.custom:
- SimpleTA
- admindeeplinkSPO
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Strat_SP_admin
- M365-collaboration
search.appverid:
- MET150
- SPO160
- MOE150
- MBS150
- SPB160
- BSA160
- GSP150
ms.assetid: d5e8dc9a-73f8-45e4-93b4-8e55b546a5af
description: See how to show or hide links to Sites or OneDrive.
locale: en-us
document_id: 96de5069-51dc-3934-ec44-cae3ab121476
document_version_independent_id: 21955afd-18c1-20f0-061f-f552f71fbfc1
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/hide-app-tiles-on-app-launcher.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: hide-app-tiles-on-app-launcher
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/hide-app-tiles-on-app-launcher.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 62d2e67c-f792-80f8-5f37-6ca71eb1605d
---

# Hide the OneDrive and SharePoint app tiles - SharePoint in Microsoft 365 | Microsoft Learn

By default, the OneDrive and SharePoint app tiles appear in the app launcher and on the Microsoft 365 admin center. If your subscription doesn't include one of these services, or if you don't want users using one of them, you can hide the app tile for it.

![Microsoft 365 start page with SharePoint selected](sharepointonline/media/4ff2c093-2b26-4d28-a65b-4d02e66818df.png)

Note

Hiding these services doesn't remove them for users. If users have saved the address of the service, they'll still be able to access it.  If users select a tile for a service they don't have, they'll see an Access Denied message.

## To show or hide app tiles

1. Go to [**Settings** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185072), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the Settings page.
2. Open the **Settings** page.
3. At the bottom of the page, select **go to the classic settings page**.
4. In **Show or Hide App Tiles**, select the tile you want to show or hide.

    ![Show or Hide App Tiles settings](sharepointonline/media/516f0f56-c44e-465e-8ec5-ba56fbbe2b3b.png)

    Note

    If you have an Office 365 Education subscription, you also have the option to hide **OneNote Class Notebooks** and **OneNote Staff Notebooks**.  Hiding the OneDrive tile also hides the tiles for Word, Excel, PowerPoint, OneNote, and Visio.
5. To save the settings, select **OK**.