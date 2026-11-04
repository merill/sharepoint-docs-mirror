---
layout: Conceptual
title: Use the Dashboard web part on a SharePoint home site - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/homesites/use-dashboard-web-part-on-home-site
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-07-21T00:00:00.0000000Z
ms.reviewer: 
ms.author: dipadur
author: divyachapan
manager: elizapo
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: sites-pages
ms.localizationpriority: high
ms.collection:
- Strat_SP_modern
- M365-collaboration
search.appverid:
- SPO160
- MET150
description: Learn how to use the Dashboard web part on a SharePoint home site
locale: en-us
document_id: 7f68bfaf-fc1a-e84b-c6b6-7daa3f7abe76
document_version_independent_id: 2fdaaa2f-a9f4-806e-0e7f-c458b0e9d168
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/homesites/use-dashboard-web-part-on-home-site.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: homesites/use-dashboard-web-part-on-home-site
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/homesites/use-dashboard-web-part-on-home-site.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 865e989e-fa44-a96f-e67e-9b8b332bd8b0
---

# Use the Dashboard web part on a SharePoint home site - SharePoint in Microsoft 365 | Microsoft Learn

A SharePoint home site provides a customized landing experience that reflects the organization's brand, voice, and priorities. A SharePoint home site also serves as the gateway to other portals in your organization's intranet. It is the foundation to the SharePoint app in Teams (formerly Viva Connections. When [deploying the SharePoint app in Teams](sharepoint-app-in-teams-setup-overview), you'll [set up a Dashboard](create-dashboard) and [use cards](available-dashboard-cards) to bring together resources for different audiences to provide a comprehensive view of everything they need to complete common tasks. For example, the Dashboard could include a card that allows users to access cafeteria menus, schedules, reports, shift schedules, HR policies, and more.

Once a Dashboard is published, you can use the Dashboard web part to display it on your SharePoint home site. If you want to add, remove, or reorder cards, the existing Dashboard on your site must be edited. To learn how to create or edit a Dashboard, see [Create a SharePoint app in Teams dashboard and add cards](create-dashboard).

## Add the Dashboard web part

To add a Dashboard web part, firstly ensure that you are in the **edit** mode. Select **Edit** at the top-right of the SharePoint home site page.

Once in **edit** mode, perform the following steps:

1. Hover your mouse around the section within which you want to place the web part, and select the **circled +**.
2. In the web part search box, enter **Dashboard** to quickly find and select the **Dashboard** web part.

    ![Screenshot that shows the screen on which you can search for a web part and select it once displayed.](../sharepointonline/media/homesites/dashboard-picker.png)

    The web part is added to your page and is populated with the cards from the existing Dashboard on your site. In this example, the Dashboard is placed in a vertical section on the right:

    ![Screenshot showing the screen that displays the web card.](../sharepointonline/media/homesites/display-of-web-card.png)
3. Optionally, you can change the title of the Dashboard by selecting it in the web part and typing over it with your own title.

    ![The screen that displays the option that allows you to edit the title of a Dashboard.](../sharepointonline/media/homesites/editing-title-of-dashboard.png)
4. To move the web part, select the **Move web part** icon and drag the web part to a different section or column on the page.
5. To set the value for maximum number of cards to display on the web part, select the **Edit web part** pencil icon.
6. Use the slider to indicate the maximum number of cards to display.

    ![The screen displaying the option by which you can define the count of the cards to be displayed.](../sharepointonline/media/homesites/defining-threshold-cards-to-display.png)

    Note

    When there are more cards available than the maximum number set for the web part, users can select **See all** to see the rest of them.
7. Once the card-count threshold is set, select **Publish** or **Republish** to make the page available with your newly placed Dashboard web part.

## Additional information

- **The Dashboard web part is hidden when there are no cards to show**: There might be no cards to show when the Dashboard author has targeted cards for specific audiences, and people outside of those audiences are viewing the page. For example, if all cards are targeted to your development group, only people in the development group will see the Dashboard.
- **We recommend you use the Dashboard web part in a vertical section**: Although a vertical section is recommended, the web part can be used in any section in one, two, or three column layouts. Here’s an example of a Dashboard web part in a horizontal section:

    ![The screen displaying the web part in a horizontal layout.](../sharepointonline/media/homesites/dashboard-web-part-horizontal-section.png)
- **The Dashboard web part can be added to any page on your SharePoint home site**: The Dashboard is most useful on your SharePoint home page, but it's possible to add it to any page on your SharePoint home site. One practical use for adding the Dashboard to your home site is to experiment with your page layout to see where you think the Dashboard fits best. Just create a copy of your SharePoint home page and start experimenting.
- **The Dashboard web part can be used in sections with a colored background**: When editing a section, you can change the background of the section and the cards of the Dashboard will have a different color from that background.

    ![The screen indicating the color of the card.](../sharepointonline/media/homesites/card-color.png)
- **“See all” appears on the top-right of the Dashboard web part** when there are more Dashboard cards available than can be displayed in the Dashboard web part. When **See all** is selected, a page that shows the entire Dashboard is displayed.

    ![The screen displaying a full view of the Dashboard.](../sharepointonline/media/homesites/full-display-dashboard.png)