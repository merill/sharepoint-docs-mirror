---
layout: Conceptual
title: Create a SharePoint home site for the SharePoint app in Teams - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/homesites/create-sharepoint-home-site-for-sharepoint-app-in-teams
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-07-16T00:00:00.0000000Z
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
description: Create a SharePoint home site for the SharePoint app in Teams
locale: en-us
document_id: 20ffadce-839f-e0e6-f694-14e0a562b959
document_version_independent_id: 75ae0074-38d4-a8b0-4cff-7a67e05ed594
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/homesites/create-sharepoint-home-site-for-sharepoint-app-in-teams.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: homesites/create-sharepoint-home-site-for-sharepoint-app-in-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/homesites/create-sharepoint-home-site-for-sharepoint-app-in-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 57cbe345-e894-8d00-97a0-7feecb2e0ffe
---

# Create a SharePoint home site for the SharePoint app in Teams - SharePoint in Microsoft 365 | Microsoft Learn

Use this guided walkthrough to create a SharePoint home site for your organization so you can use the SharePoint app in Teams. Before you start, learn more about [planning SharePoint home site content](sharepoint-app-in-teams-plan) and [how to launch a healthy portal](/en-us/sharepoint/portal-health).

Note

SharePoint home sites are created and managed in your SharePoint admin center. You'll need to be a SharePoint admin to create a home site.

## How to use this guide

The web parts used here pair well with SharePoint home sites, however web parts can be swapped or left out. Decide what is best for your organization and adjust the layout as needed.

The guidance here will help you design the SharePoint home site and customize web parts, but you need to provide your own content.

A SharePoint home site needs site navigation that is organized well, highlights popular resources and portals, and is relevant to the entire organization. This design guidance doesn't specifically talk about how to design site navigation. Get more guidance on [how to think about links in SharePoint home site navigation](/en-us/sharepoint/information-architecture-models-examples) and [in the global navigation](sharepoint-app-bar).

## Summary of web parts

