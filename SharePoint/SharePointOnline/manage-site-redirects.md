---
layout: Conceptual
title: Manage site redirects - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/manage-site-redirects
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-12-22T00:00:00.0000000Z
ms.reviewer: adwood
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
customer_intent: As a SharePoint Administrator, I want to manage site redirects so that I can free up old URLs or ensure users are routed correctly.
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Strat_SP_admin
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
description: Learn how to view and delete site redirects in SharePoint.
locale: en-us
document_id: 3cfb6e9b-57d4-749f-a1d0-5f5c24e141ce
document_version_independent_id: e67e1021-7801-477b-1642-43c283742e59
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/manage-site-redirects.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-site-redirects
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/manage-site-redirects.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 4946e45a-3bec-28b3-563d-fda864fad2b4
---

# Manage site redirects - SharePoint in Microsoft 365 | Microsoft Learn

When you [change a SharePoint site address](change-site-address), such as [moving a site to a different geo location](/en-us/office365/enterprise/move-sharepoint-between-geo-locations), or [swapping a site](modern-root-site#replace-your-root-site), we automatically create redirects to ensure that prior URLs continue to work. These redirects are sites that use a special site template at the prior site URL.

For example, if you changed a site address from https://contoso.sharepoint.com/sites/*OldSiteName* to https://contoso.sharepoint.com/sites/*NewSiteName*, or if you moved a site from https://*contoso*.sharepoint.com/sites/SiteName to https://*contosoEUR*.sharepoint.com/sites/SiteName, we place a redirect (Template type REDIRECTSITE#0) at the old URL. This redirect contains special headers and logic to redirect your browser requests to the new site.

In some cases, you might want to free up the old URL to use it for a new site. To free up the old URL, you need to delete the redirect.

Note

After you delete a redirect, any request to that URL won't get redirected. This means that any bookmarks, links, or Shared With Me references aren't routed to the new URL.

## How do I remove a redirect?

1. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    Note

    If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell."
2. Connect to SharePoint as a [Global Administrator or SharePoint Administrator](sharepoint-admin-role) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
3. Run the following command:

    ```PowerShell
    Remove-SPOSite -Identity https://contoso.sharepoint.com/sites/OldSiteName
    ```

    Note

    If you get an error message "The operation is not supported for the site," make sure a retention policy isn't applied to the old or new URL for the site. You might need to remove the retention policy to delete the redirect.
4. When prompted, confirm that you want to delete the redirect.

You can confirm that the redirect is deleted by browsing to the URL. It should return a 404 error. You can also run `Get-SPOSite -Identity https://contoso.sharepoint.com/sites/OldSiteName`. It returns "we cannot get the site."

Note

You might need to clear your browser history and cache before browsing to the URL. Otherwise, it may take longer for the redirect site deletion to reflect, depending on individual browser settings.

## How do I get a list of all redirect sites?

To get a list of all redirect sites, run the following command:

```PowerShell
Get-SPOSite -Template REDIRECTSITE
```