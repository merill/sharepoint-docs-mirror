---
layout: Conceptual
title: Change how search results look by using result types and display templates - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/use-result-types-and-display-templates
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
ms.collection: M365-collaboration
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.assetid: 0fc83eeb-28c8-4f65-afe3-0ee515296a9d
description: Learn how result types and display templates help users quickly distinguish between different types of search results in SharePoint.
locale: en-us
document_id: 55be1fa6-d7e0-7ce7-bb0e-b68e6d7597db
document_version_independent_id: 6740381f-cfd1-3c64-59c4-2eb60b12dd3b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/use-result-types-and-display-templates.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: use-result-types-and-display-templates
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/use-result-types-and-display-templates.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
platformId: 8cd9b397-b166-15b9-69e3-c3f17ff6c6e9
---

# Change how search results look by using result types and display templates - SharePoint in Microsoft 365 | Microsoft Learn

To help users quickly distinguish between different types of results when they search for something in the classic search experience, we use *result types* and *display templates*. Important information is shown directly in the search results, so that users don't have to click on each result to see if they've found what they're looking for.

By default, the Search Results Web Part in your Search Center is set up to use different display templates according to the result type of the search result. [Result types](manage-result-types) define when to use which display template, and the *display template* defines what information to show in the search results.

For example, there's a display template for PowerPoint files and another display template for Word documents. A result type says that if the search term is found in a PowerPoint file, then use the PowerPoint display template when showing that result. The users can see right away that this result is a PowerPoint file, and they can also see other information that helps them see whether this result is what they're looking for. When users hover over the result, they'll see a preview of the PowerPoint in the hover panel, together with more details about it. The hover panel also lets users perform *actions,* such as **Edit** or **Send**. The same way, the result type for Word documents uses a Word display template to show information.

Results look different based on result type and display template. This picture shows item display templates for Word, PowerPoint and Excel on the left side, and a hover panel display template for PowerPoint on the right side.

![Shows different display templates depending on result type](sharepointonline/media/29d9c7d2-82d3-483d-9aa9-e298c6b6b0b0.png)

## Types of display templates used in the Search Results Web Part

The default [Search Center](manage-search-center) on your site consists of different Web Parts: a Search Box Web Part, a Search Results Web Part, a Search Navigation Web Part, and a Refinement Web Part. The actual search results are shown in the **Search Results Web Part**, All these Web Parts can also be added to any of your site's pages.

For the Search Results Web Part, there are three main types of display templates you should know about, Control display templates, Item result templates, and Hover panel templates.

The *Control display template* decides the overall structure of how the results are presented. It contains the things "around" the individual results, such as a heading, numbering, next and previous page buttons, and a "no results found" message.

An *Item display template* defines how each result is displayed. It defines the managed properties you want to show and how they're displayed. You can have different item display templates for different result types.

![Display template types for search results](sharepointonline/media/b780c116-22b4-4138-9da9-a9026f32f8c5.png)

The *Hover panel display template* typically shows a preview of the item or document when the users hover over the search result. The hover panel display template also contains actions such as **Edit** or **Send**, and other information about the search result.

## How display templates show information about search results

The search results contain information that'll help users identify whether the result is what they're looking for. The display templates show this information by surfacing *managed properties* . Managed properties are content and metadata stored in the search index, for example the author and the title of a document. The display templates show a selection of the managed properties in the search results, such as file type, title, document summary, path, and image.

![The item display template surfaces information from managed properties](sharepointonline/media/d9835a2c-db5c-4725-b3e3-9476ac505f4e.png)

You can create your own display templates that show information that's important to your users, for specific types of results.

- For more information about managed properties, see [Manage the search schema in SharePoint](manage-search-schema).
- For information about the Search Center and how to set it up, see [Manage the Search Center in SharePoint](manage-search-center).
- For a full list of available display templates, see **Display templates for the Search Results Web Part** in [Display template reference in SharePoint Server 2013](technical-reference/display-template-reference-in-sharepoint-server).