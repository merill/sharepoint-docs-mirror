---
layout: Conceptual
title: Search limits for SharePoint - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/search-limits
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2024-11-14T00:00:00.0000000Z
ms.reviewer: 
ms.author: jtremper
author: maggierui
manager: jtremper
audience: End User
f1.keywords: NOCSH
ms.topic: reference
ms.service: sharepoint-online
ms.subservice: platform
ms.collection: M365-collaboration
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.assetid: 7c06e9ed-98b6-4304-a900-14773a8fa32f
description: Learn about Search limits for SharePoint.
locale: en-us
document_id: 171ee42a-95a9-6543-dd99-696ba7025cd0
document_version_independent_id: a3b3b40f-b808-7ac6-b420-a9b7bb0361fb
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/search-limits.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: search-limits
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/search-limits.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: b28515a8-627c-cc14-11d2-8434f16d4f88
---

# Search limits for SharePoint - SharePoint in Microsoft 365 | Microsoft Learn

As an admin who manages SharePoint (for more info, see [SharePoint search administration overview](manage-search-the-admin-center)), you should also be aware of limits to search. For example, there are limits to the number of entries you can have in a custom search dictionary or the number of rows that are returned as part of a search.

There are two types of limits:

- **Boundary** A number that can't be exceeded.
- **Supported** A recommended number, based on testing that Microsoft has done, that shouldn't be exceeded. If you exceed a supported limit, you might encounter unexpected results or see a significant decrease in performance.

These limits apply to all SharePoint plans.

The following table lists the limits for SharePoint search.

| Limit | Maximum value | Limit type | Notes |
| --- | --- | --- | --- |
| Size of document that can be downloaded by the crawl components | - All File Types: 150 MB - PDF, PPTX, PPT, DOC, DOCX: 512 MB | Boundary | Crawl processing supports files up to 150 MB for all types, with an extended limit of 512 MB for PDF, PPTX, PPT, DOC, and DOCX formats. For files exceeding these limits, only document metadata is downloaded, while the full content is NOT downloaded and remains unavailable for search. |
| Parsed content size | 2 million characters | Boundary | Search stops parsing an item after it has parsed up to 2 million characters of content from it, including the item's attachments. The actual number of parsed characters can be lower than this limit because search uses a maximum of 30 seconds on parsing a single item and its attachments. When search stops parsing an item, the item is marked as partially processed. Any unparsed content isn't processed and therefore isn't indexed. |
| Characters processed by the word breaker | 1,000,000 | Boundary | Search breaks content into individual words (tokens). The word breaker produces tokens from the first 1,000,000 characters of a single item, including the item's attachments.  The actual amount of tokens can be lower than this limit because search uses a maximum of 30 seconds on word breaking. Any remaining content isn't processed. |
| Indexed managed property size | 512 KB per managed property that is set to either "searchable" or "queryable" | Boundary |  |
| Retrievable managed property size | 64 KB per managed property | Boundary |  |
| Sortable and refinable managed property size | 16 KB per managed property | Boundary |  |
| Token size | Variable - the size depends on the word breaker, and the word-breaker is language-dependent. | Boundary | Search can index tokens of any length but the word breaker that is used to produce tokens can limit the token length. Word breakers are language-aware components that break content into single words (tokens). |
| Unique indexed tokens per managed property | 10,000 | Boundary | This is the maximum number of unique tokens that can be added to the search index per managed property. If the limit is exceeded, the index contains the first 10,000 tokens from the managed property and the file will be marked as partially processed by setting the IsPartiallyProcessed property to true. |
| Distinct users or Active Directory / Microsoft Entra security groups having access to an item | 10,000 | Boundary | When more than 10,000 distinct users or Active Directory / Microsoft Entra security groups have access to an item, the item isn't searchable by any user. Such items will only be returned as part of an eDiscovery query through the Security & Compliance center. |
| Number of entries in a custom search dictionary | 5,000 terms per tenant | Boundary | This limits the number of terms allowed for inclusions and exclusions dictionaries for query spelling correction and company extraction. You can store more terms than this limit in the term store, but search only uses 5,000 terms per tenant. |
| Managed property mappings | 100 per managed property | Supported | Crawled properties can be mapped to managed properties. Exceeding this limit may decrease crawl speed and query performance. |
| Values per managed property | 1,000 | Boundary | A managed property can have multiple values of the same type. This is the maximum number of values per managed multi-valued managed property per document. If this number is exceeded, the remaining values are discarded. |
| Number of bytes in a multi-valued string property | 32 KB | Boundary | If you reach this limit, the multi-valued property is truncated. |
| Unique contexts used for ranking | 15 unique contexts per rank model | Boundary |  |
| Authoritative pages | 1 top level and minimal second- and third-level pages per tenant | Supported | Use as few second- and third-level pages as possible while still achieving the desired relevance.  If you add additional pages, you may not achieve the desired relevance. Add the key site to the first relevance level. Add more key sites at either second or third relevance levels, one at a time. Evaluate relevance after each addition to ensure that you have achieved the desired relevance effect. |
| Text length for queries using Keyword Query Language | 4 KB (4,096 characters) | Boundary |  |
| Number of rows in a result set | 500 | Boundary | To display the entire result set, issue more paging queries.  For Discovery queries the maximum number of rows in a result set is 10,000. |
| User-defined full-text indexes | 3 | Boundary |  |
| Maximum number of on-premises items indexed in Microsoft 365 | 20 million items | Threshold | For each 1 TB of storage space your tenant has in Microsoft 365, you can index 1 million items of on-premises content in your tenant's search index in Office 365 with the cloud hybrid search solution. This quota is by default limited upwards to 20 million items. To increase the number of items that can be indexed beyond 20 million items, contact Microsoft Support. |