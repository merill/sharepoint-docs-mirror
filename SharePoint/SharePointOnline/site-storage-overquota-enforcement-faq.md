---
layout: Conceptual
title: OneDrive for Business Storage Quota Bug Fixes FAQ - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/site-storage-overquota-enforcement-faq
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
description: FAQ for how OneDrive for Business enforces per-user storage quotas based on user license, what happens when limits are exceeded, and how to restore access.
ms.date: 2026-07-01T00:00:00.0000000Z
author: JillTh
ms.author: JillTh
ms.reviewer: JillTh
manager: jmcdowe
ms.topic: faq
ms.service: onedrive
locale: en-us
document_id: 3b50cbe8-57b4-9a29-2947-eae12d4a2958
document_version_independent_id: d2de3bdd-0958-db2d-6aa4-64b955b5897f
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/site-storage-overquota-enforcement-faq.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: site-storage-overquota-enforcement-faq
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/site-storage-overquota-enforcement-faq.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
platformId: 5d9fb15d-15e4-2bb7-94e2-183602f1be83
---

# OneDrive for Business Storage Quota Bug Fixes FAQ - SharePoint in Microsoft 365 | Microsoft Learn

This article answers common questions about recent changes to how OneDrive for Business enforces per-user storage quotas, ensuring they align with each user's license entitlement. These updates address previous inconsistencies and improve quota enforcement reliability.

Note

**This change correctly applies the OneDrive for Business storage your licenses provide.** Every user’s maximum OneDrive limit has always been defined by their license. The only users affected are those configured above their licensed entitlement - so no storage that was purchased is removed. This change isn't a change in service or terms.

## General

### Will the storage quota enforcement changes impact my organization?

Most tenants aren't affected. Only users whose OneDrive storage is set above what their license entitles - typically due to a user-specific limit set higher than the entitlement - are impacted.

To check if your users are affected, run the PnP PowerShell report: [Identify OneDrive Users Over License-Based Storage Quota](https://pnp.github.io/script-samples/onedrive-overquota-report/README.html).

If all users are within their licensed quotas, no action is required.

### What happens if a user's OneDrive for Business storage allocation is exceeded?

When a user's OneDrive usage exceeds their licensed quota, their OneDrive enters a read-only state. In this state, users can't edit existing files or add new files in their OneDrive, but they can download or delete existing content.

### Are extended storage allocations still allowed?

Users keep extended storage only if they continue to hold a license that grants the higher (extended) allocation. Extended storage is tied to qualified Enterprise Plan 2 licenses. If the Enterprise Plan 2 license is present, the extended allocation remains. If a user with extended allocation no longer has a qualifying license, their maximum storage is adjusted to match their current license entitlement.

### How can I restore a user's OneDrive for Business from read-only state?

A user's OneDrive becomes read-only when their usage exceeds their licensed quota. To fix this problem, you can:

1. **Upgrade the user's license** to one with a higher entitlement.
2. **Reduce the user's storage usage** to within the licensed limit. Remember that version history, recycle bins, and Preservation Hold libraries are included in storage usage calculations.
3. **Buy extra per-user capacity** by using OneDrive Extra Storage capacity packs, which are available in 100 GB, 500 GB, and 1 TB–6 TB sizes. Each pack is assigned per user and can't be split across users. A single user's total storage can't exceed 25 TB. [Add storage space](/en-us/microsoft-365/commerce/add-storage-space)

**Note:** The pay-as-you-go option, M365 OneDrive Storage, will be available in public preview in July 2026. It's not currently available to education and government customers. Education and Government tenants should use license upgrades, usage reduction, or OneDrive Extra Storage capacity packs.

### I'm an Education tenant—are my users impacted?

Generally, only users with a user-specific limit set above their license entitlement are affected.

- **A1:** Entitled to 100 GB per user.
- **A3 / A5:** Licenses that include the “SharePoint (Plan 2) for Education” service plan entitle the user to a 5 TB OneDrive limit. If you use a less common A3 or A5 SKU, confirm it includes SharePoint (Plan 2) for Education. Admins can set a lower quota, which is honored.
- **Other licenses:** Storage limits of those licenses are enforced. For example, if a user is entitled to 10 GB and is using more, their limit is set to 10 GB and their OneDrive goes read-only.

**Student Use Benefit (SUB) licenses:** SUB licenses provide a per-user OneDrive entitlement but don't contribute to the tenant’s shared storage pool. These entitlements are separate.

### I'm a government tenant—are my users impacted?

**Not at this time.** Government environments are currently out of scope. Microsoft will communicate separately when this change becomes applicable to those clouds.

### Why is Microsoft making this change?

- **To enforce license-based storage:** Each user's OneDrive storage limit is now consistently enforced according to their license. Only users configured above their licensed entitlement are affected.
- **To fix a bug:** Previously, user-specific limits could be incorrectly updated during quota refreshes, causing inaccurate enforcement. This problem included cases where admin-set limits in Education tenants were reset to default. This fix ensures predictable storage behavior.
- **For consistency and reliability:** Admins managing storage at scale can now rely on license storage limits being enforced uniformly.

### What is the difference between tenant storage and individual OneDrive storage?

These two types of storage are separate "accounts." This change affects only individual OneDrive storage:

- **Individual OneDrive (per-user) entitlement:** The maximum amount a single user's OneDrive can hold, set by their license. This change enforces this limit.
- **Shared tenant storage pool:** The organization-wide SharePoint pool. This change doesn't affect the pool contribution.

**Key point:** Storage packs that add to the shared pool don't allow an individual user to exceed their per-user OneDrive entitlement. To increase a specific user's limit, use a OneDrive Extra Storage capacity pack or a higher-tier license. All storage in a user's OneDrive still counts toward the tenant-wide pool.

### When will my tenant be impacted?

- **General Availability:** Rollout begins July 1, 2026, and is expected to complete by mid-July 2026. Timing varies by tenant.
- Admins receive advance notice via Message Center post MC1310684.
- **Government clouds:** Not scheduled at this time.