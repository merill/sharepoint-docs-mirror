---
layout: Conceptual
title: Specify search settings for a site collection or a site - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/override-default-search-center
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
ms.date: 2018-06-21T00:00:00.0000000Z
audience: Admin
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
ms.assetid: 99da1d77-f42b-4f56-b48a-24e87f336e91
description: Learn how to specify how search should behave for a site collection or a site. The shared Search Box at the top of most pages will use these settings.
locale: en-us
document_id: 50867596-18e6-b132-b8fb-5f51563d5944
document_version_independent_id: 1150103d-949d-5bd2-7c90-9281f1158e8e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/override-default-search-center.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: override-default-search-center
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/override-default-search-center.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
platformId: 27b90c85-b814-4ce2-e081-c17fdab758e0
---

# Specify search settings for a site collection or a site - SharePoint in Microsoft 365 | Microsoft Learn

As a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) and [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365, you can specify how search should behave for a classic site collection or a site. The shared Search Box at the top of most classic pages uses these search settings. Any settings you specify on site collection level applies to all sites within that site collection, unless you specify other settings for the site.

You can specify where searches should go for your classic site collection or site by specifying the URL of your Search Center. For example, if you have created an Enterprise Search Center on your site where users can search everything in your company, you can enter the URL of that site here. If you do not enter a Search Center URL, searches will go to the default Search Center, available at &lt;host\_name&gt;/search/.

When you create an Enterprise Search Center site collection SharePoint creates a default search home page and a default search results page. In addition, several pages known as search verticals are also created. Search verticals are customized for searching specific content, such as People, Conversations, and Videos, and they display search results that are filtered and formatted for a specific content type or class.

For more on creating and customizing a search center for your site, see [Manage the Search Center in SharePoint](manage-search-center).

You can change which search results page queries are sent to. By default, queries are sent to the same search results page as the parent, but you can override this for a site collection or a site.

You can also configure search navigation for a site. With search navigation, users can move quickly between different search vertical pages. Navigation links are shown in the Search Navigation Web Part on search result pages, and can also be shown as a drop-down menu in the search box.

Note

It may take up to 30 minutes before changes take effect.

## Specify search settings for a site collection

1. On the site, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and then select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**.
2. Under **Site Collection Administration**, click **Search Settings**.
3. To specify a Search Center, in the **Search Center URL** box, type the URL of the Search Center site.
4. To change which search result page queries are sent to, in the section **Which search results page should queries be sent to?**, clear **Use the same results page settings as my parent**, and then select one of the following:

    - **Send queries to a custom results page URL**. Enter the URL. Custom URLs can be relative or absolute, and can also include special tokens, such as {SearchCenterURL}.

        Example: /SearchCenter/Pages/results.aspx or http://server/sites/SearchCenter/Pages/results.aspx.
    - **Turn on the drop-down menu inside the search box, and use the first Search Navigation node as the destination results page**. If you choose this option, users can choose search vertical in the search box when they enter a query.
5. Click **OK**.

## Specify search settings for a site

By default, a site has the same search settings as the site collection that the site belongs to. You can, however, override these settings by defining specific search settings for the site.

1. On the site, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and then select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**.
2. Under **Search**, click **Search Settings**.
3. To specify a Search Center, in the **Search Center URL** box, type the URL of the Search Center site.
4. To change which search result page queries are sent to, in the section **Which search results page should queries be sent to?**, clear **Use the same results page settings as my parent**, and then select one of the following:

    - **Send queries to a custom results page URL**. Enter the URL. Custom URLs can be relative or absolute, and can also include special tokens, such as {SearchCenterURL}.

        Example: /SearchCenter/Pages/results.aspx or http://server/sites/SearchCenter/Pages/results.aspx.
    - **Turn on the drop-down menu inside the search box, and use the first Search Navigation node as the destination results page**. Make sure that the search vertical you want as a default is the first option in the **Configure Search Navigation** section.
5. To configure search navigation, edit settings in the **Configure Search Navigation** section as required. You can, for example:

    - Change the display name or the URL of a search vertical
    - Change the order of the search vertical links
    - Add a search vertical

        See [Change settings for the Search Navigation Web Part](search-navigation-web-part) for steps.
6. Click **OK**.