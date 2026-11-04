---
layout: Conceptual
title: Remove search results - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/remove-search-results
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2018-07-11T00:00:00.0000000Z
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
audience: End User
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.collection: M365-collaboration
ms.localizationpriority: medium
ms.custom: admindeeplinkSPO
search.appverid:
- SPO160
- MET150
ms.assetid: b8177720-ff41-478e-bbe7-72183b97824f
description: As a search administrator, you can temporarily remove items from the search results with immediate effect. These items can be documents, pages, or sites that you don't want users to see when they search.
locale: en-us
document_id: 6483a618-3769-564c-6497-cede9ab053c9
document_version_independent_id: 6953d747-40ec-6a06-7877-a98e42dcce1f
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/remove-search-results.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: remove-search-results
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/remove-search-results.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 70b06ff5-c4a0-2a01-9dec-1abb8c41021e
---

# Remove search results - SharePoint in Microsoft 365 | Microsoft Learn

As a user who has [SharePoint administrator](/en-us/sharepoint/site-permissions#site-admins) or [above](/en-us/sharepoint/site-permissions) permissions in Microsoft 365, you can temporarily remove items from search results with immediate effect. The items that you can remove can be documents or pages that you don't want users to see. An example of this could be a Word document containing an invitation to an event that has been canceled, but the organizer has not removed the document from the site yet. Removing a result removes it from both classic and modern search results.

Important

This is only a quick fix! Unless you delete the items or change the permissions of items manually, they will show up again in your search results after the next crawl.

1. Go to [**More features** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185077), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.
2. Under **Search**, select **Open**.
3. On the **search administration** page, select **Remove Search Results**.
4. On the **Remove Search Results** page, in the **URLs to remove** box, enter the URLs that you want to remove from the search results, for example, `https://contoso.sharepoint.com/sites/site1`. URLs cannot contain a wildcard (\*) character. Enter one URL on each line.
5. Select **Remove Now**. The URLs are immediately removed from your search results.