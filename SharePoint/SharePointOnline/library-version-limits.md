---
layout: Conceptual
title: Set version limits for a document library - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/library-version-limits
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
ms.subservice: libraries
ms.localizationpriority: medium
search.appverid:
- SPO160
- SPS150
- MET150
description: This article provides guidance on how admins can set version limits for a document library.
locale: en-us
document_id: c8cae62d-15ac-7206-5b90-feeaa5a19e83
document_version_independent_id: e6a6dfe7-b449-6a13-0a90-30ff84dc033c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/library-version-limits.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: library-version-limits
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/library-version-limits.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 6f8fcd3c-e75f-8ea1-a3b3-d133db99741f
---

# Set version limits for a document library - SharePoint in Microsoft 365 | Microsoft Learn

The default version history limits for new document libraries are set by either the organization-level limits or the site-level limits. If the site has its own version history limit, it means the site breaks inheritance from the organization. However, to meet specific content requirements, site admins can decide to [configure versioning for a library](https://support.microsoft.com/en-us/office/enable-and-configure-versioning-for-a-list-or-library-1555d642-23ee-446a-990a-bcab618c7a37).

Here's a summary of the expected behavior when document libraries version expiration or count limits are updated:

- **When library level version expiration setting is updated**, the new expiration limit is applied to newly created versions only. Take an example of a library with version expiration settings updated from **Never Expire** to **Expire after six months**. New version created is set to expire after six months with no impact on versions that is already created.
- **When library level count limits are updated**, if existing versions exceed the new count limit, then those versions are gradually trimmed when the file is updated. Consider a library where the version count limit is initially set to 500 versions but is later reduced to 300 versions. In this scenario, if there's a file with 500 versions, each time a user updates the file, the system gradually purges the oldest 20 versions with each new version creation until the total number of versions aligns with the updated limit of 300. It's crucial to note that when count limits are lowered, the process of version deletion occurs gradually, with up to 20 versions being removed for every new version created.

[![Screenshot of overwrite version history.](sharepointonline/media/version-history/overright-version-history-limits-document-library.png)](sharepointonline/media/version-history/overright-version-history-limits-document-library.png#lightbox)

## Manage version history limits for a library using PowerShell

Follow these steps to manage version history limits for a site by using PowerShell.

1. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    Note

    If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall **SharePoint Online Management Shell**.
2. Connect to SharePoint as a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
3. Run one of the following commands to manage version history limits on a library:

    | **Action** | **PowerShell Command** |
    | --- | --- |
    | View version history limits set on a library | `Get-SPOListVersionPolicy -Site $siteUrl -List $libName` |
    | Set Automatic version history limits on a library | To set the default version history limit to automatic: `Set-SPOListVersionPolicy -Site $siteUrl -List $libName -EnableAutoExpirationVersionTrim $true`Supply `-FileTypes` parameter with an array of file types to set their version history limit to automatic: `Set-SPOListVersionPolicy -Site $siteUrl -List $libName -EnableAutoExpirationVersionTrim $true -FileTypes @("file type 1", "file type 2")` |
    | Set Manual limits with count and time parameters on a library | To set Manual limits for default version history limit with count and time parameters: `Set-SPOListVersionPolicy -Site $siteUrl -List $libName``-EnableAutoExpirationVersionTrim $false``-MajorVersionLimit <delete major versions exceeding limit>``-MajorWithMinorVersionsLimit <number of major versions for which all minor versions will be kept>``-ExpireVersionsAfterDays <delete versions exceeding time limit set in days>`Supply `-FileTypes` parameter with an array of file types to set their version history limit to Manual limits with count and time parameters: `Set-SPOListVersionPolicy -Site $siteUrl -List $libName``-EnableAutoExpirationVersionTrim $false``-MajorVersionLimit <delete major versions exceeding limit>``-ExpireVersionsAfterDays <delete versions exceeding time limit set in days>``-FileTypes @("file type 1", "file type 2")` |
    | Set Manual limits with count with no expiration limit on a library | To set Manual limits for default version history limit with count parameter only: `Set-SPOListVersionPolicy -Site $siteUrl -List $libName``-EnableAutoExpirationVersionTrim $false``-MajorVersionLimit <delete major versions exceeding limit>``-MajorWithMinorVersionsLimit <number of major versions for which all minor versions will be kept>``-ExpireVersionsAfterDays 0`Supply `-FileTypes` parameter with an array of file types to set their version history limit to Manual limits with count parameter only: `Set-SPOListVersionPolicy -Site $siteUrl -List $libName``-EnableAutoExpirationVersionTrim $false``-MajorVersionLimit <delete major versions exceeding limit>``-ExpireVersionsAfterDays 0``-FileTypes @("file type 1", "file type 2")` |
    | Sync the library version history limits to its parent site | To fully sync the version history limits: `Set-SPOListVersionPolicy -Site $siteUrl -List $libName -Sync` Append `-ExcludeDefaultPolicy` to sync only the file type version history limits and exclude the default: `Set-SPOListVersionPolicy -Site $siteUrl -List $libName -Sync -ExcludeDefaultPolicy` Supply an array to the `-FileTypes` parameter to sync the select file type version history limits: `Set-SPOListVersionPolicy -Site $siteUrl -List $libName -Sync -FileTypes @("<file type 1>", "<file type 2>")` Supply an empty array to the `-FileTypes` parameter to sync only the default version history limits: `Set-SPOListVersionPolicy -Site $siteUrl -List $libName -Sync -FileTypes @()` |

## Learn More

For more information, check out the following resources:

- [File Type Version Limits](file-type-version-limits)
- View version history limits for a library using [Set-SPOListVersionPolicy](/en-us/powershell/module/sharepoint-online/get-spolistversionpolicy)
- Manage version history limits for a library using [Set-SPOListVersionPolicy](/en-us/powershell/module/sharepoint-online/set-spolistversionpolicy)