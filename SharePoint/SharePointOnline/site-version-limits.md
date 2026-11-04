---
layout: Conceptual
title: Change version history limits for a Site - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/site-version-limits
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: rekamath
ms.author: ruihu
author: maggierui
manager: jtremper
ms.date: 2024-10-03T00:00:00.0000000Z
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
search.appverid:
- SPO160
- SPS150
- MET150
description: This article provides guidance on how admins can set version history limits on individual sites.
locale: en-us
document_id: c933c7f7-924a-cc43-ac7c-935699f1bb02
document_version_independent_id: e97d8523-5f10-b517-618b-101f3c62d3fa
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/site-version-limits.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: site-version-limits
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/site-version-limits.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/c0439c36-80e3-415f-8e4c-6951e3f1b136
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/2812d699-d85f-4a7f-839d-44e218b35d24
platformId: 3d2fe94a-59f3-4d85-dffe-ea113401acc3
---

# Change version history limits for a Site - SharePoint in Microsoft 365 | Microsoft Learn

By default, organization level settings define the version history limits that are applied to all new document libraries created in a site. However, to meet specific content needs, admins can choose to set distinct version history limits on individual sites. This way, users can break the inheritance from organization limits on an individual site.

Version history limits for an individual site can be managed in the following ways:

| Version history limits option | Description |
| --- | --- |
| **Apply to all new and existing document libraries in a site:** | To achieve a consistent version storage policy for a site, you can choose to **set a limit to universally apply to all libraries** in the site. Using this option, the Version history limit set on site-level is applied to all the new document libraries created in the site and creates a background request to asynchronously process the update on existing document libraries. |
| **Apply to only new document libraries created in a site:** | To avoid impacting the settings on existing libraries, you can **set a version history limit only for new libraries**. Using this option, the Version history limits set on site-level are only applied to new document libraries created in the site. There are no changes made to the limits on the existing document libraries or on libraries that aren't enabled for versioning in the site. |
| **Apply to existing document libraries only in a site:** | You can update the limits **only on existing document libraries** on a site without setting a site level version history setting for new document libraries. Using this option creates a background request to asynchronously process the update on existing document libraries while allowing the new document libraries created in the site to inherit the organization level version history limits. |
| **Clear existing limits set on a site:** | You can **clear the existing limits on a site** to allow new document libraries created in the site to follow organization level limits.**Note:** Clearing a setting on a Site applies only to new document libraries created on the site and doesn't impact the settings on existing doc libraries or trim existing versions. |

**Example scenario**

Take an example of Contoso, where the default organization Version history limits are configured to Automatic setting and no version limits are initially applied on marketing and legal sites. To meet business needs, the admin can decide to apply 'Manual' setting on legal site, thus breaking inheritance of legal site with the organization default version setting.

The following is the version storage for Contoso:

- **Version storage behavior on marketing site**: Since no limits are configured for marketing site, all new document libraries created within marketing site collection inherit the organization default setting of automatic.
- **Version storage on legal site**: Since the legal site has manual settings configured, all new libraries created within the legal site have the manual settings applied.

