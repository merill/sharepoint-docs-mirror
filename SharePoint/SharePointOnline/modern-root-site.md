---
layout: Conceptual
title: Modernize your root site - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/modern-root-site
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-06-25T00:00:00.0000000Z
ms.reviewer: waynewin
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
- BSA160
description: Learn about the options for modernizing the root site for your organization if it's currently a classic site.
locale: en-us
document_id: 7a824ca6-37ae-11c4-f04e-5de1ba5551c5
document_version_independent_id: b02f6141-9dc9-1e26-8beb-9a1f21dd042e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/modern-root-site.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: modern-root-site
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/modern-root-site.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 764147c1-7495-fb4a-ad62-abc065ee17fc
---

# Modernize your root site - SharePoint in Microsoft 365 | Microsoft Learn

When Microsoft SharePoint is set up for an organization, a root (or top-level) site is created. Before April 2019, the site was created as a classic team site. Now, a communication site is set up as the root site for new organizations. If your environment was set up before April 2019, you can modernize your root site in three ways:

- If you have a different site that you want to use as your root site (a communication site or modern team site that isn't connected to a Microsoft 365 group), replace (swap) the root site with the other site.
- If you want to keep using the classic team site but add a new modern home page and enable full-width pages with horizontal navigation, [enable the communication site experience on the site](modernize-classic-team-site).
- If you want to continue using the classic team site, [enable the modern site pages library experience](/en-us/sharepoint/dev/transform/modernize-userinterface-lists-and-libraries) and [set a modern page as the home page](/en-us/sharepoint/dev/transform/modernize-userinterface-site-pages) of the root site. This gives users a modern team site experience with the left navigation.

Important

Before you launch an intranet landing page at your root site location, we strongly encourage you to [review the guidance about launching healthy portals](portal-health). Some functionality is introduced gradually to organizations that have opted in to the [Targeted release option in Microsoft 365](/en-us/office365/admin/manage/release-options-in-office-365). This means that you might not yet see some features described in this article, or they might look different.

## What's the root site?

The root site for your organization is one of the sites that's provisioned automatically when you purchase and set up a Microsoft 365 or Microsoft 365 plan that includes SharePoint. The URL of this site is typically *contoso*.sharepoint.com, the default name is "Communication site," and the owner is Company Administrator (all Global Administrators in the organization). The root site can't be connected to a Microsoft 365 group.

Warning

The root (top-level) site for your organization can't be deleted. If you're a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) and [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365, you can replace the root site with a different site.

Microsoft recommends that you use roles with the fewest permissions. Using lower permissioned accounts helps improve security for your organization. Global Administrator is a highly privileged role that should be limited to emergency scenarios when you can't use an existing role.

## Replace your root site

Before you begin, make sure you:

1. Note any "Featured links" that have been added on the SharePoint start page. You'll need to add them again after you replace the root site. [Learn how](change-links-list-on-sharepoint-home-page)
2. Review your source site to make sure it has the same policies, permissions, and external sharing settings as your current root site.
3. Communicate the upcoming change to users. This can help reduce user confusion and calls to your help desk. If users are using files on the sites you're replacing, ask them to close the files and check the site recycle bin to make sure it contains no files they want to keep.

By default, a site redirect will be created that will redirect traffic from the source site to the root site. For info about site redirects, see [Manage site redirects](manage-site-redirects).

If you've [turned on audit log search](/en-us/office365/securitycompliance/turn-audit-log-search-on-or-off), the following events can be recorded:

- Scheduled site swap: A site replacement (swap) was scheduled at this time
- Swapped site: A site replacement (swap) completed successfully at this time
- Failed site swap: A site replacement (swap) failed at this time and won't be tried again

### Limitations

- The site you select as the new root site must be a communication site (SITEPAGEPUBLISHING#0) or a modern team site that isn't connected to a Microsoft 365 group (STS#3) and where **the publishing feature has never been activated.**
- When you replace the root site, both the current site and the new site can't be hub sites or associated with a hub. If either site is a hub site, unregister it as a hub site, replace the root site, and then re-register the site as a hub site. If either site is associated with a hub, disassociate the site, replace the root site, and then reassociate the site. [Learn how to manage hubs in the new SharePoint admin center](manage-sites-in-new-admin-center#change-a-sites-hub-association)
- Replacing the root site with another site replaces the entire site collection with the new site collection. If your current root site has subsites, they'll be archived.
- The site you select as the new root site must be within the same domain as the current root site.
- If the site is on hold, you'll receive an informative error and you can't replace the site.
- You as the admin must also be a member of the site that you are replacing.

### Use the new SharePoint admin center

We recommend replacing the root site at a time when site usage is low.

1. Go to [**Active sites** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185220), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the Active sites page.
2. In the upper right, make sure the **All sites** view is selected.
3. In the URL column, select to sort A to Z so the current root site appears at the top of the list.
4. Select the root site (https://contoso.sharepoint.com).
5. Select **Replace site** on the command bar.

    ![The Replace root site panel in the new SharePoint admin center](sharepointonline/media/replace-root-site.png)
6. In the **URL of the site you want to use** box, enter the full or relative URL of the site that you want to become the new root site.
7. Select **Save**.

    While the root site is being replaced, it might return a "not found" (HTTP 404) error for few minutes.

    After you replace the root site, content must be recrawled to update the search index. This might take some time depending on factors such as the amount of content in these sites. Anything dependent on the search index might return incomplete results until the sites have been recrawled.
8. If the new root site was an organization news site, update the URL. [Get a list of all organizational news sites](/en-us/powershell/module/sharepoint-online/get-spoorgnewssite?view=sharepoint-ps&amp;preserve-view=true)
9. If you disabled site redirects, you'll need to update sharing links and any apps or files (like the OneDrive sync app and OneNote files) to refer to the new URL.

Note

For info about using PowerShell to replace (swap) the root site, see [Invoke-SPOSiteSwap](/en-us/powershell/module/sharepoint-online/invoke-spositeswap).

Project Server sites might need to be validated to make sure they're still associated correctly.