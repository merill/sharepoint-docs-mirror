---
layout: Conceptual
title: Manage app requests - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/manage-app-requests
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-01-21T00:00:00.0000000Z
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
ms.collection: M365-collaboration
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
description: Learn how to manage app requests in SharePoint in Microsoft 365.
locale: en-us
document_id: a9e4cbdd-9db7-175b-7dec-c50d27d17057
document_version_independent_id: 9e265dbe-aa8a-2837-4551-06b1a311ef8c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/manage-app-requests.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-app-requests
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/manage-app-requests.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 16a417ff-edc4-a7a3-d3f2-a246fdeb98e3
---

# Manage app requests - SharePoint in Microsoft 365 | Microsoft Learn

When users request an app, they are requesting that an admin get that app on their behalf. In an app request, users can request a specific number of licenses, and they can provide a business justification for why they need the app. App requests are saved to the App Requests list in the Apps site.

To manage app requests

1. Go to the [More features page of the new SharePoint admin center](https://admin.microsoft.com/sharepoint?page=classicfeatures&amp;modern=true), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 Germany, [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), then browse to the SharePoint admin center and open the More features page.

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.
2. Under **Apps**, select **Open**, and then select **More features**.
3. Select **Configure store settings**.
4. Select **Click here to view app requests**. Then select **Active requests**.

To approve an app

1. In the **Active Requests** list, select a request.
2. On the app request form, add any comments in the **Comments** field.
3. Select **Approve and add this app**.
4. If the app allows you to automatically add it to all sites, choose if you want to add it to all sites.
5. Confirm the data access required by the app by selecting **Confirm**.

    ![Screenshot of the Confirm data access dialog box.](sharepointonline/media/app-confirm-data-access.png)
6. If the app requires additional permissions, go to the API access page to approve those permissions.
7. Close the panel.

To decline an app

1. In the **App Requests** list, select a request.
2. On the app request form, add any comments in the **Comments** field.
3. Select **Decline request**.
4. On the confirmation panel, select **Decline request**.

If you didn't add the app to all sites in the approval process, users need to add it to the site. See [Add an app to a site](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43).

Site users who request apps can view their requests by going to **Settings** &gt; **Add an app** &gt; **Your Requests**.