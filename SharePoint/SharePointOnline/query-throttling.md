---
layout: Conceptual
title: Manage query client types - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/query-throttling
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
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.collection: M365-collaboration
ms.custom: admindeeplinkSPO
ms.localizationpriority: medium
search.appverid:
- SPS150
- SPO160
- MET150
ms.assetid: 0d335bc4-e7a0-46bc-ba40-da34e414174f
description: Learn how query client types decide in which order queries are performed.
locale: en-us
document_id: 000117e6-5980-fe54-660d-9f39bb46371e
document_version_independent_id: a1963190-ece2-d603-477c-b1b47e548868
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/query-throttling.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: query-throttling
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/query-throttling.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: a81aa34d-9010-2fea-92db-56d6b60ba02e
---

# Manage query client types - SharePoint in Microsoft 365 | Microsoft Learn

**APPLIES TO:**![yes-img-13](sharepointserver/media/yes.png)2013 ![yes-img-16](sharepointserver/media/yes.png)2016 ![yes-img-19](sharepointserver/media/yes.png)2019 ![yes-img-se](sharepointserver/media/yes.png)Subscription Edition ![no-img-sop](sharepointserver/media/no.png)SharePoint in Microsoft 365

Learn how query client types decide in which order queries are performed.

A query client type is how a client performing a query tells the system what type of client it is. For example, a client might tell us it is UI, or an automated query. Query throttling monitors the use of resources and protects the search system. Administrators can use client-type information for throttling, to make sure lower-priority clients like automated queries don't squeeze out higher-priority clients like UI. Query client types are also used for things like logging, reports, and determining relevance.

The client sets the client type as a label in the query. The administrator configures the valid client types (though some are default and mandatory), and the client chooses one for each query.

Note

You can't turn query throttling on or off.

## Add a query client type

Note

You can change the name of a client type that has been created for your tenant only.

1. Go to [**More features** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185077), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

Note

If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.

1. Under **Search**, select **Open**.
2. On the search administration page, select **Manage Query Client Types**.
3. To add a client type, select **New Client Type**.
4. On the **Edit a client type** page, in the **Query Client Type** field, for the client type, enter a name.
5. From the **Throttling Tier** list, select either **Top**, **Middle**, or **Bottom**.

    Note

    Lower priority queries are throttled first. The search system processes queries from top tier to bottom tier.
6. Select **OK**.

## Prioritize a client query type

You can use throttling tiers to prioritize query processing. When the resource limit is reached, query throttling kicks in, and the search system processes queries, starting from the top tier, right through to the bottom tier.

1. Go to [**More features** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185077), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

Note

If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.

1. Under **Search**, select **Open**.
2. On the search administration page, select **Manage Query Client Types**.
3. Go to the **Client Type** section, and select the **System Type** that you want to change.
4. From the **Throttling Tier** list, select either **Top**, **Middle**, or **Bottom**.

    Note

    Lower priority queries are throttled first. The search system processes queries from top tier to bottom tier.
5. Select **OK**.