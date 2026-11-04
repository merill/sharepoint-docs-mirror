---
layout: Conceptual
title: Overview of search in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/overview-of-search
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
ms.date: 2024-04-24T00:00:00.0000000Z
audience: Admin
f1.keywords:
- CSH
ms.topic: overview
ms.service: sharepoint-online
ms.subservice: admin
ms.collection: M365-collaboration
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.assetid: 479cfd6b-900b-46aa-b497-c13787771d3f
description: Learn how you can customize the search experience in Microsoft SharePoint to help users find the information they're looking for.
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
locale: en-us
document_id: 79ad975e-61e1-b694-e5ac-b74ad0ea914d
document_version_independent_id: 15aa9b1f-4682-f1f8-537a-87ba97956773
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/overview-of-search.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: overview-of-search
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/overview-of-search.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 08d7fdf9-6290-1103-cc19-650779053e55
---

# Overview of search in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn

If you're responsible for search in your organization, learn how you can tailor the search experience to your organization and make search even better for your users.

SharePoint in Microsoft 365 has both a classic and a modern search experience, where [Microsoft Search in SharePoint](/en-us/microsoftsearch/overview-microsoft-search) is the modern search experience. As a search admin, you can’t enable or disable either search experience, both are enabled by default.

Users get the classic search experience on publishing sites, classic team sites, and in the Search Center. Users get the Microsoft Search experience on the SharePoint start page, hub sites, communication sites, and modern team sites. The most visible difference is that the Microsoft Search box is placed at the top of SharePoint, in the header bar. Another difference is that Microsoft Search is personal. The results one user sees are different from what other users see, even when they search for the same words. Users see results before they start typing in the search box, based on their previous activity and trending content in Microsoft 365, and the results update as they type. The search results are easy to explore without any effort from you as an admin. Learn more about the Microsoft Search experience for users in [Find what you need with Microsoft Search](https://support.office.com/article/d5ed5d11-9e5d-4f1d-b8b4-3d371fe0cb87).

Both search experiences use the same search index to find search results. You can customize and tailor the classic search experience more than Microsoft Search in SharePoint. Some classic search settings can impact both experiences, [learn how to avoid impacting Microsoft Search](differences-classic-modern-search). Read [When to use which search experience](get-started-with-modern-search-experience) to decide which experience is best for your organization.

See the following main areas where you can customize and impact the search experience and make sure that search is performing the way you want. The high-level overview of [How search works](overview-of-search#howsearchworks) can also help you understand where and how you can impact the search experience in SharePoint.

Many of the classic search features are available on the [search administration page](manage-search-the-admin-center) in the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219).

## 1. Make sure the content can be found

The content must be crawled and added to the search index for your users to find what they're looking for when they search in SharePoint. Microsoft Search uses the same index of SharePoint content as classic search does.

See how you can make content searchable, and how you can crawl content to get it into the search index. Also, see how you can help users search for content across Microsoft 365 and on-premises SharePoint Server at the same time. [Learn more](make-sure-content-can-be-found)

## 2. Make the search results look great

Presenting the search results the right way makes content easier to find.

See how you can manage the classic experience in the Search Center in SharePoint, and how you can use the different search Web Parts to help each user find what they're looking for. [See Make the search results look great](make-search-results-look-great)

## 3. Show relevant search results

All search results are not relevant to everyone all the time.

See how you can show each user exactly the results they're looking for. [See Show the right search results](show-relevant-search-results)

## 4. Check logs, limits and reports

See how you can check if the crawler has added content to the search index, and if your users are finding what they're looking for. Look up the limits for search, for example how many entries you can have in a custom search dictionary. [See Check logs, limits and reports](check-logs-limits-and-reports)

## How search works

This high-level overview of how search works can help you understand where and how you can customize the search in SharePoint.

In lists and libraries, site columns store detailed information about each document.

1. Search **crawls** the lists and libraries and adds the site columns and values to the search index.
2. In the **search index**, site columns are mapped to [managed properties](/en-us/sharepoint/manage-search-schema#managed-properties-and-search).
3. When a user enters a **query** in a search box, the query is sent to the search index.
4. The search engine finds **matching results**, and sends them to a search results page.

![A schematic diagram showing the flow from lists/libraries to index, and from search page to index to search results page.](sharepointonline/media/33dc2915-da17-4276-b8eb-79609d485d33.png)