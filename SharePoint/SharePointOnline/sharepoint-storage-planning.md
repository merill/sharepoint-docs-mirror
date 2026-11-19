---
layout: Conceptual
title: SharePoint storage management - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/sharepoint-storage-planning
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-11-18T00:00:00.0000000Z
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords: NOCSH
ms.topic: concept-article
ms.service: sharepoint-online
ms.subservice: platform
ms.localizationpriority: medium
ms.collection:
- Strat_OD_admin
- M365-collaboration
- essentials-get-started
ms.custom: intro-get-started
search.appverid: MET150
description: Plan SharePoint storage for your organization.
locale: en-us
document_id: fb2cad07-d52c-0c17-d124-2ea54c9afeea
document_version_independent_id: 497a49b2-e630-c147-5542-5d6f43a77b30
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/sharepoint-storage-planning.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: sharepoint-storage-planning
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/sharepoint-storage-planning.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: ff7b29d0-0a8b-f8d6-aa75-1695af8c126f
---

# SharePoint storage management - SharePoint in Microsoft 365 | Microsoft Learn

Manage your organization's SharePoint storage by understanding usage, keeping the content you need, and reducing unnecessary growth. This guide helps tenant administrators choose when to trim versions, archive inactive content, delete eligible content, or add capacity.

Start with storage usage to plan improvements, or use the steps in the following section if you need to free space now.

## Need to free storage now? Start here

1. **Protect capacity while you clean up.** If you're near or over quota, consider **Microsoft 365 SharePoint Storage (pay-as-you-go)** before starting cleanup work. It bills usage above the tenant quota while you reduce consumption. This solution allows you to address your cleanup effort at your own pace, and ensures you don't have to over-procure with a prepaid storage pack, since you'll only pay for what you use. If pay-as-you-go isn't available or suitable, review other tenant capacity options with your billing administrator. Review charges and prerequisites before enabling a service.
2. **Start with the biggest cleanup opportunity.**Identify what's using storage, then trim eligible versions or archive inactive content. If inactive content is the main contributor, prioritize archiving rather than trimming first. Delete only content that owners confirm is no longer needed and is eligible for deletion.
3. **Control future growth.** Establish version limits and lifecycle policies so cleanup becomes part of ongoing storage management.

**Capacity protection and cleanup work together.** Use pay-as-you-go to cover storage needs while cleanup is underway, then trim versions and archive inactive content to reduce active storage usage and help manage costs.

### Choose the action that matches your situation

| What you find | Start with | What to expect |
| --- | --- | --- |
| The tenant is near or over quota and cleanup will take time | Protect tenant capacity | Evaluate pay-as-you-go or additional allocated capacity before waiting for cleanup. Charges and eligibility requirements apply. |
| Older file versions use substantial storage | Trim existing versions | Reduce eligible version storage after processing. Trimmed versions aren't recoverable from the recycle bin. |
| Content is inactive but must be kept | Archive inactive content | Move eligible content out of active storage. Normal access requires reactivation, and Archive charges might apply. |
| Deleted items or unneeded content remain | Review deletion and recycle bins | Remove eligible content after checking recovery and compliance requirements. Deleting a visible file doesn't always release storage. |
| Content should be deleted after an approved period | Use retention policies to delete content | Automate eligible deletion across sites. Processing, recycle bins, and other retention requirements affect when space is released. |
| Retained content accounts for substantial usage | Review retention requirements | Identify storage that isn't currently reclaimable; coordinate with compliance owners. |
| Necessary active content exceeds available capacity after optimization | Increase tenant capacity | Support continued usage without removing needed content. Additional charges apply. |

You don't need to complete every action. Choose the options that best fit your organization's needs, whether that's freeing space, adding capacity, or managing future growth.

## Find what's using your storage