[![Diagram of set version limits for a site level.](sharepointonline/media/version-history/set-version-limits-for-a-site.png)](sharepointonline/media/version-history/set-version-limits-for-a-site.png#lightbox)

Important

- Site level Version history limits can be set using PowerShell cmdlets only.
- Setting site level Version history limits doesn't trim existing versions to meet the new limits. Additional steps are needed to [trim existing versions on a site or library.](library-version-limits#manage-version-history-limits-for-a-library-using-powershell)
- Requests to update the limits on existing libraries are processed asynchronously by a background job, which can take up to 24 hours to process. You can use PowerShell to check the progress of the job.
- Cancelling an in-progress job stops the update on libraries that were not processed. This action doesn't revert the change for document libraries where the settings update was already processed.

## Manage Version history limits for a site using PowerShell

Follow these steps to manage Version history limits for a site by using PowerShell.

1. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    Note

    If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall **SharePoint Online Management Shell**.
2. Connect to SharePoint as a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
3. Run one of the following commands to manage version history limits on your site:

| **Action** | **PowerShell Command** |
| --- | --- |
| View the version history limits set on a site | Get-SPOSite -Identity $siteUrl | fl Url, EnableAutoExpirationVersionTrim, ExpireVersionsAfterDays, MajorVersionLimit |
| Set Automatic version history limits on a site. | To set Automatic Version History Limits for all libraries on a site:`Set-SPOSite -Identity $siteUrl``-EnableAutoExpirationVersionTrim $true`Append `-ApplyToNewDocumentLibraries` parameter to apply only to new document libraries on the site:`Set-SPOSite -Identity $siteUrl``-EnableAutoExpirationVersionTrim $true``-ApplyToNewDocumentLibraries`Supply `-FileTypesForVersionExpiration` parameter with an array of file types and append `-ApplyToNewDocumentLibraries` parameter to apply automatic version history limit on those file types in new document libraries on the site:`Set-SPOSite -Identity $siteUrl``-EnableAutoExpirationVersionTrim $true``-ApplyToNewDocumentLibraries``-FileTypesForVersionExpiration @("<file type 1>", "<file type 2>")`Append `-ApplyToExistingDocumentLibraries` to apply only to existing document libraries on a site:`Set-SPOSite -Identity $siteUrl``-EnableAutoExpirationVersionTrim $true``-ApplyToExistingDocumentLibraries` |
| Set Manual limits with Count and time parameters on a site. | To set Manual limits with Count and time parameters for all libraries on a site:`Set-SPOSite -Identity $siteUrl``-EnableAutoExpirationVersionTrim $false``-MajorVersionLimit <delete major versions exceeding limit>``-MajorWithMinorVersionsLimit <number of major versions for which all minor versions will be kept>``-ExpireVersionsAfterDays <delete versions exceeding time limit set in days>`Append `-ApplyToNewDocumentLibraries` parameter to apply only to new document libraries on the site:`Set-SPOSite -Identity $siteUrl``-EnableAutoExpirationVersionTrim $false``-MajorVersionLimit <delete major versions exceeding limit>``-MajorWithMinorVersionsLimit <number of major versions for which all minor versions will be kept>``-ExpireVersionsAfterDays <delete versions exceeding time limit set in days>``-ApplyToNewDocumentLibraries`Supply `-FileTypesForVersionExpiration` parameter with an array of file types and append `-ApplyToNewDocumentLibraries` parameter to apply automatic version history limit on those file types in new document libraries on the site:`Set-SPOSite -Identity $siteUrl``-EnableAutoExpirationVersionTrim $false``-MajorVersionLimit <delete major versions exceeding limit>``-MajorWithMinorVersionsLimit <number of major versions for which all minor versions will be kept>``-ExpireVersionsAfterDays <delete versions exceeding time limit set in days>``-ApplyToNewDocumentLibraries``-FileTypesForVersionExpiration @("<file type 1>", "<file type 2>")`Append `-ApplyToExistingDocumentLibraries` to apply only to existing document libraries on a site:`Set-SPOSite -Identity $siteUrl``-EnableAutoExpirationVersionTrim $false``-MajorVersionLimit <delete major versions exceeding limit>``-MajorWithMinorVersionsLimit <number of major versions for which all minor versions will be kept>``-ExpireVersionsAfterDays <delete versions exceeding time limit set in days>``-ApplyToExistingDocumentLibraries` |
| Set Manual count with no expiration limit on a site. | To set Manual limits with Count limits set the `-ExpireVersionsAfterDays` parameter to `0:``Set-SPOSite -Identity $siteUrl``-EnableAutoExpirationVersionTrim $false``-MajorVersionLimit <delete major versions exceeding limit>``-MajorWithMinorVersionsLimit <number of major versions for which all minor versions will be kept>``-ExpireVersionsAfterDays 0`Append `-ApplyToNewDocumentLibraries` parameter to apply only to new document libraries on the site:`Set-SPOSite -Identity $siteUrl``-EnableAutoExpirationVersionTrim $false``-MajorVersionLimit <delete major versions exceeding limit>``-MajorWithMinorVersionsLimit <number of major versions for which all minor versions will be kept>``-ExpireVersionsAfterDays 0``-ApplyToNewDocumentLibraries`Supply `-FileTypesForVersionExpiration` parameter with an array of file types and append `-ApplyToNewDocumentLibraries` parameter to apply automatic version history limit on those file types in new document libraries on the site:`Set-SPOSite -Identity $siteUrl``-EnableAutoExpirationVersionTrim $false``-MajorVersionLimit <delete major versions exceeding limit>``-MajorWithMinorVersionsLimit <number of major versions for which all minor versions will be kept>``-ExpireVersionsAfterDays 0``-ApplyToNewDocumentLibraries``-FileTypesForVersionExpiration @("<file type 1>", "<file type 2>")`Append `-ApplyToExistingDocumentLibraries` to apply only to existing document libraries on a site:`Set-SPOSite -Identity $siteUrl``-EnableAutoExpirationVersionTrim $false``-MajorVersionLimit <delete major versions exceeding limit>``-MajorWithMinorVersionsLimit <number of major versions for which all minor versions will be kept>``-ExpireVersionsAfterDays 0``-ApplyToExistingDocumentLibraries` |
| Clear the file type version history limits set on a site for new document libraries created on the site. | `Set-SPOSite -Identity $siteUrl``-RemoveVersionExpirationFileTypeOverride @("<file type 1>", "<file type 2>")``-ApplyToNewDocumentLibraries` |
| Clear the existing version history limits set on a site and inherit Organization version limits on new document libraries created on the site. | `Set-SPOSite -Identity $siteUrl -InheritVersionPolicyFromTenant` |
| Cancel in progress update job | `Remove-SPOSiteVersionPolicyJob -Identity $siteUrl` |
| Start a sync job that updates all document libraries' version history limits to the same as the site | To sync all parts of the version history limit: `New-SPOSiteManageVersionPolicyJob -Identity $siteUrl -SyncListPolicy`Append `-ExcludeDefaultPolicy` to not sync the default version history limits: `New-SPOSiteManageVersionPolicyJob -Identity $siteUrl -SyncListPolicy -ExcludeDefaultPolicy`Supply `-FileTypes` with an array of file types to only sync the selection of file type version history limits: `New-SPOSiteManageVersionPolicyJob -Identity $siteUrl -SyncListPolicy -FileTypes @('<file type 1>', '<file type 2>')`Supply `-FileTypes` with an empty array to only sync the default version history limits: `New-SPOSiteManageVersionPolicyJob -Identity $siteUrl -SyncListPolicy -FileTypes @()` |
| Cancel in progress sync job | `Remove-SPOSiteManageVersionPolicyJobProgress $siteUrl` |

## Track progress of settings update on existing libraries on a site

Version limits on all new libraries created in the site are immediately applied. Settings on existing libraries are asynchronously updated using a background job. Run the following command **to track progress of settings update job**.

If it is an update job was started by `Set-SPOSite`:

```PowerShell
Get-SPOSiteVersionPolicyJobProgress -Identity $siteUrl
```

If it is a sync job started by `New-SPOSiteManageVersionPolicyJob`:

```powershell
Get-SPOSiteManageVersionPolicyJobProgress -Identity $siteUrl
```

The following table enumerates the various progress status that can be reported when attempting to update the version settings for existing libraries in a site collection:

| **Status** | **Description** |
| --- | --- |
| NoRequestFound | There are no requests on the site to set or update version settings on existing document libraries. |
| New | The update request is New and is not processed yet. |
| InProgress | The update request is processed and the settings update request is in progress. |
| CompleteSuccess | The update request is completed successfully. |
| CompleteWithFailure | The update request is completed, but setting update on some document libraries has failed. |

## Learn More:

- [Tutorial: Manage Version history limits for a Site, Library, or OneDrive account](tutorial-manage-version-limits)
- Manage Version history limits for a Site using [Set-SPOSite](/en-us/powershell/module/sharepoint-online/set-sposite)
- [File Type Version Limits](file-type-version-limits)
- Track progress of version settings update request for existing document libraries on a site using [Get-SPOSiteVersionPolicyJobProgress](/en-us/powershell/module/sharepoint-online/get-spositeversionpolicyjobprogress)
- Cancel further processing of version settings update on existing document libraries on the site collection using [Remove-SPOSiteVersionPolicyJob](/en-us/powershell/module/sharepoint-online/remove-spositeversionpolicyjob)
- Start a version settings sync request for existing document libraries on a site using [New-SPOSiteManageVersionPolicyJob](/en-us/powershell/module/sharepoint-online/new-spositemanageversionpolicyjob)
- Track progress of version settings sync request for existing document libraries on a site using [Get-SPOSiteManageVersionPolicyJobProgress](/en-us/powershell/module/sharepoint-online/get-spositemanageversionpolicyjobprogress)
- Cancel further processing of version settings sync on existing document libraries on the site using [Remove-SPOSiteManageVersionPolicyJob](/en-us/powershell/module/sharepoint-online/remove-spositemanageversionpolicyjob)