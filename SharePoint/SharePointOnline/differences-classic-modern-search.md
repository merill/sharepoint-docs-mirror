---
layout: Conceptual
title: Difference between classic & modern search experiences - SharePoint - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/differences-classic-modern-search
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2018-08-17T00:00:00.0000000Z
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
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
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
description: This article provides an overview of the difference between the classic and modern search experiences in Microsoft SharePoint.
locale: en-us
document_id: e29f89b7-afd4-1b65-f3ad-c802c7dd5a47
document_version_independent_id: 0f3e61c4-6b03-dccb-6067-09ed98228f62
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/differences-classic-modern-search.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: differences-classic-modern-search
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/differences-classic-modern-search.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
platformId: 0d0af1f5-53f3-e4cf-3339-ed047cb95d6f
---

# Difference between classic & modern search experiences - SharePoint - SharePoint in Microsoft 365 | Microsoft Learn

SharePoint in Microsoft 365 has both a classic and a modern search experience. Microsoft Search in SharePoint is the modern search experience. Both search experiences use the same search index to find results.

As a search admin, you can’t enable or disable either search experience, both are enabled by default. Users get the classic search experience on publishing sites, classic team sites, and in the Search Center. Users get the Microsoft Search experience on the SharePoint start page, hub sites, communication sites, and modern team sites. [Learn about classic and modern sites](https://support.office.com/article/5725c103-505d-4a6e-9350-300d3ec7d73f)

The most visible difference is that the Microsoft Search box is placed at the top of the SharePoint, in the header bar. Another difference is that Microsoft Search is personal. The results you see are different from what other people see, even when you search for the same words. You'll see results before you start typing in the search box, based on your previous activity and trending content in Microsoft 365, and the results update as you type. [Learn more about the Microsoft Search experience for users](https://support.office.com/article/d5ed5d11-9e5d-4f1d-b8b4-3d371fe0cb87).

Search admin can customize the *classic* search experience, but not the Microsoft Search experience. As a search admin you can *tailor* Microsoft Search to your organization so it's easy for your users to find often needed content in your organization.

For example, if your organization has Microsoft Search fully deployed, custom result sources at site collection or tenant level won't affect the search result. The search admin can use Microsoft search verticals instead. To learn more, see [Manage search verticals](/en-us/microsoftsearch/manage-verticals).

You use the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219) to manage classic search and the Microsoft 365 admin center to manage Microsoft Search. Certain aspects of the classic search settings also impact the modern search experience:

- The [search schema](manage-search-schema) determines how content is collected in and retrieved from the search index. Because both search experiences use the same search index to find search results, any changes you make to the search schema, apply to both experiences. The Microsoft Search experience doesn't support changing the sort order of results or building refiners based on metadata. Therefore, the following search schema settings don’t affect the Microsoft Search experience:

    - Sortable
    - Refinable
    - Company name extraction (deprecated since November 15, 2019)
- In environments where vertical configuration is available the modern search experience only shows results from the standard result source (Local SharePoint Results). To learn more, see [Manage search verticals](/en-us/microsoftsearch/manage-verticals).
- In environments where vertical configuration is not available the modern search experience only shows results from the default result source. If you change the default [result source](manage-result-sources), both modern and classic search experiences are impacted.
- Depending on the search scenario, some Microsoft Search features might not work if the [classic global Search Center URL](specify-default-search-center) is not set to point to the URL of the default classic Search Center. Depending on your tenant, this URL is "yourcompanyname.sharepoint.com/search" or "yourcompanyname.sharepoint.com/search/pages". Furthermore, ensure that the Search Center site collection exists and that all users have read access to it.
- If you temporarily [remove a search result](remove-search-results), the result is removed in both search experiences.
- The classic search experience lets admins define **promoted results** to help users find important content, while the Microsoft Search experience uses **bookmarks** to achieve the same. For clouds which support **bookmarks**, only **bookmarks** will show at the organization level on the **All** tab. For clouds without **bookmark** support, promoted results will show on the **All** tab if they searched across the whole organization. On site or hub site scope, promoted results defined at that site will show. In addition promoted results defined at the tenant level will show **All** tab.

    Tip

    If you want the the same bookmark to appear for both the organization level and site levels, you must create both a tenant **bookmark** and a **promoted result** for the sites where you want the bookmark to appear.