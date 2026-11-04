---
layout: Conceptual
title: Change settings for the Search Navigation Web Part - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/search-navigation-web-part
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
ms.date: 2026-06-25T00:00:00.0000000Z
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: sites-pages
ms.collection: M365-collaboration
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.assetid: 7c1a7462-d3d8-4a14-92f4-981b0ade9963
description: Learn how to customize the Search Navigation Web Part. The Search Navigation Web Part on search results pages contains links that let users move quickly between search verticals.
locale: en-us
document_id: 02ceddf5-d6b4-06aa-4b05-b51ff601c0cf
document_version_independent_id: ce302e45-d0d3-dbd5-18f7-001b33ad60a3
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/search-navigation-web-part.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: search-navigation-web-part
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/search-navigation-web-part.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
platformId: eeccba47-0f5f-d1f1-7925-0d3150b003f9
---

# Change settings for the Search Navigation Web Part - SharePoint in Microsoft 365 | Microsoft Learn

The Search Navigation Web Parts shows links that let users move quickly between the different search pages, known as search verticals. Search verticals are predesigned to give users different search experiences depending on what they are looking for. For example, if users click the **People** link, they are taken to the people search vertical, which is a search page specifically set up to display people information.

By default, the Search Navigation Web Part is set up to show links to the search verticals **Everything**, **People**, **Conversations** and **Videos**. The Search Navigation Web Part uses search results from the Search Results Web Part so that when users click a search vertical link, the search results are filtered and displayed according to how the search vertical is set up.

As a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365, you can change how the Search Navigation Web Part is set up by specifying a different Web Part to get the results from, change how many links to show, and change the appearance and layout of the Web Part. You make these changes by editing the properties in the Web Part tool pane.

To make other changes, such as changing display names for the links, or change their order, go to the **Search Settings** for the corresponding site. Here, you can also add a link to a new search vertical to be shown in the Web Part.

## Change the settings for the Search Navigation Web Part

Here's how you can change the set-up of the Search Navigation Web Part. You can specify a different Web Part to get the results from, change how many links to show, and change the appearance and layout of the Web Part.

1. On the search results page, click the **Settings** menu, and then click **Edit Page**.
2. In the Search Navigation Web Part, click the **Search Navigation Web Part** menu arrow, and then click **Edit Web Part**.
3. In the Web Part tool pane, in the **Control** section:

- To receive search results from another Web Part on the page, in the **Use Current Query from** list, select a Web Part.
- To change the number of search vertical links to display before overflowing, in the **Maximum Links Before Overflow** box, type a number.

1. To change how the Web Part looks, edit the settings in the **Appearance** and **Layout** sections.
2. Click **OK**.

## Change the display name or the URL of a search vertical

1. On the site, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and then select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**.
2. On the **Site Settings** page, in the **Search** section, click **Search Settings**.
3. On the **Search Settings** page, in the **Configure Search Navigation** section, click to select the search vertical that you want to change, and then click **Edit**.
4. In the **Navigation Link** dialog:

- To change the display name of a search vertical, in the **Title** field, type a display name.
- To change the URL of the search vertical, in the **URL** field, type a URL.

    Note

    You can't use a page that uses a friendly URL for your search vertical.

1. Click **OK**.

## Change the order of the search vertical links

1. On the site, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and then select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**.
2. On the **Site Settings** page, in the **Search** section, click **Search Settings**.
3. On the **Search Settings** page, in the **Configure Search Navigation** section, click to select a search vertical.
4. Click **Move Up** or **Move Down** to change the display order.
5. Click **OK**.

## Add a search vertical to the Search Navigation Web Part

As a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [above](/en-us/microsoft-365/admin/add-users/about-admin-roles), you can create a new search vertical page and add it to the Search Navigation Web Part. When you create a new page, we recommend that you copy one of the existing search vertical pages — for example, **results.aspx**, and then modify the copy to create a new page.

Here's how you can add a link to the new search vertical page in the Web Part:

1. On the site, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and then select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**.
2. On the **Site Settings** page, in the **Search** section, click **Search Settings**.
3. On the **Search Settings** page, in the **Configure Search Navigation** section, click **Add Link**.
4. In the **Navigation Link** dialog:

- In the **Title** field, type a display name.
- In the **URL** field, type the URL of the new search vertical.
- Click **OK** to save the new search vertical.

1. To change the display order, use the **Move Up** or **Move Down** buttons.
2. Click **OK**.