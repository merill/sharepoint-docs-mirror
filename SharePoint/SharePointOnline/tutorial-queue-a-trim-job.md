---
layout: Conceptual
title: 'Tutorial: Queue a trim job - SharePoint in Microsoft 365 | Microsoft Learn'
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/tutorial-queue-a-trim-job
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: rekamath
ms.author: ruihu
author: maggierui
manager: jtemper
ms.date: 2024-10-03T00:00:00.0000000Z
audience: Admin
f1.keywords:
- NOCSH
ms.topic: tutorial
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
search.appverid:
- SPO160
- SPS150
- MET150
description: This article provides guidance on how to queue a trim job for a site or document library.
locale: en-us
document_id: aaf00d42-2221-cb18-ea51-f1ba08784824
document_version_independent_id: 8a87ccd6-bf4e-151f-b5a6-acfad4d6577b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/tutorial-queue-a-trim-job.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: tutorial-queue-a-trim-job
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/tutorial-queue-a-trim-job.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/86a4b315-a9f1-4577-b985-6fb0e0e67420
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/96ac410d-d052-4707-8007-df31dd0fe041
platformId: 4c715f5c-3eec-f18b-fc19-62e445acd7c0
---

# Tutorial: Queue a trim job - SharePoint in Microsoft 365 | Microsoft Learn

In this tutorial, you'll learn how to trim existing versions from a site or library by queuing a trim job using PowerShell. You'll learn how to:

- Queue a job to trim versions from a site.
- Queue a job to trim versions from a library.
- Check progress of your trim job.
- Stop an in-progress trim job.

## Before you begin

Versions deleted by a trim job are permanently deleted and can't be recovered from the recycle bin. We recommend you prepare by performing the following actions:

- Review your **organization’s recovery objectives** and **version storage usage quota targets** to help determine the trim action and scope needed to meet your requirements.
- If needed, [run an impact analysis](tutorial-run-what-if-analysis) to understand the trimming impact.
- Determine the **scope of** version deletion. You can create jobs to delete old file versions for all document libraries in a site or for a specific document library.
- Determine the **trim mode** you want to apply on existing versions. You can choose to delete based on version age, count limit, or based on the automatic algorithm.

## Queue a job to trim versions on site

You can queue a job to trim versions for all document libraries in the site collection using the `New-SPOSiteFileVersionBatchDeleteJob` PowerShell command.

- Use the `<DeleteBeforeDays>` parameter to specify the age criteria you wish to apply for deleting versions. Versions older than the specified days are deleted asynchronously in batches in the upcoming days.
- Use the `<MajorVersionLimit>` to specify the count limit of major versions to store. Oldest versions exceeding the specified count are deleted asynchronously in batches in the upcoming days.
- Use the `<Automatic>` parameter to apply Automatic setting trimming logic on existing file versions.

### Example: Queue a job to trim versions based on age for all libraries on a site

In the following example, the job is queued to trim versions that are older than 180 days for all document libraries in the site collection `https://contoso.sharepoint.com/sites/site1`.

```PowerShell
New-SPOSiteFileVersionBatchDeleteJob -Identity https://contoso.sharepoint.com/sites/site1 -DeleteBeforeDays 180 
```

### Example: Queue a job to trim oldest versions exceeding the specified count limit on a site

In the example below, the job is queued to trim oldest versions that exceed 100 major version count limit for all document libraries in the site collection `https://contoso.sharepoint.com/sites/site1`.

```PowerShell
New-SPOSiteFileVersionBatchDeleteJob -Identity https://contoso.sharepoint.com/sites/site1 -MajorVersionLimit 100 -MajorWithMinorVersionsLimit 0
```

### Example: Queue a job to trim versions based on the automatic logic on a site

In the example below, the job is queued to trim versions based on the Automatic algorithm for all document libraries in the site collection `https://contoso.sharepoint.com/sites/site1`.

```PowerShell
New-SPOSiteFileVersionBatchDeleteJob -Identity https://contoso.sharepoint.com/sites/site1 -Automatic 
```

## Queue a job to trim versions on a document library

You can queue a job to trim versions from a particular document library in the site collection using the `New-SPOListFileVersionBatchDeleteJob` PowerShell command.

- Use the `<DeleteBeforeDays>` parameter to specify the age criteria you wish to apply for deleting versions. Versions older than the specified days are asynchronously in batches in the upcoming days.
- Use the `<MajorVersionLimit>` to specify the count limit of major versions to store. Oldest versions exceeding the specified count are deleted asynchronously in batches in the upcoming days.
- Use the `<Automatic>` parameter to apply Automatic setting trimming logic on existing file versions.

### Example: Queue a job to trim versions based on age on a single library on a site

To delete versions that are older than 360 days in document library 'Documents' in the site collection `https://contoso.sharepoint.com`.

```PowerShell
New-SPOListFileVersionBatchDeleteJob -Site https://contoso.sharepoint.com -List "Documents" -DeleteBeforeDays 360 
```

## Track progress of a trim job

You can track progress of the trim job using the `Get-SPOSiteFileVersionBatchDeleteJobProgress` cmdlet.

In the following example, the cmdlet reports the progress of the trim job for `https://contoso.sharepoint.com/sites/site1`

```PowerShell
Get-SPOSiteFileVersionBatchDeleteJobProgress -Identity https://contoso.sharepoint.com/sites/site1
```

## Stop an in-progress trim job

If needed, you can cancel an in-progress trim job. Once the cmdlet executes successfully, the in-progress job is stopped and no further deletions happen.

Note

Stopping a trim job doesn't revert versions that have already been deleted.

### Example: Stop a site trim job

To stop an in-progress trim job from additional version trimming on the site collection `https://contoso.sharepoint.com/sites/site1`:

```PowerShell
Remove-SPOSiteFileVersionBatchDeleteJob -Identity https://contoso.sharepoint.com/sites/site1
```

### Example: Stop a library trim job

To stop an in-progress trim job from additional version trimming in document library 'Documents' in site collection `https://contoso.sharepoint.com/sites/site1`:

```PowerShell
Remove-SPOListFileVersionBatchDeleteJob -Site https://contoso.sharepoint.com/sites/site1 -List "Documents"
```