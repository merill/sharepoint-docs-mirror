---
layout: Conceptual
title: Set up a site template for your hub site - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/set-up-site-design-hub-site
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-06-25T00:00:00.0000000Z
ms.reviewer: metorres
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords:
- CSH
ms.topic: overview
ms.service: sharepoint-online
ms.subservice: sites-pages
ms.localizationpriority: medium
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Strat_SP_admin
- M365-collaboration
search.appverid:
- SPO160
- MOE150
- GEA150
- BSA160
- BCS160
- GSP150
- MET150
description: In this article, you will learn how to run scripts on sites when they're associated with a hub site.
locale: en-us
document_id: bd09eee5-c545-e689-1194-e6b6cd70d63c
document_version_independent_id: 81523a20-4bed-a41c-9f5e-e5b5200d2f75
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/set-up-site-design-hub-site.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: set-up-site-design-hub-site
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/set-up-site-design-hub-site.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: ff12cb3b-4c97-ba9b-e5cc-e370c3aab145
---

# Set up a site template for your hub site - SharePoint in Microsoft 365 | Microsoft Learn

A site template is one or more site scripts that Microsoft SharePoint runs when a site is associated with a hub site. Actions describe changes to apply to the new site, such as creating a new list or adding nodes to the site navigation. Site templates provide reusable lists and custom actions so your users can quickly get started with the features they need.

Note

For organizations using Multi-Geo Capabilities in Microsoft 365, hub site templates work only when sites are in the same geo location as the hub site.

Note

These instructions require a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365.

## 1. Create a JSON script, add it, and create the site template

Follow the steps in [Get started creating site templates and site scripts](/en-us/sharepoint/dev/declarative-customization/get-started-create-site-design/). For the full list of supported actions, see [Site template JSON schema](/en-us/sharepoint/dev/declarative-customization/site-design-json-schema/). Note that when you create the site template, the site template you provide ("64" for team site or "68" for communication site) doesn't matter.

## 2. Scope access to the hub site template

When a site template is first created, it is available to everyone. You can grant View rights to the site template. After rights are granted, only the users or groups (principals) specified have access. We recommend granting access to the same principal used to scope the hub site.

```PowerShell
Grant-SPOSiteDesignRights  
  -Identity <ID> 
  -Principals ("HR@contoso.sharepoint.com")  
  -Rights View 
```

Replace &lt;ID&gt; with the site design ID from when you added the site script.

## 3. Set your site template for the hub site

You can set the hub site template in two ways. You can do it using the following PowerShell command:

```PowerShell
Set-SPOHubSite https://contoso.sharepoint.com/sites/Marketing  
-Title "Marketing Hub"  
-LogoUrl https://contoso.sharepoint.com/sites/Marketing/SiteAssets/hublogo.png  
-Description "Hub for the Marketing division" 
-SiteDesignId "<ID>" 
```

Replace &lt;ID&gt; with the site script ID from when you added the site script.

You can also let hub site owners set the hub site template by using a new option available in the UI. For info about the hub site settings available to site owners, see [Set up your SharePoint hub site](https://support.office.com/article/e2daed64-658c-4462-aeaf-7d1a92eba098).