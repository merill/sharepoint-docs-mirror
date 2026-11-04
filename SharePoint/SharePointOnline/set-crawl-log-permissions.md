---
layout: Conceptual
title: Crawl log permissions - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/set-crawl-log-permissions
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
- SPO160
- BSA160
- GSP150
- MET150
ms.assetid: b3a165dc-d2ad-42d3-8a41-d3fb64d0ad86
description: You can grant users or groups read access to crawl log information for the tenant. A typical use case is in eDiscovery, where users may need to check whether crawled content was in fact added to the search index.
locale: en-us
document_id: 852613da-1319-1d20-04d4-a3fd9aa6bc72
document_version_independent_id: c912d988-603a-9e37-cd43-aee69bf01c91
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/set-crawl-log-permissions.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: set-crawl-log-permissions
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/set-crawl-log-permissions.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
platformId: 84277db0-0f29-ed78-b059-050373630f55
---

# Crawl log permissions - SharePoint in Microsoft 365 | Microsoft Learn

As a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365, you can grant users read access to crawl log information for the tenant. The crawl log tracks information about the status of crawled content.

A typical use case is in eDiscovery, where you can grant a security group permission to view the crawl log information for the tenant. The users in the security group can view the crawl log data via the eDiscovery portal to check whether crawled content was successfully added to the search index, or whether indexing failed because of an error. For more information, see [Get started with eDiscovery (Standard) in Microsoft Purview](/en-us/microsoft-365/compliance/get-started-core-ediscovery) and [Investigating partially indexed items in eDiscovery](/en-us/microsoft-365/compliance/investigating-partially-indexed-items-in-ediscovery).

## Grant users permission to view the crawl log information

1. Go to [**More features** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185077), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

Note

If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.

1. Under **Search**, select **Open**.
2. On the **search administration** page, select **Crawl Log Permissions**.
3. In the **Crawl Log Permissions** box, enter names or email addresses. The names of valid users or user groups appear in the list as you enter letters in the box.
4. Select **OK**.