---
layout: Conceptual
title: Manage the Search Center in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/manage-search-center
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
ms.date: 2018-04-05T00:00:00.0000000Z
audience: Admin
f1.keywords:
- NOCSH
ms.topic: article
ms.service: sharepoint-online
ms.subservice: admin
ms.collection: M365-collaboration
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.assetid: 174d36e0-2f85-461a-ad9a-8b3f434a4213
description: Learn how to customize the Search Center pages to improve the end user's search experience. Learn about search verticals (Everything, People, Videos, and Conversations) and the predefined Web Parts (Search Box Web Part, Search Results Web Part, Search Navigation Web Part, and Refinement Web Part.)
locale: en-us
document_id: 2f43afcd-dcbb-77d1-99bf-ce85c28923f0
document_version_independent_id: 7789fd4a-bafc-b12f-f81d-3b99496785d0
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/manage-search-center.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-search-center
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/manage-search-center.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
platformId: 4ee716fe-1020-db71-bdf4-87032bed0fa0
---

# Manage the Search Center in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn

The Search Center is a classic search experience. The Search Center is a site or site collection that has a starting page where users enter search queries and a search results page where users can drill into and refine search results, or run a new query.

SharePoint offers two types of Search Centers: the **Basic** Search Center and the **Enterprise** Search Center. By default, SharePoint is set up with the Basic Search Center.

Both Search Centers search the same content and show the same search results. The main difference is that the Enterprise Search Center comes with the search verticals People, Conversations, and Videos. Search verticals are pages that are tailored for displaying search results that are filtered and formatted for a specific content type or class. Search verticals help users move quickly between such different types and classes of content. Also, as a search administrator you have more options for tailoring the look and feel of the Enterprise Search Center.

If your organization needs an enterprise-wide search experience, [evaluate first whether the modern search experience covers your needs](get-started-with-modern-search-experience). Modern search also comes with verticals, it doesn't require any set up, and the results are personal. [Learn about the modern search experience for users](https://support.office.com/article/b81ab573-ec9c-4aa9-a369-b3c630f878a7?).

If modern search doesn't cover you needs, you can [switch from the Basic Search Center to an Enterprise Search Center](switch-from-enterprise-search-center-to-basic).

## Search Center pages

These pages are located in the **Pages** library, and they contain predefined Web Parts that you can customize to improve the end user's search experience.

| Page | Description |
| --- | --- |
| default.aspx | The home page for Search Centers, and the page where users enter their queries. |
| results.aspx | The default search results page for the Search Centers.  If you have an Enterprise Search Center, this is also the search results page for the **Everything** search vertical. |
| peopleresults.aspx | If you have an Enterprise Search Center, this is the search results page for the **People** search vertical. |
| conversationresults.aspx | If you have an Enterprise Search Center, this is the search results page for the **Conversations** search vertical. |
| videoresults.aspx | If you have an Enterprise Search Center, this is the search results page for the **Videos** search vertical. |
| advanced.aspx | This is the search page where users can apply some restrictions to their search phrases — for example, they can limit the search to an exact phrase. |

As a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) and [above](/en-us/microsoft-365/admin/add-users/about-admin-roles), you can also create your own search pages and add them to the Enterprise Search Center as search verticals, see [Add a search vertical to the Search Navigation Web Part](search-navigation-web-part#add-a-search-vertical-to-the-search-navigation-web-part).

## About the Web Parts used on Search Center pages

The Search Center pages contain the following predefined Web Parts: Search Box Web Part, Search Results Web Part, Search Navigation Web Part, and Refinement Web Part.

If you have an Enterprise Search Center, the Web Parts on the search result pages are by default set up the same way. The only difference is that the query in the **Search Results** Web Part is directed to different result sources for each search vertical page. For example, for the **People** search vertical page, the query in the **Search Results** Web Part is limited to the **Local People Results** result source. For the **Videos** search vertical page, the query in the **Search Results** Web Part is limited to the **Local Video Results**.

For information about how to customize the Search Center Web Parts, see the following articles:

- [Change settings for the Search Box Web Part](search-box-web-part)
- [Change settings for the Search Results Web Part](https://support.office.com/article/40ff85b3-bc5e-4230-b1dd-f088188e487e)
- [Change settings for the Search Navigation Web Part](search-navigation-web-part)
- [Change settings for the Refinement Web Part](refinement-web-part)