---
layout: Conceptual
title: Generate version storage usage report for a site - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/version-storage-report-site
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: rekamath
ms.author: ruihu
author: maggierui
manager: jtremper
ms.date: 2024-04-30T00:00:00.0000000Z
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
description: This article provides guidance on how to generate version storage use report for a site.
locale: en-us
document_id: c2f21ea6-6ad2-56f6-4ad1-14165d4af7f3
document_version_independent_id: 4b88a776-2796-e89e-9037-a8f38f562170
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/version-storage-report-site.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: version-storage-report-site
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/version-storage-report-site.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 4f4fa308-90ea-d37e-1ef8-996d89f00c0e
---

# Generate version storage usage report for a site - SharePoint in Microsoft 365 | Microsoft Learn

As a SharePoint admin in Microsoft 365, you can request an inventory of the versions on a site, library, or file, which can be used for various scenarios:

- Review current version storage used by existing versions.
- Understand how a version limit impacts new versions by applying the desired limits on existing versions before configuring limits.
- Analyze the impact of trimming existing versions before scheduling a trim job.

Note

Additional reporting options are available with [Microsoft Graph Data Connect](/en-us/graph/data-connect-datasets#onedrive-and-sharepoint-online).

When you run the report, a background timer job is queued to generate a CSV file of every file version on a given SharePoint site. The CSV file is saved to the location of your choice on the site. If you don't want site members to see the report, consider creating a folder with different permissions where only site owners can access the report.

Important

The file version report generation job completes asynchronously over the next few days. The time it takes for the report to complete depends on the size of your library or site. For smaller sites or libraries, it takes over 24 hours to complete. For larger ones, it takes a few days to complete.

While the job is being processed, you can see the report file being gradually populated. Do not update the file during this time. It will cause the job to fail. Check the progress of the report generation to confirm that the report is fully populated and ready to process.

If you wish to cancel an in-progress report generation, you may simply delete the report file.

## Report format

The file version expiration report is in Comma-Separated Values (CSV) format. Each row corresponds to a file version and it contains the following columns:

| **File Version Identifiers:** | Description |
| --- | --- |
| `WebId` | The unique identifier of the web and is a compact column ^1^. |
| `DocId` | The unique identifier of the document and is a compact column. |
| `MajorVersion` | The major version number of the file version. |
| `MinorVersion` | The minor version number of the file version. |

| **File Version Information:** | Description |
| --- | --- |
| `WebUrl` | The SharePoint Url to the web and is a compact column. |
| `FileUrl` | The web relative Url to the file and is a compact column. |
| `Size` | The size of the version in bytes. |
| `ModifiedBy_UserId` | The identifier of the user who created this version and is a compact column. |
| `ModifiedBy_UserDisplayName` | The display name of the user who created this version and is a compact column. |
| `LastModifiedDate` | The time when the version was last modified. |
| `SnapshotDate` | The time when the version became a historical version. |
| `IsSnapshotDateEstimated` | If this identifier is set to true, then the `SnapshotDate` is a best-effort estimation. The `SnapshotDate` might be estimated if the version was snapshot before January 1, 2023. |

| **Expiration Schedule information:** | Description |
| --- | --- |
| `CurrentExpirationDate` | Time when the version will expire as it currently stands. |
| `AutomaticPolicyExpirationDate` | Time when the version would be expiring if an automatic expiration policy were to be retroactively applied, estimated on a best-effort basis. |
| `TargetExpirationDate` | Is populated to the same value as `CurrentExpirationDate`. This column is useful for any What-If analysis and batch-updating the expiration dates. |

^1^ Compact columns are columns that won't repeat values if two consecutive rows have the same value. It puts empty string for the repeated records. The header for these columns have "Compact" postfix.

## How to generate site version storage usage report for site, OneDrive or library

Follow these steps to manage version history limits for a site by using PowerShell.

1. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    Note

    If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall **SharePoint Online Management Shell**.
2. Connect to SharePoint as a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
3. Run one of the following commands to generate a version storage usage report:

| **Action** | **PowerShell Command** |
| --- | --- |
| Generate a version storage usage report for a site or OneDrive account | `New-SPOSiteFileVersionExpirationReportJob -Identity $siteUrl -ReportUrl $reportUrl` |
| Track progress of the job to generate report for a site or OneDrive account | `Get-SPOSiteFileVersionExpirationReportJobProgress -Identity $siteUrl -ReportUrl $reportUrl` |
| Generate a version storage usage report for a library | `New-SPOListFileVersionExpirationReportJob -Site $siteUrl -List $libName -ReportUrl $reportUrl` |
| Track progress of the job to generate report for a library | `Get-SPOListFileVersionExpirationReportJobProgress -Site $siteUrl -List $libName -ReportUrl $reportUrl` |

## Learn More

1. [Tutorial: Generate Version Usage Report](tutorial-generate-version-usage-report)
2. [Tutorial: Run 'What-If' Analysis](tutorial-run-what-if-analysis)