---
layout: Conceptual
title: Hybrid OneDrive and SharePoint in Microsoft 365 - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/hybrid
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2022-06-10T00:00:00.0000000Z
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords: NOCSH
ms.topic: concept-article
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- essentials-get-started
ms.custom: intro-get-started
search.appverid: MET150
description: Learn about setting up hybrid OneDrive and SharePoint in Microsoft 365.
locale: en-us
document_id: 7695e99b-84c3-f4da-f7c4-6f6eb20c8c03
document_version_independent_id: dc27b0b5-dff1-5c36-bf3a-a69a71abcb2d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/hybrid.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: hybrid
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/hybrid.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/dc29fde7-b949-4135-9273-ad8e4a53d516
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/25d6050c-71f5-4b48-8bc7-575debd6530a
platformId: 6a3c00e5-34ae-5961-a486-4d08d8db9862
---

# Hybrid OneDrive and SharePoint in Microsoft 365 - SharePoint in Microsoft 365 | Microsoft Learn

If you use SharePoint Server on-premises, there are several options for integrating that environment with SharePoint in Microsoft 365 to provide your users with a more seamless environment when navigating back and forth between the two. You can configure these options to improve your users' experience during a migration from on-premises to the cloud, or you can use them in the long term if you plan to continue using SharePoint Server.

If you have a SharePoint Server environment, we recommend setting up SharePoint Server hybrid as part of your SharePoint and OneDrive in Microsoft 365 rollout. For complete details on setting up SharePoint and OneDrive hybrid, see [Hybrid for SharePoint Server](/en-us/sharepoint/hybrid/hybrid) and [Explore SharePoint Server hybrid](/en-us/sharepoint/hybrid/explore-sharepoint-server-hybrid/).

### Hybrid features

The following hybrid features are available for integrating SharePoint Server with Microsoft 365:

- **OneDrive** - OneDrive links are provided in SharePoint Server which direct users to OneDrive in Microsoft 365.
- **Site following** - Followed sites from both locations are consolidated in the SharePoint in Microsoft 365 followed sites list.
- **Profiles** - Profiles exist in both locations, but SharePoint Server links to users' profiles redirect to profiles in Microsoft 365.
- **Extensible app launcher** - The SharePoint Server app launcher includes several tiles that link to Microsoft 365.
- **Hybrid self-service site creation** - Users going to the default SharePoint Server site creation page are redirected to the Microsoft 365 Groups creation page, allowing them to create sites in SharePoint in Microsoft 365.
- **Search** - Cloud hybrid search crawls on-premises content and indexes it in the search index in Microsoft 365. Users can search the Microsoft 365 index from either location.
- **Taxonomy and content types** - Enables you to have a single taxonomy and content types list that spans SharePoint Server and SharePoint in Microsoft 365. See [Plan hybrid SharePoint in Microsoft 365 taxonomy and hybrid content types](/en-us/sharepoint/hybrid/plan-hybrid-sharepoint-taxonomy-and-hybrid-content-types) for more information.

See [SharePoint hybrid sites and search](/en-us/sharepoint/hybrid/sharepoint-hybrid-sites-and-search) for more details on these options.

### Hybrid OneDrive

If you currently use OneDrive or MySites in SharePoint Server, we highly recommend deploying hybrid OneDrive. With hybrid OneDrive, users are redirected from their on-premises OneDrive to OneDrive in Microsoft 365. Hybrid OneDrive allows for seamless navigation to OneDrive in the cloud from both SharePoint Server and Microsoft 365.

When you deploy hybrid OneDrive, the OneDrive links in the SharePoint Server ribbon and app launcher will point to OneDrive in Microsoft 365.

If you don't use OneDrive in SharePoint Server, but you do have an on-premises SharePoint environment, you may still want to consider deploying hybrid OneDrive. Doing so will update the OneDrive navigation links in SharePoint Server to point to OneDrive in Microsoft 365 – again, giving your users seamless navigation to OneDrive in the cloud from either location.

Important

If your users have files in on-premises OneDrive, they may have trouble accessing them unless they've bookmarked the old URL. It's important to have a migration plan for these files before you deploy hybrid OneDrive.

For more info about how to configure OneDrive in a hybrid scenario and how it works, see [Plan hybrid OneDrive](/en-us/sharepoint/hybrid/plan-hybrid-onedrive-for-business/).