As your storage grows, understanding what drives that growth helps you identify areas that need attention. Explore trends with easy-to-read reports in the Microsoft 365 admin center, ask the SharePoint Admin Agent for insights, or use rich datasets in Microsoft Graph Data Connect (MGDC) for deeper analysis. Choose the approach that fits your needs. You don't need to use all three.

| Approach | Best for | Where to start |
| --- | --- | --- |
| **Existing admin center reports** | Reviewing tenant capacity, storage trends, and high-consumption sites without setting up a custom analysis | [SharePoint admin center](https://go.microsoft.com/fwlink/p/?linkid=2185219) and [Microsoft 365 usage reports](https://go.microsoft.com/fwlink/p/?linkid=2074756) |
| **SharePoint Admin Agent** | Asking storage questions in natural language and exploring the results | The agent's storage prompts below |
| **Microsoft Graph Data Connect (advanced)** | Building custom analysis across large site and file datasets | SharePoint datasets in Microsoft Graph Data Connect |

### Option 1: Use existing admin center reports

**Check tenant capacity and top sites.** In the [SharePoint admin center](https://go.microsoft.com/fwlink/p/?linkid=2185219), open [Active sites](https://go.microsoft.com/fwlink/p/?linkid=2185220). The storage bar shows usage across sites and the total storage for your subscription. For Multi-Geo organizations, it includes usage across geo locations. Review the sites consuming the most storage.

**Explore storage trends.** In the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), go to **Reports** &gt; [Usage](https://go.microsoft.com/fwlink/p/?linkid=2074756) &gt; **SharePoint** &gt; **Storage**. The SharePoint Storage report shows used, available, and allocated storage, growth trends, and optimization suggestions. See [View and interpret the SharePoint Storage report](/en-us/microsoft-365/admin/activity-reports/sharepoint-storage-reports?view=o365-worldwide) for help.

The SharePoint Storage report is available to non-Education tenants. Education tenants should use **Reports** &gt; [Storage](https://admin.microsoft.com/Adminportal/Home#/storagemanagement) and follow [Pooled storage management](/en-us/microsoft-365/education/guide/1-reference/pooled-storage-management).

Compare growth with known migrations or bulk uploads. Prioritize both large sites and sites whose consumption is increasing quickly.

For the sites you select, investigate Storage Metrics, version history, recycle bins, and retention requirements. Use these findings to distinguish total consumption from storage you can reclaim across the tenant.

Note

A library can show the size of current files, while storage reports also account for versions and other associated storage. Compare reports with the same scope and reporting time. SharePoint admin center storage figures can lag changes by 24-48 hours. The Microsoft 365 admin center's SharePoint Storage report refreshes every 48-72 hours. Background operations can take additional time.

### Option 2: Use the SharePoint Admin Agent

Use the SharePoint Admin Agent to understand storage usage and decide where to investigate next. Open it through Copilot in the SharePoint admin center, or follow [SharePoint Admin Agent access instructions](content-governance-agent).

The agent is available to eligible tenants through **SharePoint Advanced Management** or **at least one Microsoft Copilot license assigned to a user**. The licensed user doesn't need to be the administrator. See [licensing prerequisites](sharepoint-advanced-management-prerequisites).

#### Try it now

Enter one of these prompts:

1. Tenant storage overview
2. Analyze storage trend over the last six months
3. Compare active and archive storage growth
4. How much version storage is used across the tenant?
5. Which geo has the fastest storage growth? (\*)

(\*) The geo comparison is relevant to organizations using Multi-Geo. Review the scope and time period of the results before deciding what action to take.

#### Coming soon

The following agent prompts are planned and aren't part of the current "Try it now" experience:

1. How much storage could we save if we use the automatic version limit?
2. Which sites weren't modified in the last 180 days?
3. List sites using the most version storage

You don't need to wait for these agent prompts to preview storage opportunities. Use [version reports and what-if analysis](trim-versions) to estimate trimming savings. Both [inactive site policies](inactive-site-policy) and [inactive files policies](/en-us/microsoft-365/archive/manage-inactive-files?view=o365-worldwide) offer simulation modes to identify archive candidates and review their storage impact before enabling enforcement.

### Option 3: Use Microsoft Graph Data Connect for advanced analysis

Use [SharePoint datasets in Microsoft Graph Data Connect](https://aka.ms/SharePointData) for custom analysis across sites and files, such as comparing storage by site type, ownership, or version contribution. Review its setup, permissions, and billing requirements. For urgent help, start with existing reports or the agent rather than building a new data pipeline.

## Trim existing file versions

**Use this when:** Version history is a significant storage contributor and you don't need all older versions for recovery or compliance.

For an overview of version controls, see [Document library version history limits](document-library-version-history-limits). Follow [Trim existing versions](trim-versions) to choose the scope, estimate savings, and start a trimming job.

### Choose the trimming scope

| Scope | Use it to |
| --- | --- |
| **Tenant level** | Apply a version policy across eligible SharePoint sites and OneDrive accounts. Review the broad impact before starting. |
| **Site level** | Target selected sites with substantial version storage or start with a smaller pilot. You can also target a document library or an individual OneDrive account. |

Note

Tenant-level version trimming is currently documented as **public preview** and requires a SharePoint Advanced Management or Copilot license. Review availability and exclusions in [Trim existing versions at the tenant level](trim-versions#trim-existing-versions-at-the-tenant-level). For Multi-Geo tenants, run data collection, what-if analysis, and trimming separately for each geo.

Tenant-level trimming includes both SharePoint and OneDrive. Review their impact separately: OneDrive savings don't free SharePoint capacity when those services have separate quotas. In pooled-storage tenants, such as Education and trial tenants that share storage across the two services, OneDrive savings can free shared capacity.

### Estimate the storage opportunity

The SharePoint Admin Agent provides a quick view of **how much storage versions currently consume across the tenant**. That view isn't the same as **how much space a specific trimming policy could save**.

To estimate trimming savings, run a data collection job, wait for it to complete, and then run a **what-if analysis**. Compare automatic limits, manual limits, and supported file type overrides without deleting versions. For site-level analysis, generate a version storage usage report and follow the [what-if tutorial](tutorial-run-what-if-analysis).

Note

Data collection can take a long time for large tenants. Completion depends on tenant size, version volume, service load, and off-peak processing. The data collection job must be complete before you run impact queries. The agent's quick consumption summary doesn't replace this collection step.

**Optional: Add file type overrides.** Use different version limits for supported file types when their recovery needs differ from your default policy. Include the overrides in your what-if comparison before applying them. See [File type version limits](file-type-version-limits) for supported types and examples.

### Run the trim job and review savings

1. Review the projected savings, recovery needs, and retention requirements. Select the policy and scope you want to apply.
2. Start the trim job by using the [tenant-level or site-level procedure](trim-versions).
3. Use the job's progress and results to review storage savings and any incomplete processing. Distinguish the what-if estimate from storage actually reclaimed, and allow time for tenant storage reports to update.

**Expected result:** The job removes eligible versions according to the selected policy. Retention policies and eDiscovery holds can prevent deletion, so not all projected savings are immediately reclaimable.

Caution

Version trimming jobs bypass the normal recycle bin. Deleted versions can't be recovered from it. Recovery depends on a suitable backup created before deletion. Review the projected impact before starting a job.

Changing organization-level version defaults isn't the same as trimming existing versions. See Prevent storage from building up again.

## Archive inactive content you need to keep

**Use this when:** Content still has business or compliance value but you don't need frequent access.

Use **site-level archive and file-level archive together** to address different sources of inactive content across the tenant.

| Scope | Manual approach | Policy-based approach |
| --- | --- | --- |
| **Site-level archive**: an entire eligible site is no longer active | A SharePoint administrator selects sites in **Active sites** in the SharePoint admin center and chooses **Archive**. See [Archive a site](/en-us/microsoft-365/archive/archive-manage?view=o365-worldwide#archive-a-site). | Configure an [inactive site policy](inactive-site-policy) to identify inactive sites, notify owners, and archive eligible sites after the configured notification and mandatory read-only periods. |
| **File-level archive**: individual files are inactive but their sites remain in use | Where manual file archive is enabled, end users with edit permissions select files and choose **Archive**. Tenant administrators control where this action is available. See [Archive a file](/en-us/microsoft-365/archive/archive-manage?view=o365-worldwide#archive-a-file). | Configure an [inactive files policy](/en-us/microsoft-365/archive/manage-inactive-files?view=o365-worldwide) to automatically archive eligible files based on their recorded last human access date. Confirm preview availability; the current preview is managed through PowerShell. |

1. Identify candidates across the tenant and confirm business needs with content owners. A lack of recent edits doesn't mean content is unused; review activity and access patterns.
2. Review Archive eligibility, billing, application limitations, and reactivation requirements in [Microsoft 365 Archive](/en-us/microsoft-365/archive/archive-overview?view=o365-worldwide). Policy-based approaches also require the applicable SharePoint Advanced Management entitlement.
3. Preview the storage impact before enabling enforcement. **Both inactive site policies and inactive files policies have simulation modes.** Use the site policy report to review candidate sites and their storage usage, and the file policy report to review files and storage that would be archived. Review scope, exclusions, and results with owners. Notify affected users and explain how to reactivate content when needed.

Tip

**For urgent cleanup, distinguish direct action from lifecycle automation.** Manually archive eligible sites already approved by their owners rather than waiting for a new inactive site policy to complete its notification and mandatory read-only periods. File policies also take time to evaluate and process content. Neither policy creation nor a simulation result guarantees immediate storage savings.

Inactive files policies use recorded human access, not just modification dates. Access records can lag, so review the policy's [inactivity and data-quality guidance](/en-us/microsoft-365/archive/manage-inactive-files?view=o365-worldwide#select-an-inactivity-threshold) before broad deployment. Manual file archiving and policy archiving are separate controls; disabling the user-facing Archive action doesn't disable automatic file policies.

### Review file archive policy savings

Use the [inactive files policy reports](/en-us/microsoft-365/archive/manage-inactive-files?view=o365-worldwide#review-simulation-results) to review storage savings. Simulation reports show the files and storage that would be archived. After you enable archiving, review policy reports for processed content and storage moved to the archive tier.

Check processing coverage and skipped or failed items. A policy might need multiple runs, and simulation estimates can differ from actual savings as activity and eligibility change. Storage moved out of the active tier isn't necessarily an equal reduction in your bill.

**Expected result:** Archived files or sites no longer consume the tenant's active storage quota. They contribute to Archive storage consumption instead. Archiving changes how content is accessed; it doesn't delete the content or remove compliance requirements.

**Understand archive costs.** Archiving frees tenant quota for active content. If your **combined active and archived SharePoint storage** remains within your tenant's included or licensed storage capacity, archived sites and files have no additional Archive storage charge. Being below the quota for active content alone isn't enough; both tiers count when determining Archive charges. See [Microsoft 365 Archive pricing](/en-us/microsoft-365/archive/archive-pricing?view=o365-worldwide) for billing scenarios and applicable terms.

Moving files to a folder named "Archive" in an active library doesn't move them to the archive storage tier.

## Clean up unneeded content and recycle bins

**Use this process when:** Content has no remaining business value, isn't under a legal hold, and is eligible for deletion under your retention requirements.

1. **Agree on what to delete.** Ask site owners to identify files or sites they no longer need. Confirm with compliance owners that no legal hold or retention requirement prevents deletion. Review the exact items and confirm destructive actions before proceeding.
2. **Delete approved content.** Delete selected files or follow [Delete a SharePoint site](delete-site-collection) for an unneeded site. A deleted site is retained for 93 days before permanent deletion, unless you permanently delete it sooner. Recovery from a separate backup depends on its protection and retention settings.
3. **Clean up already-deleted items.** Review the site's first-stage and second-stage recycle bins. Empty them only after confirming that the items no longer need to be recoverable. Follow [Delete items or empty the recycle bin of a SharePoint site](https://support.microsoft.com/sharepoint/admin/delete-items-or-empty-the-recycle-bin-of-a-sharepoint-site) and its second-stage guidance.
4. **Recheck used storage against quota.** Allow 24-48 hours for SharePoint storage figures to reflect cleanup. Background deletion and retention processing can take longer. Use retention policies to automate future deletion after an approved period and reduce manual cleanup.

**Expected result:** Deleting eligible content can release active storage. Deleting a visible file or emptying the first-stage recycle bin isn't always the end of its lifecycle: items can move to the second stage, and retention can preserve copies.

Caution

Permanent deletion removes recycle-bin recovery. Don't empty recycle bins indiscriminately to meet a storage target. Deleting a Microsoft 365 group-connected site also deletes the group and associated resources; their recovery periods can differ from the site's 93-day period.

Note

Deleted **sites** in the SharePoint admin center's recycle bin don't count toward the organization's total SharePoint storage usage. It can take up to 48 hours for usage to update, so don't permanently purge those sites solely to reclaim tenant capacity. Deleted sites are different from deleted **items** in a site's second-stage recycle bin.

Microsoft 365 Backup uses separate storage accounting. When content is protected by Backup, deleted content, including content in the second-stage recycle bin, continues to count toward protected backup storage while retained for recovery. Deleting a protected site doesn't automatically eliminate its backup storage charges. See [Microsoft 365 Backup pricing](/en-us/microsoft-365/backup/backup-pricing?view=o365-worldwide).

### Use retention policies to delete content

Use Microsoft Purview retention policies to automate deletion across SharePoint sites when content reaches the end of its approved lifecycle. Choose **retain and then delete** when content must be kept for a required period, or **delete-only** when appropriate for your organization's requirements.

1. Work with compliance and records management owners to define the content, sites, time period, and deletion requirements.
2. Review overlapping retention policies, labels, and eDiscovery holds before configuring deletion. A requirement to retain content can prevent permanent deletion.
3. Review [Retention for SharePoint and OneDrive](/en-us/purview/retention-policies-sharepoint) to understand the deletion lifecycle. Then follow [Create retention policies](/en-us/purview/create-retention-policies?tabs=other-retention) to configure the appropriate policy with your compliance administrator.

**Expected result:** Eligible files enter the deletion lifecycle automatically. Background processing, recycle-bin stages, and applicable retention requirements mean storage might not be released immediately. Use this approach for ongoing lifecycle management, not as an instant response to a full tenant.

The Preservation Hold Library is a system-managed compliance location, not a cleanup folder. Don't manually edit, move, or delete its retained files, or shorten retention requirements solely to free space.

## Manage tenant capacity while you clean up

Address near-term capacity pressure before waiting for cleanup to finish. Additional capacity can also support necessary active content that remains after optimization.

| Option | When to consider it | Before you enable or purchase |
| --- | --- | --- |
| **Microsoft 365 SharePoint Storage (pay-as-you-go)** | You want usage-based billing for storage above the tenant quota | Review eligibility, preview status, Azure billing prerequisites, and budget alerts. |
| **Office 365 Extra File Storage** | You want to purchase additional allocated capacity | Review plan eligibility, purchasing channel, price, and required billing permissions. |
| **Eligible additional user licenses** | You also need licenses for users | Confirm the storage contribution for your specific plan; don't assume all licenses add the same capacity. |

Follow [Add storage capacity](/en-us/microsoft-365/commerce/add-storage-space?view=o365-worldwide) for current availability and setup instructions.

Microsoft 365 SharePoint Storage is currently documented as public preview for commercial tenants, excluding education, GCC, and Microsoft 365 operated by 21Vianet. While enrolled, tenants don't receive the usual tenant quota-related email and banner notifications. Set up [pay-as-you-go budget monitoring](/en-us/microsoft-365/commerce/services/pay-as-you-go-budget) and continue reviewing usage. Disconnecting while over quota resumes quota enforcement immediately.

Pay-as-you-go doesn't clean up content or remove other service limits. Archive and active storage have different billing implications; review both when assessing total cost.

## Prevent storage from building up again

Assign owners and review storage regularly to keep growth aligned with your organization's needs.

| Ongoing action | Why it matters |
| --- | --- |
| Use the [Automatic version setting](document-library-version-history-limits#automatic-setting) | Microsoft recommends Automatic to balance recovery needs and storage efficiency without choosing version count or age limits. New libraries inherit the tenant policy; apply it to existing libraries and [trim existing versions](trim-versions) to match. |
| Choose Automatic or Manual [site storage limits](manage-site-collection-storage-limits) | Balances ease of administration with site-specific controls. Limits don't increase tenant capacity. |
| Establish [inactive site policies](inactive-site-policy) and, where available, [inactive files policies](/en-us/microsoft-365/archive/manage-inactive-files?view=o365-worldwide) | Automates lifecycle management for entire sites and for inactive files within active sites. Review simulations, notification periods, exclusions, preview availability, and applicable entitlements. |
| Plan migrations and bulk uploads | Accounts for incoming files, versions, and expected growth before they consume capacity. |
| Review usage, growth, headroom, and costs regularly | Helps identify emerging pressure before users are affected. Increase review frequency during rapid growth or capacity incidents. |
| Use [retention policies](/en-us/purview/retention-policies-sharepoint) to retain and delete content according to approved requirements | Automates content lifecycle management without treating retention as an emergency cleanup tool. |

For your plan's storage entitlement and limits, see [SharePoint limits](/en-us/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits).

Note

**Pooled-storage exception:** OneDrive storage is separate from SharePoint tenant storage unless your tenant uses a shared storage pool. In pooled-storage tenants, such as Education and trial tenants where OneDrive and SharePoint share capacity, cleaning up OneDrive can free space in that shared pool. Check your tenant's storage model before attributing savings. For Education customers, see [Pooled storage management](/en-us/microsoft-365/education/guide/1-reference/pooled-storage-management).

## FAQs

### How is the SharePoint storage quota calculated?

For many plans, the tenant storage allocation starts at 1 TB, with an additional 10 GB for each eligible license purchased. Additional storage packs increase this allocation. Entitlements vary by plan, and pooled-storage tenants have different rules. See [SharePoint limits](/en-us/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) for your subscription's storage calculation.

### What happens if my tenant exceeds the SharePoint storage quota?

Reduce active storage usage through eligible cleanup or archiving, or increase tenant capacity. Eligible tenants can use Microsoft 365 SharePoint Storage (pay-as-you-go) to cover usage above the quota while cleanup continues.

Without additional capacity or applicable pay-as-you-go coverage, exceeding the quota blocks classic site creation and site creation through PowerShell. Continued operation above storage limits also risks read-only enforcement, which can prevent users from adding or modifying content. See [SharePoint limits](/en-us/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) and [storage capacity options](/en-us/microsoft-365/commerce/add-storage-space?view=o365-worldwide) for current guidance.

### How does version trimming work with the Preservation Hold Library?

Version trimming doesn't remove the preserved files in the Preservation Hold Library. Retention policies and eDiscovery holds can also prevent deletion of versions, so a trimming job might not reclaim all projected storage while those requirements apply.

The service manages the Preservation Hold Library to meet compliance requirements. Don't manually edit, move, or delete its retained files. See [Version history FAQs](faqs-for-versions) and [Learn about retention for SharePoint and OneDrive](/en-us/purview/retention-policies-sharepoint).