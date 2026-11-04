---
layout: Conceptual
title: View search usage reports in modern sites - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/view-search-usage-reports-modern-sites
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: 
ms.author: ruihu
author: Lovina-Saldanha
manager: dansimp
ms.date: 2021-06-27T00:00:00.0000000Z
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
description: Learn how you can view search usage reports in modern sites.
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
locale: en-us
document_id: 1ada8124-63bd-7532-3cc6-28eb2c9dbc45
document_version_independent_id: 1533d7e3-0127-2008-b567-bad28c67727c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/view-search-usage-reports-modern-sites.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: view-search-usage-reports-modern-sites
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/view-search-usage-reports-modern-sites.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
platformId: bd64ff19-a098-2e29-7f67-e7dc280691d0
---

# View search usage reports in modern sites - SharePoint in Microsoft 365 | Microsoft Learn

If you're a SharePoint Administrator in your organization, you're probably asked questions about search usage, such as:

- What are the top queries on my site per day or per month?
- How many search queries are users performing on average?
- Which queries are getting low clicks as they're not showing up in any results?
- How often are query rules firing and how often are people clicking promoted results?

## To view a report

To view search usage reports in modern sites, navigate to **Site settings** &gt; **Site collection administration** &gt; **Microsoft Search** &gt; **Configure search settings** &gt; **Insights**.

Modern search usage reports with Microsoft Search provide a few graphs and tables generated from searches that are executed from search in modern sites. You can see data from the past 31 days (about one month), per day, or monthly for the previous year.

The first date picker lets you pick past 31 days (about one month) or past 12 months for the first two graphs. The second date picker lets you select a particular day or month for the bottom three tables (top, abandoned, no results). Downloading a report will allow you to see reports from a broader range of time. Click on the download arrow and select past 31 days (about one month) or past 12 months. The report is downloaded as an Excel spreadsheet. If you selected the past 31 days (about one month), the spreadsheet will have an individual tab for each day. The past 12 months download will have a tab for each month.

[![view usage reports.](sharepointonline/media/view-search-usage-reports-1.png)](sharepointonline/media/view-search-usage-reports-1.png#lightbox)

## Overview of search reports

| Report | Description |
| --- | --- |
| Query Volume | This report shows the number of search queries performed. Use this report to identify search query volume trends and to determine periods of high and low search activity. |
| Top Queries | This report shows the most popular search queries. A query is added to this report when it's searched at least three times with a click on a result. Use this report to understand what types of information your users are searching for. |
| Abandoned Queries | This report shows popular search queries that receive low click-through. Use this report to identify search queries that might create user dissatisfaction and to improve the finding of content. |
| No Results Queries | This report shows popular search queries that returned no results. Use this report to identify search queries that might create user dissatisfaction and to improve the finding of content. |
| Impression distribution | This report shows impressions over various time frames. The timeline shows the daily number of impressions for a result type. Determine which result type is most frequently, or infrequently, used. Use this report to understand what result types users are using and any changes in user behavior over a period of time. |