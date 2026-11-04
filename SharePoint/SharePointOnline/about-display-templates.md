---
layout: Conceptual
title: About display templates in the Content Search Web Part and other search-driven Web Parts - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/about-display-templates
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
ms.date: 2026-06-24T00:00:00.0000000Z
audience: End User
f1.keywords:
- NOCSH
ms.topic: article
customer-intent: As a user, I want to learn about display templates in search-driven Web Parts.
ms.service: sharepoint-online
ms.subservice: sites-pages
ms.collection: M365-collaboration
ms.localizationpriority: medium
search.appverid:
- SPO160
- SPS150
- MET150
ms.assetid: c7cb0a7e-fb1e-45b1-b259-c0dae30f7528
description: The Content Search Web Part and the other search-driven Web Parts use display templates to control how the search results appear in the Web Part. By using display templates, you can control the ways in which search results appear and behave in search-driven Web Parts.
locale: en-us
document_id: d31b798b-3cb1-72dd-bf94-b01da4536763
document_version_independent_id: 1aaf32ab-e41c-669d-0e2e-a7297f10568e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/about-display-templates.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: about-display-templates
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/about-display-templates.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
platformId: 0b7fa2cd-bf37-4488-e142-a89f052c657f
---

# About display templates in the Content Search Web Part and other search-driven Web Parts - SharePoint in Microsoft 365 | Microsoft Learn

The Content Search Web Part and the other search-driven Web Parts use display templates to control how the search results appear in the Web Part. By using display templates, you can control the ways in which search results appear and behave in search-driven Web Parts.

Display templates are HTML files that specify which managed properties from the search result to display, and also how these properties should be displayed. For example, a display template could specify that the managed property PublishingImage displays a 100x100 pixel picture, and the managed property Title appears in bold to the left of the image. You can use any of the pre-configured display templates, or create your own.

The different search-driven Web Parts have different default display template settings that are optimized for the intended use of that Web Part. For example, by default, the Content Search Web Part displays a list of items where each item has a picture on the left side and three lines of text on the right.

## To change display template settings

1. In the **Control** list, select a display template to control the organization and layout of your search results and the overall look of the Web Part.
2. In the **Item** list, select a display template for the individual items that are displayed in the search results within the Web Part.
3. Select the **Don't show anything when there are no results** check box if you don't want to display the Web Part at all if there are no search results returned by the query in that Web Part.

    If you clear the check box, the Web Part is displayed even if there are no search results, and the Web Part will show the "No results" message in the selected Control display template.

## To change which managed properties are displayed in the fields in the Item Display Template

By default, display templates have a set of property mappings in them that were defined when the display template was created. However, you can override these settings in a particular Content Search Web Part.

1. Under **Property Mappings**, select the check box **Change the mapping of managed properties for the fields in the Item Display Template**.
2. In the different lists below the check box, enter the managed property to use for that field in the Item Display Template.

    If you enter multiple managed property names in a list, separate the managed properties by using semicolon. When displaying content, SharePoint will use the first property that isn't empty.

For more information, see:

- [About search criteria for the Content Search Web Part and other search-driven Web Parts](https://support.office.com/article/9937e459-2b94-4a04-8c06-90696a7d94a8)