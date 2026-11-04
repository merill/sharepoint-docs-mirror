---
layout: Conceptual
title: Change settings for the Search Box Web Part - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/search-box-web-part
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
ms.assetid: 1915c232-3a41-440a-b5be-b1cdf364b607
description: Learn how to customize the Search Box Web Part.
locale: en-us
document_id: 59d40f45-9586-afac-1d76-d86901fe8c20
document_version_independent_id: e6ee601b-56af-a579-d91b-dc01ccfa1317
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/search-box-web-part.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: search-box-web-part
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/search-box-web-part.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
platformId: 1fe98704-c7a8-605f-d3ab-9d577bdcfd15
---

# Change settings for the Search Box Web Part - SharePoint in Microsoft 365 | Microsoft Learn

The Search Box Web Part shows a text box where users can enter words or phrases to search for information. By default, the Search Box Web Part is used on the home page for the Search Center (default.aspx), and all default search results pages (**Everything**, **People**, **Conversations**, and **Videos**).

As a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365, you can change settings in the Search Box Web Part. You can:

- Change where the search results should be displayed — for example, show results in a custom Search Results Web Part or a custom search results page.
- Turn off query suggestions.
- Show links to a search preference page and an advanced search page.
- Change the display template that is used for the Web Part.

## Change where search results are displayed

1. On the Search Center site home page, click the **Settings** menu, and then click **Edit Page**.
2. In the Web Part, click the **Search Box Web Part Menu** arrow, and then click **Edit Web Part**.
3. In the **Search Box** tool pane, under **Properties for Search Box**, expand **Which search results page should queries be sent to**.

- To use the settings that are defined on the **Search Settings** page, select the **Use this site's Search Settings** check box.
- To override the settings that are defined on the **Search Settings** page, clear the **Use this site's Search Settings** check box.
- To show search results in a Web Part on the page, in the section **Send queries to other Web Parts on this page**, select a Web Part.

    Note

    If there are no other Web Parts on a page, search results will be sent to the search results page that is specified on the **Search Settings** page.
- To send queries to a different search results page, select **Send queries to a custom results page URL**, and then type the URL of the custom search results page.

    Note

    You can't send queries to a custom search results page that uses a friendly URL.

1. Click **OK**.

## Change settings for query suggestions

As a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365, you can turn off or on query suggestions or edit the different settings for query suggestions. Query suggestions are turned on by default.

1. On the Search Center site home page, click the **Settings** menu, and then click **Edit Page**.
2. In the Web Part, click the **Search Box Web Part Menu** arrow, and then click **Edit Web Part**.
3. In the **Search Box** tool pane, under **Properties for Search Box**, expand the **Query Suggestions** section.

- To turn off query suggestions, clear the **Show suggestions** check box.
- To change how many query suggestions to show, type the maximum number in the **Number of query suggestions** box.
- To change how many characters the user must type before query suggestions are shown, edit the number in the **Minimum number of characters** box.
- To change how many milliseconds elapse before query suggestions are shown, edit the number in the **Suggestions delay (in milliseconds)** box.

1. Click **OK**.

## Show links or change the display template

1. On the Search Center site home page, click the **Settings** menu, and then click **Edit Page**.
2. In the Web Part, click the **Search Box Web Part Menu** arrow, and then click **Edit Web Part**.
3. In the **Search Box** tool pane, under **Properties for Search Box**, expand the **Settings** section:

- To show a link to a search preference page, select **Show preferences link**.
- To show a link to an advanced search page, select **Show advanced link**, and then in the **Advanced search page URL** box, type the URL of the advanced search page that you want to link to.
- To apply another display template, in the **Search box control Display Template** list, select the display template that you want to apply to the Web Part.
- Select the **Make the search box have focus when the page is loaded** check box so that users can immediately type a query in the search box when the page is loaded without first having to click the search box. This option is selected by default.

1. Click **OK**.