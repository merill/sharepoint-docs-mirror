---
layout: Conceptual
title: Creating and launching a healthy SharePoint portal - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/portal-health
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: andreye
ms.author: ruihu
author: maggierui
manager: jtremper
ms.date: 2026-06-25T00:00:00.0000000Z
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.service: sharepoint-online
ms.subservice: sites-pages
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- enabler-strategic
- m365initiative-spsites
description: Create and launch a healthy SharePoint portal to ensure a performant viewing experience
locale: en-us
document_id: a7e23d5c-f139-adcb-ed0e-cf395fda8906
document_version_independent_id: f09f734d-de34-4120-996f-4c2eb0bb89d7
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/portal-health.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: portal-health
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/portal-health.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/dc29fde7-b949-4135-9273-ad8e4a53d516
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/25d6050c-71f5-4b48-8bc7-575debd6530a
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 56f2fafb-0f36-2e44-ce31-4db7ed961803
---

# Creating and launching a healthy SharePoint portal - SharePoint in Microsoft 365 | Microsoft Learn

A **portal** is a Microsoft SharePoint site on your intranet with many site viewers who consume the content. In large organizations, you could have several, such as a company portal and an HR portal.

Typically portals have relatively few people who create and author the site and its content. Most visitors to the portal only read and consume the content. We don't recommend using SharePoint portals to host a town hall or live event.

Tip

Are you wanting to host a live event or town hall? Here are the options we recommend:

- [Learn about Microsoft Teams live events](/en-us/microsoftteams/teams-live-events/what-are-teams-live-events)
- [Learn about hosting events with Viva Engage](https://support.microsoft.com/office/attend-a-live-event-in-viva-engage-41f1afe3-2a8e-4998-a25b-843d96791b10)
- Link directly to the live event you are streaming (**not** through your portal)

## What type of site should I use as my portal?

SharePoint Online has several types of sites and page types. **For portals, we highly recommend using a communication site with a site page for the home page**, the default configuration when you create a communication site. Site pages allow you to use out-of-the-box web parts, custom web parts, and extensions.

To learn more, see [Create communication sites in SharePoint](https://support.microsoft.com/office/create-a-communication-site-in-sharepoint-7fb44b20-a72f-4d2c-9173-fc8f59ba50eb).

Important

**Modern Team sites** are designed for use on collaboration sites, like projects / interest groups / focus areas or when you would like to collaborate with other team members. To learn more, see [Create team sites in SharePoint](https://support.microsoft.com/office/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).

The **App page type** was designed to be used for specific business applications within SharePoint Online. It was not designed to be used as a SharePoint Team site or a SharePoint Portal. To learn more, see [Creating application pages in SharePoint](/en-us/visualstudio/sharepoint/creating-application-pages-for-sharepoint).

## Guidance

This set of guidance will walk you through best practices and recommendations before you launch your portal and how to keep your portal healthy.

| Icon | What to do | Follow this |
| --- | --- | --- |
| ![Deploy](/en-us/Office/media/icons/PNGs/deploy-blue-32.png) | [Plan the rollout of your portal](/en-us/Office365/Enterprise/planportallaunchroll-out) | Launch in waves |
| ![Document 3 blue 32](/en-us/office/media/icons/PNGs/document-3-blue-32.png) | [Portal design guidance](https://aka.ms/spdesignguidance) | Review the guidance while designing your sites |
| ![Page diagnostics tool](sharepointonline/media/page-diag-tool.png) | [Run the Page Diagnostics for SharePoint tool](/en-us/microsoft-365/enterprise/page-diagnostics-for-spo) | Validate your pages and follow the guidance |
| ![Bandwidth blue 32](/en-us/Office/media/icons/PNGs/bandwidth-blue-32.png) | Optimize your Performance | Follow the guidance below and run the Page Diagnostics for SharePoint tool |
| ![Global hyperlink blue 32](/en-us/Office/media/icons/PNGs/globe-hyperlink-blue-32.png) | [Use CDN for better performance](/en-us/microsoft-365/Enterprise/office-365-cdn-quickstart) | Implement Public and Private Content Delivery Networks (CDN) |
| ![Graph 4 blue 32](/en-us/Office/media/icons/PNGs/graph-4-blue-32.png) | [Batch REST API calls to SharePoint](/en-us/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis) | Combine operations into fewer requests |
| ![Analytics usage report blue 32](/en-us/Office/media/icons/PNGs/analytics-usage-report-blue-32.png) | [Improve performance for slow web parts](/en-us/microsoft-365/Enterprise/modern-web-part-optimization) | Follow guidance to remediate common issues |
| ![Bill blue](/en-us/Office/media/icons/bill-blue.png) | [Review page weight](/en-us/microsoft-365/Enterprise/modern-page-weight-optimization) | Follow guidance to reduce page weight in your site pages |
| ![Task list planning blue 32](/en-us/Office/media/icons/PNGs/task-list-planning-blue-32.png) | [Limit the number of requests to a page](/en-us/Office365/Enterprise/modern-page-call-optimization) | Limit the number of web parts and calls into SharePoint |
| ![Search document blue 32](/en-us/Office/media/icons/PNGs/search-document-blue-32.png) | [Limit the number of search requests on a page](/en-us/microsoft-365/Enterprise/modern-search-optimization) | Follow the guidance to limit the number of search requests on a page. |
| ![Picture photo blue 32](/en-us/Office/media/icons/PNGs/picture-photo-blue-32.png) | [Optimize your images](/en-us/microsoft-365/Enterprise/modern-image-optimization) | Follow basic image optimization for the web |
| ![Files blue 32](/en-us/Office/media/icons/PNGs/files-blue-32.png) | [Limit and use Iframes carefully](/en-us/microsoft-365/Enterprise/modern-iframe-optimization) | Don't use more than two Iframes on a page |
| ![Graph 3 blue](/en-us/office/media/icons/graph-3-blue.png) | [Optimize extensions](/en-us/microsoft-365/Enterprise/modern-custom-extensions) | Follow the guidance to optimize and limit your custom extensions |
| ![Task checklist planning blue 32](/en-us/office/media/icons/PNGs/task-checklist-planning-blue-32.png) | [Modern portal limits](/en-us/Office365/Enterprise/modern-portal-limits) | Follow the limits for modern portals to further optimize performance |
| ![Globe Internet](/en-us/Office/media/icons/globe-internet.png) | [Network optimization](/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges) | Configure your URLs and IP endpoints |