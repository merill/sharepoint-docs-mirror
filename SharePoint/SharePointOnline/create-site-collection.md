---
layout: Conceptual
title: Create a site - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/create-site-collection
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
ms.custom:
- TellMe_Admin
- O365P_SitesMgmtModern
- O365M_SitesMgmtModern
- O365E_SitesMgmtModern
- How To
- seo-marvel-apr2020
- admindeeplinkSPO
ms.service: sharepoint-online
ms.subservice: sites-pages
ms.localizationpriority: medium
ms.collection:
- Strat_SP_admin
- M365-collaboration
- m365initiative-spsitemanagement
search.appverid:
- SPO160
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 3a3d7ab9-5d21-41f1-b4bd-5200071dd539
description: This article describes how users with at least SharePoint admin permissions can create sites in the SharePoint admin center.
locale: en-us
document_id: 0419db4c-9918-fcbe-53b3-4aca315e7703
document_version_independent_id: 0eca18cd-d073-8a6c-47ba-3e3330d63167
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/create-site-collection.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: create-site-collection
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/create-site-collection.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: d0895c8a-1c2e-4d3b-2d25-a2c3cb826e0f
---

# Create a site - SharePoint in Microsoft 365 | Microsoft Learn

This article explains how users with at least [SharePoint Administrator](sharepoint-admin-role) permissions in Microsoft 365 can create sites (formerly known as "site collections") in the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219). To learn about creating sites and managing users and groups using Microsoft PowerShell, see [Create SharePoint sites and add users with PowerShell](/en-us/microsoft-365/enterprise/create-sharepoint-sites-and-add-users-with-powershell).

For info about creating site collections in SharePoint Server, see [Create a site collection in SharePoint Server](sites/create-a-site-collection).

## Create a team site or communication site

1. Go to [**Active sites** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185220), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

Note

If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the Active sites page.

1. Select **Create**.

    ![The Create button on the Active sites page.](sharepointonline/media/create-site-button.png)

    Tip

    If you go to **Resources** &gt; **Sites** in the Microsoft 365 admin center and select **Add a site**, it opens [**Active sites** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185220) in a new tab, and opens the Create a site panel.
2. Select **Team site** (to create a Microsoft 365 group-connected team site), **Communication site**, or **Browse more sites**.

    ![The Create a site panel.](sharepointonline/media/new-site-creation-admin.png)
3. Browse and select a template. Select **Use template**.
4. Follow the steps to specify a site name, owner, language, and other settings. When you're done, select **Create site**.

    Note

    If you enter a site name and another site already exists at the default address for that name, the site address is automatically changed to an available address. For example, if you enter "Marketing" as the site name, and you already have a site at /sites/marketing, you'll receive a warning ***This site address is available with modification*** and will be offered a new URL automatically at /sites/marketing2. If you want to reuse the URL "marketing" for the new site, you need to [permanently delete the existing site](delete-site-collection#permanently-delete-a-site) or [delete the redirect at that address](manage-site-redirects).

## Create a classic site

We recommend using the new site templates for all your new sites. However, if you need to create a site that uses a classic template, you can do so using the following steps:

1. Go to [**Active sites** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185220), and select **Create**.

    ![The Create button on the Active sites page.](sharepointonline/media/create-site-button.png)
2. At the bottom of the panel, select **Brose more sites**.

    ![Image of the site creation panel with admin controls highlighted.](sharepointonline/media/new-site-admin-bottom.png)
3. Under **Choose a template**, select **More templates**.

    ![More templates in the Choose a template list.](sharepointonline/media/create-site-classic-template.png)

    - In the **Title** box, enter a name for the site.
    - In the **Web Site Address** drop-down lists, select a domain name and a URL path—either **/sites/** or \*\*/teams/—and then type a URL name for the site.
    - In the **Template Selection** section, in the **Select a language** drop-down list, select a language for the site. You can enable the SharePoint multiple language interface on your sites, but the primary language for the site remains the one you select here.

        Note

        It's important to select the appropriate language for the site, because once it's set, it can't be changed. After creating a site, verify the locale and regional settings are accurate. (For example, a site created for Chinese will have its locale set to China.)
    - In the **Template Selection** section, under **Select a template**, select the template that most closely describes the purpose of your site.

        Tip

        For more information about the classic templates, see [Using templates to create different kinds of SharePoint sites](https://support.office.com/article/449eccec-ff99-4cf3-b62e-dcfee37e8da4).
    - In the **Time Zone** box, select the time zone that's appropriate for the location of the site.
    - In the **Administrator** box, enter the user name of the person you want to be the site administrator. You can also use the **Check Names** or **Browse** button to find a user to make site administrator.
    - In the **Storage Quota** box, enter the number of megabytes (MB) you want to allocate to this site. Don't exceed the available amount that is displayed next to the box.
    - In the **Server Resource Quota** box, accept the resource quota default. This setting no longer affects the resource amounts available for the site.
4. Select **OK**.