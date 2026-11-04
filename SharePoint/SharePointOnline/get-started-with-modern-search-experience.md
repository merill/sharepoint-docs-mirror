---
layout: Conceptual
title: Get started with the modern search experience - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/get-started-with-modern-search-experience
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2018-09-20T00:00:00.0000000Z
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: get-started
ms.service: sharepoint-online
ms.subservice: platform
ms.localizationpriority: medium
ms.collection:
- Strat_SP_modern
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
search.appverid:
- SPO160
- MET150
description: In this article, you'll learn about when to use the classic or modern search experience in SharePoint.
locale: en-us
document_id: b864d5f6-b3d0-418b-62f9-5e33a69c6e37
document_version_independent_id: 7763bfd1-5cda-ab14-b7e8-ff6b4f16200a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/get-started-with-modern-search-experience.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: get-started-with-modern-search-experience
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/get-started-with-modern-search-experience.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
platformId: aba3be70-7290-8a7f-6529-19eb29b30fc6
---

# Get started with the modern search experience - SharePoint in Microsoft 365 | Microsoft Learn

Microsoft Search is the modern search experience in SharePoint in Microsoft 365 and is a personalized experience. It uses the insights of the Microsoft Graph to show results that are relevant to you. Routine tasks such as finding the right version of a document, getting back to a presentation you were editing, or a document you were collaborating with others on, are easy. [Learn more about Microsoft Search for users](https://support.office.com/article/d5ed5d11-9e5d-4f1d-b8b4-3d371fe0cb87). The classic search experience, on the other hand, can be tailored more to your organization. [Learn about the differences between the search experiences](differences-classic-modern-search).

Both search experiences are turned on by default and as a search administrator you can't turn either search experience off. Which search experience your users see depends on where they search from:

- Users get the classic search experience on publishing sites, classic team sites, and in the Search Center.
- Users get the Microsoft Search experience on the SharePoint start page, hub sites, communication sites, and modern team sites. [Learn about classic and modern sites](https://support.office.com/article/5725c103-505d-4a6e-9350-300d3ec7d73f).

    If you're in a document library, the search box shows **Search this library**. If you're in the home page of the site, the box shows **Search this site**. In all other locations, the search box shows **Search**.

## Benefits of Microsoft Search in SharePoint

**Easy to search** - Microsoft Search suggests results based on users' previous activity in Microsoft 365, right in the search box. On the search results page the results are ordered by relevance.

**Find shared files** - Microsoft Search uses advanced query understanding to make finding shared files simple. Users can easily find files they're collaborating on.

**Show relevant content** - Promote the information and answers your users need to complete tasks, for example policies, benefits, resources, tools, and more. You can also target specific groups, like new hires or remote workers.

**Administer across all apps** - Microsoft Search is on by default and any administration you do applies to Microsoft Search in all the apps.

**Easy to explore results** - Users can explore results without leaving search. They can for example browse through a presentation directly in the search results page and quickly assess if it's the right result.

**Mobile friendly** - The Microsoft Search results page is mobile friendly.

**User friendly interface** - Microsoft Search offers a great user interface without a search administrator configuring anything. [Learn more](https://support.office.com/article/d5ed5d11-9e5d-4f1d-b8b4-3d371fe0cb87)

**Microsoft Search evolves** - The set of content types users can search for and the intelligence of the search box will grow over time. [Learn what's coming next in Microsoft Search](https://aka.ms/MicrosoftSearch)

## When to use which search experience?

Which experience your users see depends on whether your organization mostly uses classic or modern sites. If you believe that Microsoft Search gives your users the best experience, [learn how to get started with Microsoft Search in SharePoint](/en-us/microsoftsearch/get-started-search-in-sharepoint-online).

### Should you use the Search Center or the SharePoint start page as your portal?

If you need custom refiners or search verticals for organization-specific content, or you need to display results for organization-specific content differently than other content. Use the Search Center (classic search) as your portal. If not, we recommend promoting the SharePoint start page (Microsoft Search) to your users.

### Is the search experience impacted if you migrate from classic to modern sites?

Yes, if you have customized search. A classic site has a classic search box. For example, you've set up the search box to redirect to a custom Search Center in order show results that are filtered and formatted for organization-specific content types. The modern site has the Microsoft Search box. You can't customize the Microsoft Search experience like that. If you don't need to customize search, we recommend using modern sites.

### Can users search across all sites of an administrative unit?

It's possible, but it takes some effort to do this with classic search. It's better to use a hub site to organize the sites. Hub sites use Microsoft Search, which is scoped to search for news, people, files, and sites across all sites that are associated with the hub. [Learn more about hub sites](https://support.office.com/article/fe26ae84-14b7-45b6-a6d1-948b3966427f?)

### Can you use Microsoft Search in combination with cloud hybrid search?

Yes. With [cloud hybrid search](hybrid/learn-about-cloud-hybrid-search-for-sharepoint), both on-premises and online content go into the same index, which both the classic and Microsoft Search experiences use.