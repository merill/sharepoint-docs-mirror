---
layout: Conceptual
title: Configure the SharePoint App for Teams - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/homesites/sharepoint-app-in-teams-app-config
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
description: Instructions on how to set the landing experiences for the SharePoint Teams apps on mobile and desktop
author: divyachapan
ms.author: dipadur
manager: elizapo
ms.service: sharepoint-online
ms.subservice: sites-pages
ms.topic: how-to
ms.date: 2026-09-21T00:00:00.0000000Z
ai-usage: ai-assisted
locale: en-us
document_id: 23fad17d-b530-3586-b0cb-21e51dc63be2
document_version_independent_id: a4214936-dca4-d64e-5876-6cc970db23e8
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/homesites/sharepoint-app-in-teams-app-config.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: homesites/sharepoint-app-in-teams-app-config
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/homesites/sharepoint-app-in-teams-app-config.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/1ae5c491-970a-4062-8301-6336e69f9026
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/f2c3e52e-3667-4e8a-bf11-20b9eaccdc8c
platformId: 13e19853-cedb-ba34-7856-d3701f40672a
---

# Configure the SharePoint App for Teams - SharePoint in Microsoft 365 | Microsoft Learn

The SharePoint app in Teams configuration flow gives home site owners control over how the app appears for everyone in their organization — both on mobile and desktop. Home site owners can choose which tabs are shown, the order they appear in, and whether the desktop experience opens with the home site or the preset layout.

Note

- You must be a **home site owner** to access the configuration flow.
- Configuration changes apply to **all users** associated with your home site.
- The configuration flow is accessed through the home site settings.

## What is the configuration flow?

The configuration flow is a settings experience built into your SharePoint home site. It lets home site owners make two key decisions:

**Use the configuration flow to:**

- Control which tabs appear in the SharePoint app in Teams on **mobile** and in what order.
- Choose whether the SharePoint app in Teams on **desktop** opens with your home site as the landing page or defaults to the preset railed experience.

Once a home site owner saves a configuration, it takes effect for all users associated with that home site. No per-user configuration is required.

## Access the configuration flow

To open the configuration flow, navigate to your organization's home site and follow these steps:

1. Select the **Settings cog** on the home site.
2. Select **Manage home site**.
3. Select **SharePoint app for Teams**.

    This opens the configuration panel where you can set preferences for both the mobile and desktop experiences.

![Screenshot that describes how to access SharePoint app in Teams through Manage home site option.](../sharepointonline/homesites/media/sharepoint-teams-app-config/image2.png)

## Configure the mobile experience

The mobile configuration controls which tabs appear in the SharePoint app in Teams on mobile devices and in what order. There are two layout options to choose from.

### Custom layout (recommended)

The custom layout gives home site owners flexibility to tailor the mobile experience for their organization.

- **Tabs included**: Home, Dashboard, and News — in any order you choose.
- **Reorder tabs**: Use drag and drop to arrange the tabs in your preferred order.
- **Optional**: Hide the News tab if it isn't relevant to your organization's experience.

![Screenshot that describes the mobile custom layout configuration.](../sharepointonline/homesites/media/sharepoint-teams-app-config/image3.png)

Note

The **Resources tab is not available** in the custom layout. Users can still access resources through:

- **Global navigation** on the home site, if resources have been set up with global navigation links. Learn how to [enable and customize global navigation](/en-us/sharepoint/sharepoint-app-bar).
- A **Resources web part** added to the home site.
- **News links cards** on the Dashboard.

### Fixed layout

The fixed layout preserves the original tab structure for organizations that prefer the classic experience.

- **Tabs included**: Dashboard, News, and Resources — in the original order.
- No reordering or tab visibility options are available in this mode.

![Screenshot that describes the mobile fixed layout configuration.](../sharepointonline/homesites/media/sharepoint-teams-app-config/image4.png)

## Configure the desktop experience

Note

The history of navigation in the SharePoint app in Teams desktop is available while you are in the app using the **Back &lt;** or **Forward &gt;** arrow to the left of the search bar. Once you leave, that history isn’t retained. You’ll return to the default experience of the app the next time you open the app either directly or using the history navigation of the app.

The desktop configuration controls how the SharePoint app in Teams appears on desktop and tablet devices. Choose between two layout options.

### Custom layout (recommended)

The custom layout sets your **SharePoint home site as the landing experience** when users open the SharePoint app in Teams on desktop. Users arrive directly on the home site, giving them immediate access to organizational news, resources, and navigation from a familiar, branded experience.

![Screenshot that describes the desktop custom layout configuration.](../sharepointonline/homesites/media/sharepoint-teams-app-config/image6.png)

### Fixed layout

The fixed layout uses the predefined structured view that includes a Spotlight, Dashboard, News, and Resources panels as the default landing experience in Teams desktop.

![Screenshot that describes the desktop fixed layout confuguration.](../sharepointonline/homesites/media/sharepoint-teams-app-config/image5.png)