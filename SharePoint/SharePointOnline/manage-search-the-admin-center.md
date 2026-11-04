---
layout: Conceptual
title: SharePoint classic search administration overview - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/manage-search-the-admin-center
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
ms.topic: overview
ms.service: sharepoint-online
ms.subservice: admin
ms.collection: M365-collaboration
ms.localizationpriority: medium
ms.custom: admindeeplinkSPO
search.appverid:
- SPO160
- MET150
ms.assetid: 21ea5d29-6cb2-4e40-9cc8-77c05d94beb5
description: Use the search page in the classic SharePoint admin center to customize the classic search experience for users.
locale: en-us
document_id: abb4771c-6c09-daca-5a88-e6f0b2e08175
document_version_independent_id: 5156d0e5-1a97-b722-a8dd-f6c7a2ecd1e1
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/manage-search-the-admin-center.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-search-the-admin-center
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/manage-search-the-admin-center.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 13dcc3cf-522e-0af3-f94b-c84ead167200
---

# SharePoint classic search administration overview - SharePoint in Microsoft 365 | Microsoft Learn

As a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) and [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365, you can customize and impact the search experiences for your users. You can define searchable managed properties in the search schema, identify high-quality pages to improve relevance, manage query rules and result sources, and remove individual results. You can also evaluate any changes by viewing reports about usage and search.

The changes you make from the search administration page are valid for the whole tenant, but you can also customize search on site collection level and on site level.

You can customize and tailor the classic search experience more than Microsoft Search in SharePoint. Some classic search settings can impact both experiences, [learn how to avoid impacting Microsoft Search](differences-classic-modern-search).

## How to get to the classic search administration page

1. Go to [**More features** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185077), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.
2. Under **Search**, select **Open**.

## What do you want to do?

| Choose this option: | To do this: |
| --- | --- |
| [Manage the search schema](manage-search-schema) | Learn how to create a customized search experience by changing the search schema. In the search schema, you can view, create, or change managed properties, and map crawled properties to managed properties. |
| [Manage search dictionaries](manage-search-dictionaries) | Learn how to manage search dictionaries for classic search. You can use search dictionaries to include or exclude company names to be extracted from the content of your indexed documents, or you can include or exclude words for query spelling correction. |
| [Manage authoritative pages](manage-authoritative-pages) | Influence the pages or documents that should appear at the top of the search results by identifying high-quality pages, also known as authoritative pages, for the classic search experience. |
| [Manage query suggestion settings](manage-query-suggestions) | Learn how to add phrases that you want the system to suggest to users as they search for an item using classic search, and how to add phrases that you don't want the system to suggest to users. Also, learn how to turn this feature on or off. |
| [Manage result sources](manage-result-sources) | Result sources limit searches to certain content or to a subset of search results. Learn how to create your own result sources, or change the predefined result sources. |
| [Manage query rules](manage-query-rules) | Improve search results in the classic search experience by creating and managing query rules. Query rules can help searches respond to the intent of users. |
| [Manage query client types](query-throttling) | Learn how query client types decide in which order queries are performed in the classic search experience. |
| [Remove search results](remove-search-results) | Learn how you can temporarily remove items from the search results with immediate effect. These items can be documents, pages, or sites that you don't want users to see when they search. |
| [View usage and search reports](view-search-usage-reports-modern-sites) | View usage reports and search reports and see how often your users search, what their top queries are, and which queries they're having trouble getting answers for. |
| [Manage Search Center settings](specify-default-search-center) | Choose where searches in the classic search experience should go by specifying the URL of your Search Center. |
| [Import and export customized search configuration settings](export-and-import-search-settings) | Learn how to export and import customized search configuration settings between tenants, site collections, and sites. |
| [Manage crawl log permissions](set-crawl-log-permissions) | Learn how to grant users or groups read access to crawl log information for the tenant. A typical use case is in eDiscovery, where users may need to check whether crawled content was in fact added to the search index. |

Note

Thesaurus isn't available in SharePoint in Microsoft 365.