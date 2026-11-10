---
layout: Conceptual
title: Trim existing versions - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/trim-versions
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: rekamath
ms.author: ruihu
author: maggierui
manager: jtremper
ms.date: 2026-10-30T00:00:00.0000000Z
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
description: Learn how to reduce version storage consumption by analyzing, managing, and trimming file versions at the library, site, or tenant level.
ai-usage: ai-assisted
locale: en-us
document_id: 083d3139-8c5c-1fe3-1479-cec825bcb0d7
document_version_independent_id: e0851805-41b7-8c8a-5d6a-83f79fa48c03
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/trim-versions.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: trim-versions
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/trim-versions.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 142be7e9-26ce-fd2e-55c7-3e6fb4118e35
---

# Trim existing versions - SharePoint in Microsoft 365 | Microsoft Learn

Learn how to reduce version storage consumption by analyzing, managing, and trimming file versions at the library, site, or tenant level.

Caution

Versions deleted by using trimming jobs are permanently deleted. This deletion workflow bypasses the normal recycle bin retention, and deleted versions can't be recovered unless the data was previously backed up by using [Microsoft 365 Backup](/en-us/microsoft-365/backup/backup-overview?view=o365-worldwide&amp;preserve-view=true) or a similar backup solution. To prevent unwanted data loss, run a [What-if analysis](tutorial-run-what-if-analysis) before trimming activity.

As a SharePoint Administrator in Microsoft 365, you can queue a job to trim existing versions to reduce the version storage footprint across your organization. Trimming can be applied at different scopes:

- **Site, library, or OneDrive level** — Target specific sites, document libraries, or OneDrive user accounts.
- **Tenant level** — Apply your tenant-level version policy across all sites in one operation.

Version availability is critical for recovery scenarios like undoing unwanted changes. Before trimming at any scope, carefully evaluate your recovery objectives and review the projected impact.

## Trim existing versions from site, library, or OneDrive

You can queue a job to trim existing versions on a site, library, or OneDrive user account to reduce the version storage footprint of your site. You can also align existing version storage with updated version history limits by scheduling a job to trim existing versions.

| **Phase** | **Recommended Actions** |
| --- | --- |
| Prepare | **Evaluate your recovery objectives and target version storage use:** Determine the right trim mode and trim scope that you need to meet your organization's recovery objectives. **Review Impact:** Before committing to trim existing versions, you have the option to review the impact of the purge action by running a 'What-if' analysis operation of the selected trim mode on the specified scope. |
| Queue Job | Once you're ready to commit to a trim job, queue a version trimming job to asynchronously delete versions that match the criteria specified in the trim mode within a site, library, or OneDrive user account. |
| Track Progress | Track the progress of all queued jobs to review the progress made in trimming versions. |

Note

Trim jobs are background jobs that factors such as the volume of file versions to evaluate, service health, and other jobs being processed on the farm influence. They're also subject to off-peak hour processing logic. You can always track the progress of a trim job.

### Review impact by running What-if analysis

Before you trim existing versions, review the impact of the purge action by running a What-if analysis operation. Running a What-if operation follows these steps:

- **Generate a version storage usage report for a site or library**: Use this report for version storage analytics and to understand the impact of different trimming settings.
- **Run What-if analysis**: Set different trimming modes to preview the changes and analyze the storage savings impact of applying one of the trimming modes to the version storage report CSV file.

Important

Depending on the size of the site or library, the job can take a few days to complete. Check the progress of the job until the status returns as "completed".

### Version trim modes

Version trimming workflows allow you to select and apply one of the trimming modes for queuing a trim job on a site, document library, or OneDrive account.

#### Automatic trim mode (recommended)

The automatic trim mode applies the Automatic algorithm to delete existing versions. Depending on the version age, the job permanently deletes versions or sets expiration time according to the automatic version storage algorithm.

