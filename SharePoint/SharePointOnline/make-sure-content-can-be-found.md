---
layout: Conceptual
title: Make sure content can be found - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/make-sure-content-can-be-found
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
ms.subservice: admin
ms.collection: M365-collaboration
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.assetid: 16fb530a-ed64-4fea-ab15-adf4b5fe96e9
description: The content must be crawled and added to the search index for your users to find what they're searching for in SharePoint.
locale: en-us
document_id: 32a618b8-9648-7b9a-af11-5bab6332d4c9
document_version_independent_id: a2340908-c5ea-3879-97ac-51160ed49b67
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/make-sure-content-can-be-found.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: make-sure-content-can-be-found
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/make-sure-content-can-be-found.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 3091141d-ff04-99f7-6453-a7de84c22f35
---

# Make sure content can be found - SharePoint in Microsoft 365 | Microsoft Learn

The content must be crawled and added to the search index for your users to find what they're searching for in Microsoft SharePoint. SharePoint in Microsoft 365 has both a classic and a modern search experience, both use the same search index. [Learn about the differences between the classic and modern search experiences in SharePoint](differences-classic-modern-search)

## Make site content searchable

When users search on a site, results can come from many places such as columns, libraries, and pages. A site owner can change search settings to decide whether or not content should appear in search results.

Users only see search results for content they have access to. Setting the right permissions for content ensure that people can see the right documents and sites in the search results. [Learn more](make-site-content-searchable).

## Crawl site content

In SharePoint, content is automatically crawled based on a defined crawl schedule. The crawler picks up content that has changed since the last crawl and updates the index.

In some cases, you may want to manually request crawling and full re-indexing of a site, a document library, or a list. [Learn more](crawl-site-content).

## Search across on-premises and online content

[Hybrid search in SharePoint](hybrid/hybrid-search-in-sharepoint) lets your users search for files and documents across SharePoint Server and Microsoft 365 at the same time. With [cloud hybrid search](hybrid/learn-about-cloud-hybrid-search-for-sharepoint), both on-premises and online content go into the index that both the classic and Microsoft Search experiences use.

## Remove search results temporarily

You can **temporarily** remove documents, pages and sites from search results with immediate effect. [Learn more](remove-search-results).