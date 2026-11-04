---
layout: Conceptual
title: Manage authoritative pages - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/manage-authoritative-pages
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
ms.assetid: 68429de6-7c7b-455c-a90a-2afaa3444647
description: You can influence the pages or documents that should appear at the top of your list of search results by identifying high-quality pages, also known as authoritative pages.
locale: en-us
document_id: 3575b7e0-e560-1504-bffc-ee0c0fa08943
document_version_independent_id: e4157d38-6f8d-d230-a874-4d599cd01297
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/manage-authoritative-pages.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-authoritative-pages
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/manage-authoritative-pages.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: ef84a951-057c-0d07-3a59-f3d39d12f659
---

# Manage authoritative pages - SharePoint in Microsoft 365 | Microsoft Learn

**APPLIES TO:**![yes-img-13](sharepointserver/media/yes.png)2013 ![yes-img-16](sharepointserver/media/yes.png)2016 ![yes-img-19](sharepointserver/media/yes.png)2019 ![yes-img-se](sharepointserver/media/yes.png)Subscription Edition ![no-img-sop](sharepointserver/media/no.png)SharePoint in Microsoft 365

As a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) and [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365, you can influence the pages or documents that should appear at the top of your list of search results by identifying high-quality pages, also known as authoritative pages. Authoritative pages link to the most relevant information. A typical example of an authoritative page could be the home page of your company portal.

Authoritative pages only work for **classic** search and only for web parts that use the **default** ranking model.

If you have specific knowledge of an area, you can influence the relative importance of pages by adding more levels of authoritative pages (second-level and third-level).

In the same way, you can also add non-authoritative pages. A typical example of a non-authoritative page could be the URL of a site that contains outdated information.

## Specify authoritative or non-authoritative pages

1. Go to [**More features** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185077), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.
2. Under **Search**, select **Open**.
3. On the search administration page, select **Manage Authoritative Pages**.
4. In the **Authoritative Web Pages** section, in the **Most authoritative pages** box, enter the URLs of pages that are the most important. Separate the URLs with returns so that there is one URL per line.
5. In the **Second-level authoritative pages** box, enter the URLs of any pages that should be seen as second-level.
6. In the **Third-level authoritative pages** box, enter the URLs of any pages that should be seen as third-level.
7. In the **Non-authoritative Sites** section, in the **Sites to demote** box, enter the URLs of any sites that you want to be ranked lower than all of the other sites. Type one URL per line.

    Tip

    All URLs whose prefix matches the prefix of a URL in the **Sites to demote** box are demoted. Example: Entering http://archive/ demotes the rank of all URLs that begin with http://archive/.
8. Select **OK**.

## How results are ranked

Classic search uses the list of authoritative pages to calculate the ranking of results. Static rank determines the relative importance of a page. Static rank is calculated as the smallest number of clicks that it would take a user to navigate from an authoritative page to a document. The closer a document is to the most authoritative page, the higher the static rank of the page is.