---
layout: Conceptual
title: Get started planning and implementing SharePoint navigation design - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/plan-implement-navigation-design
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
ms.topic: get-started
ms.service: sharepoint-online
ms.subservice: sites-pages
ms.localizationpriority: high
ms.collection:
- Strat_SP_modern
- m365solution-spintranet
- m365solution-scenario
- M365-collaboration
- highpri
ms.custom:
- seo-marvel-apr2020
search.appverid:
- SPO160
- MET150
description: Learn about how architecture design stems from the unique needs of your organization and user
locale: en-us
document_id: eed991ea-9da7-45d3-5692-b4502f2c3bff
document_version_independent_id: 528d2485-9316-fa13-c2fb-a6e55cd440c9
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/plan-implement-navigation-design.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: plan-implement-navigation-design
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/plan-implement-navigation-design.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 3a077fdb-cfd2-3f68-9533-1b97ee2798d8
---

# Get started planning and implementing SharePoint navigation design - SharePoint in Microsoft 365 | Microsoft Learn

To begin, understand that no two organizations will build identical architecture structures in SharePoint. This is because your architecture design stems from the unique needs of your organization and users. Also, remember that architectural structure will change over time as you learn more about user needs and as the business scales and grows.

Similar to SharePoint intranet content, SharePoint architecture should be reviewed and revised as often as needed to ensure users have easy access to relevant content and resources.

**In this article:**

- Explore how to understand users' needs, content requirements, and scope
- Learn how to think about planning, implementing, and managing global, hub, and local navigation

## First: Understand your users

The most important step in planning an effective information architecture is understanding your users:

- Who are your users? What key roles do they have?
- What vocabulary do they have? What terms do they use to look for content?
- What do they want to learn?
- What do they want to do? What are their top tasks?

## Next: Understand your content

In addition to understanding your users and their experiences, you also need to understand your content. Think about how content is distributed across current intranet sites, libraries, and folders. [Look at usage data](https://support.microsoft.com/office/view-usage-data-for-your-sharepoint-site-2fa8ddc2-c4b3-4268-8d26-a772dc55779e) to understand what content is accessed most and least frequently.

Think about the categories of information in your organization, such as services, products, areas of expertise, and functions. Don’t just think about the organization chart. Think about the information people need in their daily work and the key business outcomes you want to achieve. Use this information, and your knowledge of your users, to organize groups of related information, such as key business processes, major projects or initiatives, key business roles, frequent tasks, services, as well as organizational units.

## Then: Understand your scope

Information architecture includes five primary elements:

- **Portal navigational structure** – How you structure your sites so that users can find content including the [home site](home-site) of your intranet.
- **Hub structure and organization** – How you [group together similar topics, tasks, and content](planning-hub-sites).
- **Site and page architecture** – How content is organized on each site and page so that users can further navigate or consume content effectively.
- **Metadata architecture** – How to structure and label your individual content items for browsing and searching as well as compliance and retention.
- **Search experiences** – How your users “consume” information architecture in addition to browsing.

## Finally: Decide which navigational model works and start to plan and implement

**New navigational design for a site:**

Note

To edit site navigation, you must be a site owner.

| Plan | Build | Manage |
| --- | --- | --- |
| 1. Ensure you understand your [users needs and the site goals](information-architecture-modern-experience#understand-your-role-and-how-to-collaborate). 2. Learn about designing for [local navigation](information-architecture-modern-experience#local-navigation). | 1. Customize the [navigation](https://support.microsoft.com/office/customize-the-navigation-on-your-sharepoint-site-3cd61ae7-a9ed-4e1e-bf6d-4655f0bf25ca) of your site. 2. Consider [joining a hub site](https://support.microsoft.com/office/associate-a-sharepoint-site-with-a-hub-site-ae0009fd-af04-4d3d-917d-88edb43efc05) to increase viewership. 3. Target [navigational links](https://support.microsoft.com/office/target-navigation-news-and-files-to-specific-audiences-33d84cb6-14ed-4e53-a426-74c38ea32293) to specific audiences. | 1. Use [site analytics](https://support.microsoft.com/office/view-usage-data-for-your-sharepoint-site-2fa8ddc2-c4b3-4268-8d26-a772dc55779e) to understand how users are engaging with your site. 2. Review site navigation as needed to ensure all links are active, relevant, and up to date. |

**New navigational design for a hub:**

Note

To edit hub navigation, you must be the hub owner or tenant administrator. The default navigation menu style for team sites hub navigation will be cascading.

| Plan | Build | Manage |
| --- | --- | --- |
| 1. Ensure you understand your [users needs and the site goals](information-architecture-modern-experience#understand-your-role-and-how-to-collaborate). 2. Learn about designing for [global navigation](information-architecture-modern-experience#global-navigation). 3. Consider using a [hub site](planning-hub-sites) to group similar sites together. 4. Learn about [multi-lingual](https://support.microsoft.com/office/create-multilingual-communication-sites-pages-and-news-2bb7d610-5453-41c6-a0e8-6f40b3ed750c) considerations. | 1. Decide on a [menu style](plan-navigation-modern-experience#navigation-menus-in-sharepoint). 2. Customize the [navigation](https://support.microsoft.com/office/customize-the-navigation-on-your-sharepoint-site-3cd61ae7-a9ed-4e1e-bf6d-4655f0bf25ca) for individual sites. 3. Set up [associations and permissions for hub sites](https://support.microsoft.com/office/set-up-your-sharepoint-hub-site-e2daed64-658c-4462-aeaf-7d1a92eba098). | 1. Use [hub analytics](https://support.microsoft.com/office/view-usage-data-for-your-sharepoint-site-2fa8ddc2-c4b3-4268-8d26-a772dc55779e) to understand how users are engaging with your site. 2. Review site navigation as needed to ensure all links are active, relevant, and up to date. |

**New navigational design for an intranet site:**

Note

To edit intranet site navigation, you must be the hub owner or tenant administrator.

| Plan | Build | Manage |
| --- | --- | --- |
| 1. Define new intranet [business objectives](plan-intranet#identify-initiatives) and choose [pilot scenarios](plan-intranet#choose-pilot-scenarios). 2. Learn about [user needs](information-architecture-principles#get-organized) and find methods to [test potential designs](https://www.nngroup.com/articles/quantitative-user-research-methods/). 3. Take an inventory of your current sites and subsites 4. Plan the [home site](home-site). | 1. Start [planning hubs](planning-hub-sites) and your [home site](home-site) by grouping high priority tasks and content. 2. Set up [associations and permissions for hub sites](https://support.microsoft.com/office/set-up-your-sharepoint-hub-site-e2daed64-658c-4462-aeaf-7d1a92eba098). 3. Release hubs and associated sites in phases. | 1. Establish an intranet review team that ensures navigation and content are up to date and aligned with your organization. 2. Regularly review [hub and site analytics](https://support.microsoft.com/office/view-usage-data-for-your-sharepoint-site-2fa8ddc2-c4b3-4268-8d26-a772dc55779e) to track page traffic and popular content. 3. Make navigation changes based on your learning from user testing and analytics. |

[**Next: learn how to get started planning and implementing SharePoint site navigation**](plan-navigation-modern-experience)