To learn more about automatic trim mode, see [Understand version storage under Automatic limits](/en-us/sharepoint/plan-version-storage#understand-version-storage-under-automatic-limits).

#### Manual expiration trim mode

The manual expiration trim mode evaluates the age of versions and deletes versions that match the expiration criteria.

**Example:** In the following example, a trim job is queued to trim versions older than 60 days. On August 31, the job is picked up and it starts permanently deleting versions older than 60 days as of August 31.

Important

**Known limitations of manual expiration trim mode:**

- The manual expiration trim mode doesn't delete versions created in the last 30 days. This limitation means your input can't be less than 30 days.
- The manual expiration trim mode always deletes all versions that were created before January 1, 2023. If you want to trim versions, you can't keep any older versions created before January 1, 2023. This limitation means the value you use for the `DeleteBeforeDays` parameter should result in a date after January 1, 2023.

#### Manual count limit trim mode

The manual count limit trim mode deletes the oldest versions that exceed the specified count limit.

**Example:** In the following example, a trim job is queued to delete versions that exceed 50 major version counts. On August 31, the job starts permanently deleting older versions that exceed the 50 major version count limit as of August 31.

Tip

You can run the impact analysis of either applying the Manual Count, Expire, or Automatic trim mode to understand the version delete impact under each mode.

### Queue trim job and track progress

The version trimming workflow uses a job to asynchronously delete versions that match the criteria you specify in the trim mode.

To queue the trim job, determine the scope for version deletion and choose the trim mode to set the criteria for deleting existing versions. You can delete old file versions based on version age, count limits, or an automatic algorithm for all document libraries in a site or for a specific document library.

When you're ready to trim, queue the job to asynchronously delete versions that match the trim mode criteria. You can monitor the progress of committed trim jobs to keep track of the deletion progress.

Note

To learn more about how version trimming works on versions that are subject to a retention policy or an eDiscovery hold, see [FAQs](/en-us/sharepoint/faqs-for-versions).

### Trim existing versions by using PowerShell

Follow these steps to trim existing versions by using PowerShell.

1. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    Note

    If you installed a previous version of the SharePoint Online Management Shell, go to **Add or Remove programs** and uninstall **SharePoint Online Management Shell**.
2. Connect to SharePoint as a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
3. Run one of the following commands to trim the existing versions:

    | **Action** | **PowerShell Command** |
    | --- | --- |
    | Queue a trim job to expire versions | **Expire versions on a site:**`New-SPOSiteFileVersionBatchDeleteJob -Identity $siteUrl -DeleteBeforeDays <days>`**Expire versions on a library:**`New-SPOListFileVersionBatchDeleteJob -Site $siteUrl -list $libName -DeleteBeforeDays <days>` |
    | Queue a trim job to delete versions exceeding the specified count limit | **Delete versions exceeding count limits from a site:**`New-SPOSiteFileVersionBatchDeleteJob -Identity $siteUrl -MajorVersionLimit <delete major versions exceeding limit> -MajorWithMinorVersionsLimit <number of major versions for which all minor versions will be kept>`**Delete versions exceeding count limits from a library:**`New-SPOListFileVersionBatchDeleteJob -Site $siteUrl -list $libName -MajorVersionLimit <delete major versions exceeding limit> -MajorWithMinorVersionsLimit <number of major versions for which all minor versions will be kept>` |
    | Queue trim job to delete versions using the estimated automatic trimming algorithm | **Apply automatic logic to trim existing versions from a Site:**`New-SPOSiteFileVersionBatchDeleteJob -Identity $siteUrl -Automatic`**Apply automatic logic to trim existing versions from a library:**`New-SPOListFileVersionBatchDeleteJob -Site $siteUrl -List $libName -Automatic` |
    | Queue site-level trim job to delete versions using the version history limit of individual document libraries | **Sync all document libraries' version history limit to the same as the site and trim existing versions from the site:**`New-SPOSiteManageVersionPolicyJob -Identity $siteUrl -SyncListPolicy -TrimUseListPolicy` |
    | Queue library-level trim job to delete versions using its version history limits | **Trim existing versions from the library using its version history limits:**`New-SPOListFileVersionBatchDeleteJob -Site $siteUrl -List $libName -TrimUseListPolicy` |
    | Stop further processing of an in-progress trim job | **To stop processing an in-progress site level trim job:**`Remove-SPOSiteFileVersionBatchDeleteJob -Identity $siteUrl` or `Remove-SPOSiteManageVersionPolicyJob -Identity $siteUrl`**To stop processing an in-progress library level trim job:**`Remove-SPOListFileVersionBatchDeleteJob -Site $siteUrl -List $libName` |
    | Get the status for a file version trimming job | **To get status of a site level trimming job:**`Get-SPOSiteFileVersionBatchDeleteJobProgress -Identity $siteUrl` or `Get-SPOSiteManageVersionPolicyJobProgress -Identity $siteUrl`**To get status of a library level trimming job:**`Get-SPOListFileVersionBatchDeleteJobProgress -Site $siteUrl -List $libName` |

## Trim existing versions at the tenant level

Note

Tenant-level version trimming is currently in public preview. This feature might change based on feedback, including the addition of throttling limits on the number of jobs you can run within a specific time period.

Tenant admins can use tenant-level operations to start a file version trimming job across all sites in a tenant, update document library version policies to match the tenant policy, and estimate the storage impact of trimming by using what-if analysis.

Tenant-level file version trimming cmdlets let you:

- Update all document library version policies to match the tenant policy.
- Trim existing versions based on that policy.
- Track progress and delete the tenant-level job.

To help you understand trimming impact, use additional cmdlets to run fast, synchronous what-if analysis queries after an initial asynchronous data collection job.

Caution

Versions you delete by using trimming jobs are permanently deleted. This deletion workflow bypasses the normal recycle bin retention, and deleted versions can't be recovered unless the data was previously backed up by using [Microsoft 365 Backup](/en-us/microsoft-365/backup/backup-overview?view=o365-worldwide&amp;preserve-view=true) or a similar backup solution.

### Prerequisites and limitations

- Requires a **SharePoint Advanced Management license** or **Copilot license**.
- Only **one job is allowed per tenant** at a time.
- The following site types are excluded from processing:

    - Read-only sites
    - Locked sites
    - Archived sites
    - Sites with version policy broken inheritance
- If the tenant-level version policy changes while the job is in progress, the job applies the updated policy to remaining unprocessed sites. Sites already processed aren't re-evaluated.
- The tenant-level trim uses the version policy configured at the tenant level (Automatic, Manual Expiration, or Manual Count Limit). To understand these trim modes, see Version trim modes above.
- The what-if analysis returns impact data for both **SharePoint sites** and **OneDrive accounts**.
- If your tenant is **Multi-Geo**, run the what-if analysis and version trimming separately for each geo location.

### Recommended workflow

#### 1. Prerequisites

1. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).
2. Connect to SharePoint as a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
3. Confirm your tenant-level version policy by running:

    ```powershell
    Get-SPOTenantVersionPolicy
    ```

    You can also use `Get-SPOTenant` and check the `EnableAutoExpirationVersionTrim`, `MajorVersionLimit`, `ExpireVersionsAfterDays`, and `VersionPolicyFileTypeOverride` properties.

