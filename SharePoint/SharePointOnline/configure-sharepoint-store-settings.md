---
layout: Conceptual
title: Configure settings for the SharePoint Store - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/configure-sharepoint-store-settings
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2018-07-11T00:00:00.0000000Z
ms.reviewer: 
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.collection:
- M365-collaboration
- M365-sam
ms.custom: admindeeplinkSPO
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.assetid: 6b806fb8-9295-441d-b954-07009021dc48
description: Learn how to allow or prevent users from getting apps from the SharePoint Store, and how to manage app requests.
locale: en-us
document_id: 1b12ead9-dcc9-19af-e7b1-d846f8116300
document_version_independent_id: 45ad5ca0-5c6f-c058-90e7-27f7824e937e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/configure-sharepoint-store-settings.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: configure-sharepoint-store-settings
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/configure-sharepoint-store-settings.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 2b90abd2-3efb-52da-b5ff-2ad143756d42
---

# Configure settings for the SharePoint Store - SharePoint in Microsoft 365 | Microsoft Learn

The [SharePoint Store](https://appsource.microsoft.com/marketplace/apps?product=sharepoint) is a public marketplace that offers apps for Microsoft 365, as well as Dynamics 365 and Power Platform. Site users can access the SharePoint Store directly from a SharePoint site to browse for and add third-party apps. If a SharePoint environment has been configured to prevent users from getting apps from the SharePoint Store, users can still browse for and request apps. These requests are added to the App Requests list in the SharePoint admin center.

## Specify whether users can get apps from the SharePoint Store

By default, SharePoint is configured to allow users to get or request apps from the SharePoint Store. The option to change this setting will not be enabled if you have not yet created an Apps site. For information about how to create an Apps site, see [Use the Apps site to make custom business apps available for your SharePoint environment](use-app-catalog).

Even if you choose not to allow users to add apps from the SharePoint Store, they will still be able to browse the SharePoint Store and request apps.

1. Go to the [More features page of the SharePoint admin center](https://admin.microsoft.com/sharepoint?page=classicfeatures&amp;modern=true), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.
2. Under **Apps**, select **Open**, and then select **More features**.
3. Select **Configure store settings**.
4. Next to **App Purchases**, do one of the following:

    - If you want users to be able to add apps, select **Yes**.
    - If you do not want users to be able to get third-party apps, select **No**.

## Specify whether to allow apps for Office to start in documents

Documents stored on sites may contain apps for Office from several sources. You can specify whether or not you want to allow these apps to work when documents are opened in the browser.

1. Go to the [More features page of the SharePoint admin center](https://admin.microsoft.com/sharepoint?page=classicfeatures&amp;modern=true), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.
2. Under **Apps**, select **Open**, and then select **More features**.
3. Select **Configure store settings**.
4. Next to **Apps for Office from the Store**, do one of the following:

    - If you want to allow apps for Office to start when documents are opened in the browser, select **Yes**.
    - If you do not want to allow apps for Office to start when documents are opened in the browser, select **No**.