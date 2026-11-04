---
layout: Conceptual
title: Manage result types - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/manage-result-types
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
ms.date: 2018-06-29T00:00:00.0000000Z
audience: End User
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.collection: M365-collaboration
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.assetid: ceccf561-e82c-495c-bf3e-b3f006ae9c8c
description: Create and use result types to customize how results are displayed for particular types of documents.
locale: en-us
document_id: 7708cff4-2d62-9a20-4ec7-a2767c15d8a0
document_version_independent_id: e66ac76a-10ac-12aa-ffc1-b15146e88ad6
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/manage-result-types.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-result-types
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/manage-result-types.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: d3e78db1-605b-6d79-c380-34854bdc04eb
---

# Manage result types - SharePoint in Microsoft 365 | Microsoft Learn

As a site collection administrator or site owner, you can create and use result types to customize how results are displayed for particular types of documents.

SharePoint has both a classic and a modern search experience. For the classic search experience, you use a result type to specify a [display template](use-result-types-and-display-templates) that the search system should use for a particular type of document or search result. As documents aren't all the same, search results shouldn't be either. By using result types and display templates, it's much easier for users to find the results they are looking for. You can't customize how results are displayed for the modern search experience. [Learn about the differences between the classic and modern search experiences in SharePoint](differences-classic-modern-search).

A result type specifies one or more conditions to compare search results against, such as the type or the result source of the search result, and an action to take if a search result meets those conditions. The action specifies the display template to use for the search result.

For example, a preconfigured result type named **Person** specifies that if a search result comes from the result source **Local People Results**, then use the **People Item** display template. The **People Item** display template shows information in the hover panel such as documents the person's authored and gives you quick access to those documents.

Another example is to have a result type that fires if the **ContentType** property **contains***Sales Report* , and then have a specific display template for sales reports. Users will identify the search result as a sales report right away.

See [Change how search results look by using result types and display templates](use-result-types-and-display-templates) for more information.

There are many preconfigured result types to choose from, and you can also create new custom result types. You can configure result types at site collection level and at site level.

## Add a new result type

1. Go to the **Manage Result Types** page for a site collection or a site:

- For a site collection, in your site collection, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and then select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**. Under **Site Collection Administration**, select **Search Result Types**.
- For a site, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and then select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**. Under **Search**, select **Result Types**.

1. On the **Manage Result Types** page, do one of the following:

- Click **New Result Type**, or
- In the list of existing result types, click the name of a result type, such as **Person**, and then click **Copy** so that you can modify the copy to create a new result type.

1. In the **General Information** section, in the **Give it a name** box, type a name for the result type.
2. In the **Conditions** section, in the first list, choose a result source that the results should match.
3. In the **Conditions** section, in the second list, choose which types of content should match. To match all content, skip the rule. To add more content types, click **Add value**.
4. To add more advanced conditions related to managed properties, expand **Show more conditions**.
5. In the first list, choose a property to match.
6. Choose how the property should relate to one or more values.
7. Enter one or more values for the property in the box. Separate by using semicolons.
8. To add more properties to match, click **Add property**.
9. In the **Actions** section, select a display template. The URL of the display template is shown under **Display template URL**.
10. Check the **Optimize for frequent use** box if the result type will be among the most frequently used result types.
11. Click **Save**.