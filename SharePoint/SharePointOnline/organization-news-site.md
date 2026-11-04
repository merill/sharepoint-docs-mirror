---
layout: Conceptual
title: Create an organization news site - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/organization-news-site
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2019-05-22T00:00:00.0000000Z
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
description: In this article, you'll learn how to specify a site as an official or authoritative organization news site.
locale: en-us
document_id: afaab219-ec0f-143b-b418-36fea8322393
document_version_independent_id: 2054b3a7-5acd-fd32-4517-442a48abbff4
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/organization-news-site.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: organization-news-site
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/organization-news-site.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: f38c1db0-a2a3-74ef-3996-d3704f4520be
---

# Create an organization news site - SharePoint in Microsoft 365 | Microsoft Learn

To specify SharePoint sites as "official" or "authoritative" for news in your organization, mark them as organization news sites. These posts get special visual treatment (see the "NEWS @ CONTOSO" color block below), and appear on the SharePoint start page.

![A post from an organization news site on the SharePoint start page](sharepointonline/media/c9335bc4-6be2-41e8-bd53-bf32a946d179.png)

SharePoint Administrators can create and specify up to 100 organization news sites. For multi-geo tenants, organization news sites would have to be set up for each geo location. Each geo location could use the same central organization news site, and/or have its own unique site that shows organization news specific to that region.

Note

If you set a communication site as the [home site for your organization](home-site-plan), it's automatically configured as an organization news site.

For more info about working with news, see [Use the News web part on a SharePoint page](https://support.office.com/article/C2DCEE50-F5D7-434B-8CB9-A7FEEFD9F165) and [Add news posts](https://support.office.com/article/495f8f1a-3bef-4045-b33a-55e5abe7aed7).

## Use Microsoft PowerShell to specify a site as an organization news site

1. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    Note

    If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell."
2. Connect to SharePoint as a [Global Administrator or SharePoint Administrator](sharepoint-admin-role) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
3. Run the following command to designate the site as an organization news site:

    ```PowerShell
    Set-SPOOrgNewsSite -OrgNewsSiteUrl <site URL> 
    ```

    Example: `Set-SPOOrgNewsSite -OrgNewsSiteUrl https://contoso.sharepoint.com/sites/Marketing`

## Related commands

- View a list of all your organization news sites: [Get-SPOOrgNewsSite](/en-us/powershell/module/sharepoint-online/get-spoorgnewssite)
- Remove a site from the list of organization news sites: [Remove-SPOOrgNewsSite](/en-us/powershell/module/sharepoint-online/remove-spoorgnewssite)