---
layout: Conceptual
title: Set version limits on OneDrive using PowerShell - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/version-limits-onedrive-ps
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
description: This article provides guidance on how an admin can set the version limits on OneDrive for a specific user using PowerShell.
locale: en-us
document_id: 04c459ce-8b4d-3cc5-3899-df4ee8ca92b1
document_version_independent_id: 8b4dde23-6100-7975-38d5-ba41fb1e005e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/version-limits-onedrive-ps.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: version-limits-onedrive-ps
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/version-limits-onedrive-ps.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
platformId: 0ef27eb6-db24-dfb1-3ab1-f1919d973d9e
---

# Set version limits on OneDrive using PowerShell - SharePoint in Microsoft 365 | Microsoft Learn

By default, organization version history settings are applied to all new OneDrive accounts. As a SharePoint admin in Microsoft 365, you can set the version limits on OneDrive storage for a specific user.

Follow these steps to manage Version history limits for a site by using PowerShell.

1. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    Note

    If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall **SharePoint Online Management Shell**.
2. Connect to SharePoint as a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
3. Run one of the following commands to manage Version history limits for a specific user:

| **Action** | **PowerShell Command** |
| --- | --- |
| View the version history limits set for a user | Get-SPOSite -Identity $siteUrl | fl Url, EnableAutoExpirationVersionTrim, ExpireVersionsAfterDays, MajorVersionLimit |
| Set automatic Version history limits for a user | `Set-SPOSite -Identity $siteUrl -EnableAutoExpirationVersionTrim $true` |
| Set manual limits with count and time parameters for a user | `Set-SPOSite -Identity $siteUrl``-EnableAutoExpirationVersionTrim $false``-MajorVersionLimit <delete major versions exceeding limit>``-MajorWithMinorVersionsLimit <number of major versions for which all minor versions will be kept>``-ExpireVersionsAfterDays <delete versions exceeding time limit set in days>` |
| Set manual limits with count with no expiration limit for a user | To set manual limits with count limits set the `-ExpireVersionsAfterDays parameter` to 0:`Set-SPOSite -Identity $siteUrl``-EnableAutoExpirationVersionTrim $false``-MajorVersionLimit  <delete major versions exceeding limit>``-MajorWithMinorVersionsLimit <number of major versions for which all minor versions will be kept>``-ExpireVersionsAfterDays 0` |
| Clear the existing Version history limits for a user**Note:** Clearing a setting for a user applies to new versions created on files stored on the user’s OneDrive account and doesn't trim existing versions. | `Remove-SPOSiteVersionPolicyJob -Identity $siteUrl` |

## Learn More

[Change a specific user's OneDrive storage space](change-user-storage)