| Image of the SharePoint home site | Web parts key |
| --- | --- |
| [![Screenshot that shows SharePoint home site.](../sharepointonline/media/homesites/create-sharepoint-home-site-for-viva-connections/home-site-overview-1.png)](../sharepointonline/media/homesites/vc-home-site-design.png#lightbox) | 1. Hero web part<br>2. World clock web part<br>3. Weather web part<br>4. Dashboard web part<br>5. Image web part<br>6. File viewer web part<br>7. Events web part<br>8. Quick Links web part<br>9. Quick Links web part<br>10. News web part<br>11. Quick Links web part<br>12. Call to action web part |

## Summary of the site structure

This SharePoint home site design uses a vertical section and a combination of one and two column sections. After [creating your communication site](https://support.microsoft.com/sharepoint/sites-in-sharepoint/create-a-communication-site-in-sharepoint), start by [laying out the sections](https://support.microsoft.com/sharepoint/pages-in-sharepoint/add-sections-and-columns-on-a-sharepoint-modern-page) before adding web parts.

[![Screenshot that shows SharePoint home site design.](../sharepointonline/media/homesites/create-sharepoint-home-site-for-viva-connections/home-site-overview-2.png)](../sharepointonline/media/homesites/create-sharepoint-home-site-for-viva-connections/home-site-overview-2.png#lightbox)

## Build the site

Start with a [modern SharePoint communication site](https://support.microsoft.com/sharepoint/sites-in-sharepoint/create-a-communication-site-in-sharepoint). Next, start adding sections following the diagram in the site sections summary. Then, add and edit web parts. The guidance for customizing web parts can be applied when you are in edit mode for each web part.

[![Screenshot that shows Build SharePoint home site top section.](../sharepointonline/media/homesites/create-sharepoint-home-site-for-viva-connections/build-site-overview-1.png)](../sharepointonline/media/homesites/create-sharepoint-home-site-for-viva-connections/build-site-overview-1.png#lightbox)

| Number | Web part | Customization guidance |
| --- | --- | --- |
| 1 | [Hero web part](https://support.microsoft.com/sharepoint/pages-in-sharepoint/use-the-hero-web-part) | Select **Tiles layout** and then **Four tiles**. |
| 2 | [Resources web part](https://support.microsoft.com/sharepoint/sites-pages/use-the-world-clock-web-part) | Add **Top resources** - Changes reflect in all the pages in the site where that web part was added. |
| 3 | [Announcements web part](announcements-web-part) | Add your announcements. The most recently posted announcements will show first. |
| 4 | [World clock web part](https://support.microsoft.com/sharepoint/sites-pages/use-the-world-clock-web-part) | Toggle the **Show days of the week** to **On**. |
| 5 | [Weather web part](https://support.microsoft.com/sharepoint/sites-pages/show-the-weather-on-your-page) | Decide which temperate measurement system makes the most sense for your audience between **Fahrenheit** and **Celsius**. |
| 6 | [The Dashboard web part](use-dashboard-web-part-on-home-site) | Set the **Maximum number of cards to show** to 9. |
| 7 | [Image web part](https://support.microsoft.com/sharepoint/web-parts-and-apps-in-sharepoint/use-the-image-web-part) | Toggle **Add text over image** to **On**. |
| 8 | [File and Media web part](https://support.microsoft.com/sharepoint/sites-pages/use-the-file-and-media-web-part) | No settings guidance. |

[![Screenshot that shows Build SharePoint home site middle section.](../sharepointonline/media/homesites/create-sharepoint-home-site-for-viva-connections/build-site-overview-2.png)](../sharepointonline/media/homesites/create-sharepoint-home-site-for-viva-connections/build-site-overview-2.png#lightbox)

| Number | Web part | Customization guidance |
| --- | --- | --- |
| 9 | [Events web part](https://support.microsoft.com/sharepoint/sites-pages/use-the-events-web-part) | Select the **Filmstrip** layout and toggle **Show event images** to **On**. |
| 10 | [Quick Links web part](https://support.microsoft.com/sharepoint/sites-pages/use-the-quick-links-web-part) | Select the **Compact** layout and then toggle **Show image in layout** to **Yes**. |
| 11 | [News web part](https://support.microsoft.com/sharepoint/pages-in-sharepoint/use-the-news-web-part-on-a-sharepoint-page) | Select the **Side-by-side** layout, set the **Number of news posts to show** to 4. Then toggle **Show number of views**, **Show author**, and **Show publish date** to **On**. |
| 12 | [Call to action web part](https://support.microsoft.com/sharepoint/sites-pages/use-the-call-to-action-web-part) | No settings guidance. |

## Customize site details

After the site is built, edit site details to create a customized design that aligns with your organization's brand and identity. These [site details can be managed](https://support.microsoft.com/sharepoint/sites-pages/customize-your-sharepoint-site) from **Settings** &gt; **Change the look**.

- **Theme** – Select a theme that is ideal for the entire organization. If you make your SharePoint home site [a hub site](/en-us/sharepoint/dev/features/hub-site/hub-site-overview), this theme will get passed down to sites that associate with the hub.
- **Header** – Use the Compact header layout to reproduce the same look as your SharePoint home site.
- **Logo** – Under **Header** &gt; **Display**, select a logo that is recognizable to the entire organization.
- **Footer** – Footer navigation is optional and can be used to highlight popular portals and resources.

## Extensibility

Use the [SharePoint Framework](/en-us/sharepoint/dev/spfx/sharepoint-framework-overview) (SPFx) to create [customized components like web parts](/en-us/sharepoint/dev/spfx/web-parts/overview-client-side-web-parts) and [SharePoint app in Teams Dashboard cards](/en-us/sharepoint/dev/spfx/viva/design/design-intro) that can be surfaced on a SharePoint home site and throughout the SharePoint app in Teams experience. SPFx is the only extensibility and customization option for Cthe SharePoint app in Teams. [Learn more about SharePoint app in Teams extensibility](/en-us/sharepoint/dev/spfx/viva/overview-viva-connections).

## Best practices before launching your new SharePoint home site

- A SharePoint home site is used by the entire organization, so the site needs to be [inclusive and easily accessible on all devices](https://support.microsoft.com/en-us/accessibility/sharepoint/get-ready-build-an-accessible-sharepoint-site) and potentially [needs to be viewed in other languages](https://support.microsoft.com/sharepoint/sites-pages/create-multilingual-sharepoint-sites-pages-and-news).
- The SharePoint home site will be viewed by a high volume of users. Make sure you [manage site performance](/en-us/sharepoint/portal-health) through the planning and building phases.
- Before launching the SharePoint home site broadly, test the site with a handful of users to make sure key tasks and resources are readily accessible and fully functioning.
- Consider using the [Portal launch scheduler](/en-us/microsoft-365/enterprise/portallaunchscheduler) to help you follow a phased roll-out approach by batching viewers in waves and managing the URL redirects for the new portal.

## Next: Enable and set up global navigation

Once you’ve set a communication site as a SharePoint home site, you'll be able to [enable and set up global navigation in the SharePoint app bar](sharepoint-app-bar). Global navigation can be set up while you're designing your SharePoint home site but will only be accessible to visitors using SharePoint or the SharePoint app in Teams. Links from global navigation can be [imported to the Resources section](edit-resources#import-sharepoint-links) so they appear across all instances of the SharePoint app in Teams (desktop, mobile, and web).

## Learn more

[Plan, build, and launch a SharePoint home site for your organization](sharepoint-app-in-teams-plan)

[Creating and launching a healthy SharePoint portal](/en-us/sharepoint/portal-health)

[Plan, build, and launch the SharePoint app in Teams for your organization](plan-sharepoint-app-in-teams)