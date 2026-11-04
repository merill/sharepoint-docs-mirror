---
layout: Conceptual
title: Check logs, limits and reports - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/check-logs-limits-and-reports
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
ms.date: 2017-06-14T00:00:00.0000000Z
audience: Admin
f1.keywords:
- NOCSH
ms.topic: overview
ms.service: sharepoint-online
ms.subservice: platform
ms.collection: M365-collaboration
ms.localizationpriority: medium
ms.custom: admindeeplinkSPO
search.appverid:
- SPO160
- MET150
ms.assetid: 581ea83b-5cb8-4603-80c1-e86eb59909c1
description: See if the crawler has added content to the search index, and if your users are finding what they're looking for in SharePoint.
locale: en-us
document_id: 29e17f59-b027-4994-a928-4ef9f5db58cd
document_version_independent_id: 10c23c98-44d1-c53d-a6ab-86345cafed85
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/check-logs-limits-and-reports.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: check-logs-limits-and-reports
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/check-logs-limits-and-reports.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
platformId: b1b27536-feda-34ee-9bf2-1bb2ff758252
---

# Check logs, limits and reports - SharePoint in Microsoft 365 | Microsoft Learn

See if the crawler has added content to the search index, and if your users are finding what they're looking for in SharePoint.

## View search usage reports

This article describes how you can use search reports in the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219) to find answers to questions about how search is being used in your organization. You can for example see the number of queries and the top queries. [Learn more](view-search-usage-reports-modern-sites).

## Query throttling

In SharePoint, you can't turn query throttling on or off, but you can use client-type information to make sure lower-priority clients like automated queries don't squeeze out higher-priority clients like UI. [Learn more](query-throttling).

## Set crawl log permissions

Use the crawl log to see if crawled content was successfully added to the search index, if it was excluded because of a crawl rule, or if indexing failed because of an error. [Learn more](set-crawl-log-permissions).

## Search limits

Look up the limits to SharePoint search. For example, there are limits to the number of entries you can have in a custom search dictionary and the number of results that can be returned for a query. [Learn more](search-limits).