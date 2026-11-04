---
layout: Conceptual
title: Planning considerations for a global intranet - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/set-up-global-intranet
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-06-25T00:00:00.0000000Z
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: article
ms.service: sharepoint-online
ms.subservice: sites-pages
ms.localizationpriority: medium
ms.collection:
- Strat_SP_admin
- m365solution-spintranet
- m365solution-scenario
- highpri
ms.custom: admindeeplinkSPO
search.appverid:
- SPO160
- BSA160
- GSP150
- MET150
description: Learn about setting up a SharePoint intranet for a global organization.
locale: en-us
document_id: 6bf54ef5-8856-1194-7201-3e8498ba47ec
document_version_independent_id: 73ce3fa2-ee38-8be7-be2e-295785c23d1b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/Set-up-global-intranet.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: set-up-global-intranet
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/Set-up-global-intranet.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/c6f99e62-1cf6-4b71-af9b-649b05f80cce
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3f56b378-07a9-4fa1-afe8-9889fdc77628
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: ad12b749-0f7a-641c-24c4-57f49014e9d2
---

# Planning considerations for a global intranet - SharePoint in Microsoft 365 | Microsoft Learn

If your organization has team members in multiple locations around the world, you have additional considerations and options as you plan for your SharePoint intelligent intranet. For example, you may want different branding for individual regions. You may want to target content to team members in certain countries/regions. You may want to provide sites in multiple languages. Or you may need to comply with data residency requirements in certain countries/regions. Here are options to consider which can be used independently or in combination to meet the needs of your global intranet and create the best experience for your users.

Hub sites

Multilingual sites and pages

Regional settings

Audience targeting

Multi-Geo for data residency requirements

## Hub sites

The advantage to using hub sites is that they provide a flat architecture that is flexible and carries branding and navigation across multiple sites connected to the hub.

![Hub site concept](sharepointonline/media/hubsiteexample.png)

If you have subsidiaries in different regions that have their own branding and navigation, an option for you is to create a hub site for each region.

[Learn how to plan for hub sites](planning-hub-sites)

## Multilingual sites and pages

A separate consideration for a global or regional intranet is whether you want to set up sites on your intranet to be multilingual so that users can read and work with content in their preferred languages.

User interface elements like site navigation, site title, and site description can be shown in the [user's preferred language](https://support.microsoft.com/office/change-your-personal-language-and-region-settings-caa1fccc-bcdb-42f3-9e5b-45957647ffd7). Additionally, you can provide pages and news posts on communication sites that you translate to users' preferred languages. For example, you may have provisioned your site with a default language of English, but you have users who have set their language preference to Spanish, and users who have set their language preference to French. You can set up your site(s) to view in the site default language as well as in French and Spanish.

Note

User interface elements and pages are not translated automatically. Each page created in your default language can have a corresponding page in a chosen target language that you, or someone you assign, manually translates. After you translate such a page and publish it, it will automatically be displayed to users who have set a preferred language in their Office personal profile.

### Next steps for multilingual sites and pages

- Site owners determine which [languages to support](https://support.microsoft.com/office/languages-supported-by-sharepoint-dfbf3652-2902-4809-be21-9080b6512fff) on their sites
- Site owners [enable multilingual features and choose languages](https://support.microsoft.com/office/create-multilingual-communication-sites-pages-and-news-2bb7d610-5453-41c6-a0e8-6f40b3ed750c#bkmk_enable)
- [Create multilingual communication sites, pages, and news](https://support.microsoft.com/office/create-multilingual-communication-sites-pages-and-news-2bb7d610-5453-41c6-a0e8-6f40b3ed750c)
- [Set up a multilingual site name, navigation and footer](https://support.microsoft.com/office/create-multilingual-communication-sites-pages-and-news-2bb7d610-5453-41c6-a0e8-6f40b3ed750c#bkmk_muitranslations)

## Regional settings for sites

Site owners can change [regional settings](https://support.microsoft.com/office/change-regional-settings-for-a-site-e9e189c7-16e3-45d3-a090-770be6e83c1a) for a site to specify calendar settings and how numbers, dates, and times are shown for all users of a site. Individual users can choose to [specify their own personal settings](https://support.microsoft.com/office/change-your-personal-language-and-region-settings-caa1fccc-bcdb-42f3-9e5b-45957647ffd7).

## Audience targeting

Audience targeting helps the most relevant content get to the right audiences. By enabling audience targeting, specific content will be prioritized to specific audiences through SharePoint web parts, page libraries, and navigational links.

For example, you might want to prominently display news about a sales meeting in Asia to users in that region rather than display it prominently to all regions.

### Next steps for audience targeting

- Learn how to [set up audience targeting](https://support.microsoft.com/office/target-content-to-a-specific-audience-on-a-sharepoint-site-68113d1b-be99-4d4c-a61c-73b087f48a81)
- Learn more about [creating groups](/en-us/microsoft-365/admin/create-groups/create-groups) for audience targeting

## Microsoft 365 Multi-Geo

Some countries/regions have laws requiring that user data be stored within that country. To accommodate these requirements, you can set up a Microsoft 365 Multi-Geo tenant. With a Multi-Geo tenant, your tenant may be provisioned in one country, but user data for SharePoint, OneDrive, and Exchange can be stored in other countries/regions. For example, you may have 5,000 employees in Europe and 8,000 employees in North America. All the users are working within the same tenant, but data for the 5,000 employees are stored in Europe while data for the 8,000 employees is stored in North America. This allows for seamless collaboration across your organization while still meeting data residency requirements.

After Multi-Geo is enabled for your tenant, you can set up and manage geo locations on the [Geo locations page](https://go.microsoft.com/fwlink/p/?linkid=2185076) in the SharePoint admin center.

![SharePoint Multi-Geo Admin Center](sharepointonline/media/sharepoint-multi-geo-admin-center.png)

Note

Due to the unique nature of data requirements in China, a differentiated version of Office 365 is available and operated by a partner from datacenters inside China. This service is not considered a Multi-Geo service. It is powered by technology that Microsoft has licensed to 21Vianet. For more information, see [Office 365 operated by 21Vianet - Service Descriptions](/en-us/office365/servicedescriptions/office-365-platform-service-description/office-365-operated-by-21vianet).

A differentiated service called Microsoft Cloud Germany is being migrated to Office 365 services in the new German datacenter. For more information, see [Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions](/en-us/microsoft-365/enterprise/ms-cloud-germany-transition).

### Next steps for Microsoft 365 Multi-Geo

- Learn how to [plan and set up](/en-us/microsoft-365/enterprise/multi-geo-tenant-configuration) Multi-Geo for your organization
- Learn how to [set up Multi-Geo](https://techcommunity.microsoft.com/t5/office-365-blog/now-available-multi-geo-in-sharepoint-and-office-365-groups/ba-p/263302) in the SharePoint admin center to enable Multi-Geo features [across the user experience](/en-us/microsoft-365/enterprise/multi-geo-user-experience)