#### 2. (Optional but strongly recommended) What-If Analysis

Before committing to a trim, you can estimate the impact of your tenant version policy without deleting any versions:

1. **Run a data collection job** to gather version data across all sites:

    ```powershell
    New-SPOTenantApplyFileVersionPolicyJob -CollectVersionData
    ```
2. **Monitor the data collection job** until it completes:

    ```powershell
    Get-SPOTenantApplyFileVersionPolicyJobProgress
    ```
3. **Run what-if queries** to estimate the impact of applying your policy:

    ```powershell
    Get-SPOTenantApplyFileVersionPolicyJobImpact
    ```

    You can run multiple what-if queries with different policy options using `Get-SPOVersionPolicyWithChanges` to create modified policy objects for comparison.
4. Review the projected impact and choose a desired version policy.

    Note

    The projected impact includes both **SharePoint sites** and **OneDrive accounts**.

#### 3. Trim existing versions and update document library policies

Once you confirm your tenant version policy and review the projected impact:

1. **Run the trim job** with desired options:

    ```powershell
    # Trim existing versions AND set version policy on all libraries
    New-SPOTenantApplyFileVersionPolicyJob -TrimVersions -SetVersionPolicy
    
    # Or trim only (without updating library policies)
    New-SPOTenantApplyFileVersionPolicyJob -TrimVersions
    
    # Or set policy only (without trimming existing versions)
    New-SPOTenantApplyFileVersionPolicyJob -SetVersionPolicy
    
    # Or specify a custom version policy object
    $policy = Get-SPOVersionPolicyWithChanges -VersionPolicy (Get-SPOTenantVersionPolicy) -EnableAutoExpirationVersionTrim $true
    New-SPOTenantApplyFileVersionPolicyJob -VersionPolicy $policy -TrimVersions
    ```
2. **Monitor and validate the trim job:**

    ```powershell
    Get-SPOTenantApplyFileVersionPolicyJobProgress
    ```
3. **Cancel an in-progress job** (if needed):

    ```powershell
    Remove-SPOTenantApplyFileVersionPolicyJob
    ```

    Note

    Once the cmdlet executes successfully, all new asynchronous version deletion stops. Canceling a trim job doesn't impact versions that were permanently deleted while the job was in progress.

### Tenant-level PowerShell cmdlet reference

