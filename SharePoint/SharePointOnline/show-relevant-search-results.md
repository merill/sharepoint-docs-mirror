---
layout: Conceptual
title: Show the right search results - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/show-relevant-search-results
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
search.appverid:
- SPO160
- MET150
ms.assetid: 02b36b7c-c1e1-4d73-9a92-5658389ed4b6
description: All search results are not relevant to everyone all the time. Learn how you can help users find exactly the results they're looking for in SharePoint.
locale: en-us
document_id: eff3c5a8-5f21-74fb-0492-224ca0060ff1
document_version_independent_id: 72ec4094-8599-8e52-c8a2-1e7331a06c73
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/show-relevant-search-results.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: show-relevant-search-results
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/show-relevant-search-results.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 3c8a5df8-e99b-e925-a108-6d2a8c557034
---

# Show the right search results - SharePoint in Microsoft 365 | Microsoft Learn

All search results are not relevant to everyone all the time. Learn how you can help users find exactly the results they're looking for in SharePoint. SharePoint has both a classic and a modern search experience, [learn about the differences between the classic and modern search experiences in SharePoint](differences-classic-modern-search).

## Manage the search schema

The search schema controls what users can search for, how they can search it, and how the results get presented on your search websites. In the search schema, you can view, create, or change managed properties, and map crawled properties to managed properties. Learn about [the search schema](manage-search-schema).

## Manage query rules

Query rules apply to the classic search experience. They consist of conditions and associated actions. When a query meets the conditions in a query rule, the search system performs the actions specified in the rule. Query rules can be used to promote results to the top of the result list.Learn about [managing query rules](manage-query-rules).

## Manage query suggestions

Query suggestions are words that appear below the search box as a user types a query. SharePoint automatically creates a query suggestion when you've clicked a search result for a query at least six times. In the classic search experience you can also import your own lists of query suggestions to SharePoint. Learn about [managing query suggestions](manage-query-suggestions).

## Using query transforms

Query transforms apply to the classic search experience. You can configure a query transform to replace properties of a query, such as the result source that the query will use to get search results, or the sort order that it will use when it displays search results. Read [Understanding query transforms](https://support.office.com/article/b31631a5-0c1f-436e-8061-fd807bb96ae1) to learn more.

## Manage result sources

Result sources limit searches to certain content, or to a subset of search results. You can also use result sources to send queries to external providers such as Bing. Learn about [managing result sources](manage-result-sources)

## Manage result types

Results types apply to the classic search experience. A result type specifies one or more conditions to compare search results against, and an action to take if a search result meets those conditions. The action specifies the display template to use for the search result. Learn about [managing result types](manage-result-types).

## Manage search dictionaries

Search dictionaries apply to the classic search experience. You can use search dictionaries to include or exclude words for query spelling correction, and you can include or exclude company names to be extracted from the content of indexed documents. Learn about [managing search dictionaries](manage-search-dictionaries).

## Manage authoritative pages

You can influence the pages or documents that should appear at the top of your list of search results by identifying authoritative pages - high-quality pages that link to the most relevant information. Authoritative pages apply to the classic search experience. Learn about [managing authoritative pages](manage-authoritative-pages).

## Export and import search settings

You can export and import customized search configuration settings between tenants, site collections, and sites. The settings include all customized query rules, result sources, result types, ranking models and site search settings. Learn about [exporting and importing search settings](export-and-import-search-settings).