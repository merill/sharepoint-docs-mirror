---
layout: Conceptual
title: Manage the Viva Connections spotlight - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/homesites/manage-spotlight
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-04-16T00:00:00.0000000Z
ms.reviewer: evanatkin
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
- Strat SP modern
- M365-collaboration
- m365initiative-viva-connections
search.appverid:
- SPO160
- MET150
description: Learn how to manage the spotlight found above the Viva Connections dashboard by pinning links to content items and selecting SharePoint sites to pull news from.
locale: en-us
document_id: f1a3b18b-2499-e0df-6bdc-e698b6ae00e2
document_version_independent_id: 0efa4952-1535-8511-eed8-591631b40112
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/homesites/manage-spotlight.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: homesites/manage-spotlight
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/homesites/manage-spotlight.md
platformId: eda70fad-42ac-571b-d9bd-3ebe63aa0b6f
---

# Manage the Viva Connections spotlight - SharePoint in Microsoft 365 | Microsoft Learn

The Viva Connections spotlight dynamically displays content from the home site, news from SharePoint sites, or links to articles or sites above the dashboard in your Connections experience. Experience owners and admins can dynamically populate extra content in the spotlight by selecting SharePoint sites to automatically pull news posts from or by pinning links to content sources, to display up to 11 items at a time.

Using the spotlight settings allows you to curate news without needing to have SharePoint news on a home site as a prerequisite (which Experience owners can still do if they choose).

## Selecting news sources for the Spotlight

SharePoint news sources will display in the spotlight section after any pinned links, and news posts from these sources will automatically populate if there's remaining space. To select a source:

1. Select **Edit** above the spotlight, then **Settings**.
2. Under SharePoint News, select a news source:

    - **This site**: Only displays news posted to this SharePoint home site.
    - **Select sites**: Display all available SharePoint sites within the organization that an owner or admin has access to.
    - **Search all sites**: Search for a site by name or URL.

    Note

    If you created your Connections experience without a home site, the **this site** option will still show but won't allow you to save since no home site is detected.
3. If selecting a source other than your current site, extra sources display from available SharePoint sources:

    - **Sites selected**: lists any currently selected SharePoint sites.
    - **Frequent sites**: lists SharePoint sites you've frequently visited.
    - **Recent sites**: lists SharePoint sites you've recently visited.
4. Select the **sites** you want to pull news from.
5. Select **Save** to save your changes.

    ![Screenshot of the spotlight settings property pane listing available SharePoint news sites.](../sharepointonline/media/homesites/edit-viva-home/spotlight-sharepoint-news.png)
6. News from selected SharePoint sites will display after any pinned links and if there's space available.

## Pinning a link to a content source

You can add a link to any source of content (blog, post, site, etc.) to display it in the spotlight. Up to 11 links can be pinned at a time. Pinned links display first in the spotlight before any news from SharePoint sites (if space is available).

1. Select **Edit** above the spotlight, then **Settings**.
2. In the Spotlight settings, select **Pin item**.

    ![Screenshot of the spotlight settings property pane.](../sharepointonline/media/homesites/edit-viva-home/spotlight-spotlight-settings.png)
3. The **Pin an item** panel appears. In the **Link** field, enter the URL of the SharePoint news post or external source.
4. Additional information populates based on the information from the news source.

    - **Title**: Edit the title or keep the populated entry from the news source.
    - **Preview Image**: Select **Change image** to select your own, or keep the image used from the news source.
    - **Alternative Text**: Enter descriptive text for the image to be used by screen readers.
5. Select **Add** to add your pinned item and return to the spotlight settings.

    ![Screenshot of the pin an item settings property pane.](../sharepointonline/media/homesites/edit-viva-home/spotlight-pin-item.png)
6. Select **Save** to save your changes and close the spotlight settings pane.

### Editing a pinned item

You can make changes to existing pinned links or rearrange the order that the pinned links appear in the spotlight.

1. Select **Edit** above the spotlight, then **Settings**.
2. Under **Pinned items**, select the **edit icon** for the pinned item you want to edit.

    ![Screenshot of the pinned items property pane with the edit icon highlighted.](../sharepointonline/media/homesites/edit-viva-home/spotlight-edit-item.png)
3. Make any necessary changes to the link, title, image, or alternative text as needed. When finished, select **Update** to apply your changes.
4. To reorder a pinned item, hover your mouse over the **six vertical dots** to the left of the item. Select and drag the item to its new location within your list of news items.

    ![Screenshot of the pinned items property pane with the move icon highlighted.](../sharepointonline/media/homesites/edit-viva-home/spotlight-move-item.png)
5. You can also reorder items by selecting the **three vertical dots** to the right of the item. Use the number field to indicate the new location for the item, then select **Update**.

    ![Screenshot of the pinned items property pane with the reorder icon highlighted and number field displayed.](../sharepointonline/media/homesites/edit-viva-home/spotlight-reorder-item.png)
6. When finished making your changes, select **Save**.