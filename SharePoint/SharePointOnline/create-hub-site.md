---
layout: Conceptual
title: Create a hub site in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/create-hub-site
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-06-24T00:00:00.0000000Z
ms.reviewer: metorres
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords:
- CSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: sites-pages
ms.localizationpriority: medium
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
ms.assetid: 92bea781-15d8-4bda-805c-e441e2191ff3
description: In this article, you learn how to register a site as a hub site in the SharePoint admin center.
locale: en-us
document_id: bc4df1d8-955c-63d2-628e-8359391b8710
document_version_independent_id: 01326ab6-1270-d096-64e8-eb7d63ea9863
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/create-hub-site.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: create-hub-site
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/create-hub-site.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 8a35c2f0-83b9-b8f5-d801-8ffc32df634b
---

# Create a hub site in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn

If you have the permissions of a [SharePoint Administrator](sharepoint-admin-role) or higher in Microsoft 365, you can transform any existing site into a hub site.

Note

We recommend selecting a communication site, or a team site that uses the new template. If you use a classic team site, the hub navigation appears only on modern pages, and hub site settings will only appear on modern pages.Sites that are already associated with another hub can't be converted to a hub site. You can create up to 2,000 hub sites for an organization. This applies to hub-to-hub associations as well. Any site labeled as a hub site counts against this limit. There's no limit on the number of sites that can be associated with a hub site. When users associate their sites with a hub, it doesn't impact the permissions of either the hub site or the associated sites. It's important to make sure all users you allow to associate sites to the hub have permission to the hub.

## Create a hub site in the new SharePoint admin center

1. Go to [**Active sites** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185220), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

Note

If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the Active sites page.

1. Select the site, select **Hub** on the command bar, and then select **Register as hub site**.

    ![Registering a site as a hub site](sharepointonline/media/register-hub-site.png)

    Tip

    Using the Hub site menu, you can also associate a site with the hub site, change a site's association to a different hub site, or disassociate a site from a hub site.
2. Enter a display name for the hub site, and specify the individual users or security groups you want to allow to associate sites with the hub.

    ![The Register as hub site panel](sharepointonline/media/register-hub-site-panel.png)

    Important

    If you leave the **People who can associate sites with this hub** box empty, any user can associate their site with the hub.If you later want to change the hub site display name or the list of people who can associate sites with the hub, you need to use PowerShell or go to hub site settings on the hub site.
3. Select **Save**.