| **Action** | **PowerShell Cmdlet** | **Reference** |
| --- | --- | --- |
| Collect version data (prerequisite for what-if) | `New-SPOTenantApplyFileVersionPolicyJob -CollectVersionData` | [New-SPOTenantApplyFileVersionPolicyJob](/en-us/powershell/module/microsoft.online.sharepoint.powershell/new-spotenantapplyfileversionpolicyjob?view=sharepoint-ps&amp;preserve-view=true) |
| Estimate impact (what-if query) | `Get-SPOTenantApplyFileVersionPolicyJobImpact` | [Get-SPOTenantApplyFileVersionPolicyJobImpact](/en-us/powershell/module/microsoft.online.sharepoint.powershell/get-spotenantapplyfileversionpolicyjobimpact?view=sharepoint-ps&amp;preserve-view=true) |
| Trim existing versions using current tenant policy | `New-SPOTenantApplyFileVersionPolicyJob -TrimVersions` | [New-SPOTenantApplyFileVersionPolicyJob](/en-us/powershell/module/microsoft.online.sharepoint.powershell/new-spotenantapplyfileversionpolicyjob?view=sharepoint-ps&amp;preserve-view=true) |
| Set version policy on all document libraries | `New-SPOTenantApplyFileVersionPolicyJob -SetVersionPolicy` | [New-SPOTenantApplyFileVersionPolicyJob](/en-us/powershell/module/microsoft.online.sharepoint.powershell/new-spotenantapplyfileversionpolicyjob?view=sharepoint-ps&amp;preserve-view=true) |
| Trim + set policy | `New-SPOTenantApplyFileVersionPolicyJob -TrimVersions -SetVersionPolicy` | [New-SPOTenantApplyFileVersionPolicyJob](/en-us/powershell/module/microsoft.online.sharepoint.powershell/new-spotenantapplyfileversionpolicyjob?view=sharepoint-ps&amp;preserve-view=true) |
| Trim with a specific policy object | `New-SPOTenantApplyFileVersionPolicyJob -VersionPolicy $policy -TrimVersions` | [New-SPOTenantApplyFileVersionPolicyJob](/en-us/powershell/module/microsoft.online.sharepoint.powershell/new-spotenantapplyfileversionpolicyjob?view=sharepoint-ps&amp;preserve-view=true) |
| Track job progress | `Get-SPOTenantApplyFileVersionPolicyJobProgress` | [Get-SPOTenantApplyFileVersionPolicyJobProgress](/en-us/powershell/module/microsoft.online.sharepoint.powershell/get-spotenantapplyfileversionpolicyjobprogress?view=sharepoint-ps&amp;preserve-view=true) |
| Cancel an in-progress job | `Remove-SPOTenantApplyFileVersionPolicyJob` | [Remove-SPOTenantApplyFileVersionPolicyJob](/en-us/powershell/module/microsoft.online.sharepoint.powershell/remove-spotenantapplyfileversionpolicyjob?view=sharepoint-ps&amp;preserve-view=true) |
| Get current tenant version policy | `Get-SPOTenantVersionPolicy` | [Get-SPOTenantVersionPolicy](/en-us/powershell/module/microsoft.online.sharepoint.powershell/get-spotenantversionpolicy?view=sharepoint-ps&amp;preserve-view=true) |
| Create a modified policy object locally | `Get-SPOVersionPolicyWithChanges` | [Get-SPOVersionPolicyWithChanges](/en-us/powershell/module/microsoft.online.sharepoint.powershell/get-spoversionpolicywithchanges?view=sharepoint-ps&amp;preserve-view=true) |

## Related information

- [Tutorial: Generate Version Usage Report](tutorial-generate-version-usage-report)
- [Tutorial: Run 'What-If' analysis](tutorial-run-what-if-analysis)
- [Tutorial: Queue Trim Job](tutorial-queue-a-trim-job)
- [File Type Version Limits](file-type-version-limits)
- Start a version settings sync and trim request for existing document libraries on a site by using [New-SPOSiteManageVersionPolicyJob](/en-us/powershell/module/microsoft.online.sharepoint.powershell/new-spositemanageversionpolicyjob?view=sharepoint-ps&amp;preserve-view=true).
- Track progress of version settings sync and trim request for existing document libraries on a site by using [Get-SPOSiteManageVersionPolicyJobProgress](/en-us/powershell/module/microsoft.online.sharepoint.powershell/get-spositemanageversionpolicyjobprogress?view=sharepoint-ps&amp;preserve-view=true).
- Cancel further processing of version settings sync and trim on existing document libraries on the site by using [Remove-SPOSiteManageVersionPolicyJob](/en-us/powershell/module/microsoft.online.sharepoint.powershell/remove-spositemanageversionpolicyjob?view=sharepoint-ps&amp;preserve-view=true).
- Start a version trim request for a document library by using [New-SPOListFileVersionBatchDeleteJob](/en-us/powershell/module/microsoft.online.sharepoint.powershell/new-spolistfileversionbatchdeletejob?view=sharepoint-ps&amp;preserve-view=true).
- Track progress of a version trim request for a document library by using [Get-SPOListFileVersionBatchDeleteJobProgress](/en-us/powershell/module/microsoft.online.sharepoint.powershell/get-spolistfileversionbatchdeletejobprogress?view=sharepoint-ps&amp;preserve-view=true).
- Cancel further processing of a version trim for a document library by using [Remove-SPOListFileVersionBatchDeleteJob](/en-us/powershell/module/microsoft.online.sharepoint.powershell/remove-spolistfileversionbatchdeletejob?view=sharepoint-ps&amp;preserve-view=true).