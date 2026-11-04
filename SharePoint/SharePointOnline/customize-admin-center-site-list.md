---
layout: Conceptual
title: Customize the SharePoint admin center site list - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/customize-admin-center-site-list
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2018-07-11T00:00:00.0000000Z
ms.reviewer: trgreen
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords:
- CSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.collection:
- Strat_SP_admin
- M365-collaboration
- m365initiative-spsitemanagement
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
search.appverid:
- SPO160
- MET150
- BSA160
description: In this article, you'll learn about how to customize views on the SharePoint admin center active sites page.
locale: en-us
document_id: 0a04d249-1b38-368c-6d96-e1158fe6dfe1
document_version_independent_id: 6b56a141-5923-b9c9-cf41-18ca9f6336c9
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/customize-admin-center-site-list.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: customize-admin-center-site-list
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/customize-admin-center-site-list.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: c15a320e-25d7-17ac-5dcb-2d3b82c9f65b
---

# Customize the SharePoint admin center site list - SharePoint in Microsoft 365 | Microsoft Learn

The [**Active sites** page in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185220) lets you view the SharePoint sites in your organization. You sort and filter sites, search for sites, and customize the columns and views.

## Sort and filter the site list

Sorting and filtering the site list is just like sorting and filtering other lists in SharePoint.

1. Select the arrow next to the column header.
2. Select how you want to arrange the items. The options vary depending on the column. For example, you might have options to sort alphabetically, in numeric order, or chronologically.

    If the column allows filtering, a "Filter by" option appears. Select the value or values that you want to show. Your selections appear with a check mark beside them. To remove a selection, select that value again. To clear all filters on the column, select **Clear filters**.

    ![Filter options for the Primary admin column](sharepointonline/media/0d188752-2bce-4d69-9cf4-a16ab87a2892.png)

## Customize columns

1. Select the arrow next to any column header, and then select **Customize columns**.
2. To show and hide columns, select and clear check boxes.
3. To rearrange the columns, point to a column, and select the up or down arrow to move the column up or down.

    ![The Customize columns panel](sharepointonline/media/customize-columns.png)

    Note

    Data in the following columns is not available for US Government GCC High and DoD customers:

    - Last activity
    - File views or edited
    - Page views
    - Page visits
    - Files
    - Storage used

## Switch views and create custom views

The [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219) comes with a few standard views: **All sites**, **Sites connected to Teams**, **Microsoft 365 Group sites**, **Sites without a group**, **Classic sites**, **Largest sites**, **Least active sites**, and **Most popular shared sites**.

To select a different view:

- On the far right of the command bar, select the **Change view** arrow next to the name of your current view, and then select a different view.

    ![The list of views](sharepointonline/media/view-menu.png)

To create and save a custom view:

1. Customize columns, sort, and filter your view the way you want. (Views that are filtered through search can't be saved.)
2. On the far right of the command bar, select the **Change view** arrow next to the name of your current view.
3. Select **Save view as**.
4. In the **Save as** dialog box, enter a name for the view.

    Note

    To set the view as default, in the list of views, select **Set current view as default**.

## Track a view

When you select a built-in or custom view, you can add a card to your home page that shows the number of sites in the view and summarizes info about the set of sites.

1. Select the **Change view** arrow, and then select the view you want to track.
2. Select **Track view** on the command bar.
3. Select **Add card**.
4. Go to your home page to see the card for the tracked view.

    ![A tracked view card](sharepointonline/media/tracked-view.png)

Note

If you remove a tracked view card from your home page, you can't add it back from the Add cards panel. You need to open the view on the Active sites page and select **Track view**.

## Search for a site

You can search for a site by name, URL, primary admin, or template. To do this, enter keywords in the Search box, and press Enter.

Note

Search doesn't look in hub site display names for the keywords you enter. All characters you enter are treated as part of the query. Search doesn't recognize operators or wildcards (\*).

## Export to CSV

To export the site list you're viewing as a .csv file that you can work with in Excel, go to **Active sites** page and select **Export** on the command bar.

Note

The .csv file lists the hub as a GUID and the template as an ID (for example, STS#0).