---
layout: Conceptual
title: Lock and unlock sites - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/manage-lock-status
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-06-17T00:00:00.0000000Z
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
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
- M365-SAM
ms.custom:
- seo-marvel-apr2020
description: This article contains information about how to use the lock state of a site to control the actions allowed on the site.
locale: en-us
document_id: bea1ac5a-f66c-3678-e5e5-7672407d395f
document_version_independent_id: 00fffbdd-9663-2441-a5e8-2bf541f7b1d1
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/manage-lock-status.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-lock-status
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/manage-lock-status.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 730e4815-3194-813d-148c-aefed2e4dcd2
---

# Lock and unlock sites - SharePoint in Microsoft 365 | Microsoft Learn

By using the permissions of a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [more](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365, you can block access to a site or make a site read-only. Use Microsoft PowerShell to change the lock state of the site.

Note

You can't set the lock state on the root site. If the SharePoint administrator changes the SharePoint domain, OneDrive and SharePoint sites in a locked state (excluding sites connected to Microsoft Teams channels or Microsoft 365 Groups) are updated to the new domain.

## Change the lock state for a site

Follow these steps to change the lock state for a site by using PowerShell.

1. Install the SharePoint Online Management Shell by downloading and running the [SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251) or installing the module from the [PowerShell Gallery](https://www.powershellgallery.com/packages/Microsoft.Online.SharePoint.PowerShell/). If you installed a previous version of the SharePoint Online Management Shell, go to **Add or remove programs** and uninstall SharePoint Online Management Shell.
2. Connect to SharePoint as a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
3. At the PowerShell command prompt, type the following command, and then press Enter.

    ```PowerShell
    Set-SPOSite -Identity "<SiteURL>" -LockState "<State>"
    ```

    Where:`SiteURL` is the URL of the site that you want to lock or unlock and `State` is one of the following values:

    - **Unlock** to unlock the site and make it available to users.
    - **ReadOnly** to prevent users from adding, updating, or deleting content. A message appears on the site stating that the site is under maintenance and is read-only.
    - **NoAccess** to prevent users from accessing the site and its content. If you provided a `NoAccessRedirectUrl` value for your organization, traffic is redirected to the URL you specified. If you didn't set this URL, a 403 error is displayed.

    Note

    If the site was closed and made read-only through a [site closure policy](/en-us/sharepoint/sites/site-policy-overview#sharepoint-site-policy-options), the PowerShell command to unlock the site doesn't work.

    ```PowerShell
    Set-SPOTenant -NoAccessRedirectUrl 'https://www.contoso.com'
    ```

For more info about the `LockState` parameter, see [Set-SPOSite](/en-us/powershell/module/sharepoint-online/set-sposite). For more info about the NoAccessRedirectUrl parameter, see [Set-SPOTenant](/en-us/powershell/module/microsoft.online.sharepoint.powershell/set-spotenant).