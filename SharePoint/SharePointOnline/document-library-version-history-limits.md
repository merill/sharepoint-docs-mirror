---
layout: Conceptual
title: Version history limits for document library and OneDrive overview - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/document-library-version-history-limits
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
ms.topic: concept-article
ms.service: sharepoint-online
ms.subservice: platform
ms.localizationpriority: medium
search.appverid:
- SPO160
- SPS150
- MET150
description: This article provides guidance on how version history limits are applied at organization, site, library or OneDrive user account level.
locale: en-us
document_id: 626df1aa-b00a-f131-9b91-a31a45a6941a
document_version_independent_id: 87788642-4b47-a533-45ee-8c639cf71c99
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/document-library-version-history-limits.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: document-library-version-history-limits
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/document-library-version-history-limits.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: a8397662-8c0d-693b-82e1-282b2d660a1f
---

# Version history limits for document library and OneDrive overview - SharePoint in Microsoft 365 | Microsoft Learn

Version history limits control how versions are stored in a SharePoint document library or OneDrive account. Limits can be set at organization, site, library or OneDrive user account level allowing admins and site owners the ability to better manage content recovery and auditing requirements. Global and SharePoint admins in Microsoft 365 can set version history limits at the organization level. These settings apply universally to all new libraries, whether on existing or new SharePoint sites, and on default libraries on new OneDrive sites. Site owners can overwrite organization-level version settings by [configuring version settings for sites](site-version-limits) they own. Site owners can overwrite organization or site settings by [configuring version settings for libraries and lists](https://support.microsoft.com/en-us/office/enable-and-configure-versioning-for-a-list-or-library-1555d642-23ee-446a-990a-bcab618c7a37) they own.

The following table summarizes the various ways of managing version history limits on your document libraries:

| Area | How does it work? |
| --- | --- |
| **Set default organization version history limits** | Default organization version history limits are set on all new document libraries created across existing and new SPO sites. |
| **Set site or library level version history limits** | If needed, site admins can break inheritance from the default organization limits for an individual site or library. |
| **Report on version storage on a site** | Run a report to analyze version storage use of existing versions, understand how a version limit works before configuring limits, or analyze the impact of trimming existing versions before scheduling trim job. |
| **Trim existing versions** | Site admins can choose to trim existing versions by queuing a timer job to execute the trimming. |

## How Version history limits are applied

Version history limits are applied in the following ways:

- **Default organization limits:** Organization default settings are applied to all new libraries created on sites that don't have site level settings configured.
- **Site limits:** It is possible to break inheritance for a site by configuring version history limits for the site. When version limits are configured on a site, the settings are applied to all new libraries created on the site.
- **Library limits:** It is possible to break inheritance at library level to define version limits for files stored in the library.

In the following example, default organization limits are applied to new libraries created on marketing and sales sites as these sites do not have site level limits applied. Legal site has site level limits applied and broken inheritance from the organization defaults. Libraries created in the legal site follow the limits applied at the legal site level.

[![Screenshot of how version history limits are applied.](sharepointonline/media/version-history/how-ver-lim-app.png)](sharepointonline/media/version-history/how-ver-lim-app.png#lightbox)

The following figure shows the workflow of applying a version limit on new document libraries. When a new library is created, site level setting check is performed. If no site setting is defined, the organization default setting is applied to new libraries.

[![Diagram of version limits for new libraries.](sharepointonline/media/version-history/version-limits-new-libraries-flow.png)](sharepointonline/media/version-history/version-limits-new-libraries-flow.png#lightbox)

## Types of version limits

There are two version history settings that admins can use to configure version limits for all new libraries created in their organization:

### Automatic setting

Automatic setting is recommended for optimized version storage. It combines the data recovery benefits that version history offers while optimizing for its storage. For admins, this setting offers the most optimal storage option without having to estimate the version count or age limits needed to meet the diversified need of their end users. For more information, see [version storage under automatic limits](plan-version-storage#understand-version-storage-under-automatic-limits).

### Manual setting

The manual setting allows admins to set count limits on the number of major versions or to set expiration and count limits. When this option is selected, the admins can configure it in the following ways.

- **Major version limit with expiration period**: Versions are deleted after exceeding either the set number of major versions or after the set period of time. For example, if you configure a library to store 500 major versions with a 365-day expiration, the system stores no more than 500 versions, and automatically deletes any version older than 365 days.
- **Major version limits with no expiration period**: Versions are deleted after they exceed the set number of major versions. For example, if a library is configured to store 500 major versions, no more than 500 versions is stored for each file or item.

    For more information, see [determining the right count or expiration version limits](plan-version-storage#determine-right-count-or-expiration-version-limits).

Note

- The UI doesn't allow a value less than 100 major versions or less than 30 days expiration time limits to be set, but it's possible to set the system to store fewer versions using public APIs. For reliability, any value less than 100 versions or less than 30 days expiration time limit isn't recommended and can result in the user activity causing an inadvertent data loss.
- If time version history limits are configured on a library, the file version expiration date is stamped on a version at creation time. The expiration date set on a file version is determined from the SnapshotDate of the version which is the date a version became a historical version. The SnapshotDate might be estimated if the version was snapshotted before January 1, 2023.

## Version storage behavior

Version storage in SharePoint is determined by several factors including limits configured on a library, user deletion activity, or retention policies. The following table enumerates the various scenarios and expected version storage behavior:

The following table enumerates the scenarios and the expected version storage behavior:

| Scenario | Version Trimming Behavior |
| --- | --- |
| User deletes versions from the version history of a file. | When a user deletes a version from the version history of a file, the deleted version is moved to the site's recycle bin and can be recovered for a period. For more information, see [Restore items in the recycle bin that were deleted from SharePoint or Teams](https://support.microsoft.com/en-us/office/restore-items-in-the-recycle-bin-that-were-deleted-from-sharepoint-or-teams-6df466b6-55f2-4898-8d6e-c0dff851a0be). |
| Versions exceed settings applied on the document library. | When versions exceed the limits set at the library, versions matching the criteria are marked for permanent deletion. This version deletion workflow bypasses the normal recycle bin and the deleted versions can't be recovered from recycle bin. |
| Timer job scheduled to trim existing versions on a library or site. | Versions deleted using scheduled jobs are permanently deleted. This version deletion workflow bypasses the normal recycle bin and deleted versions can't be recovered from recycle bin. |
| Version storage on items that are subject to retention policy or on an eDiscovery hold. | For items that are subject to a retention policy (or an eDiscovery hold), the versioning limits for the document library are ignored. This exemption continues until the retention period of the document is reached (or the eDiscovery hold is released). For more information, see [How retention works with document versions](/en-us/purview/retention-policies-sharepoint). |
| Timer job scheduled to trim existing versions on a library or site encounters versions that are subject to retention policy or on an eDiscovery hold. | When a trim job encounters a version under a retention policy or an eDiscovery hold, it will stamp an expiration date on the version instead of deleting it. Once the expiration date is reached: 1) if the retention policy or eDiscovery hold is still in effect for the version, the expiration date is extended; or 2) if the retention policy or eDiscovery hold has been lifted for the version, the version is deleted. |
| Trimming existing versions on sites that are Read Only (locked sites). | Trimming of expired versions on sites that are under retention or are on hold is suspended until the site is unlocked. |
| Versions deletion on items with retention labels applied. | Versioning limits are honored on items with retention labels when the content isn't subject to a retention policy (or an eDiscovery hold). Versions matching the limit criteria are automatically deleted to accommodate new versions, but users are still prevented from deleting versions. |
| Version deletion on items marked as records. | Version deletion on documents marked as records is blocked. For more information, see [Use record versioning in SharePoint or OneDrive](/en-us/purview/record-versioning). |

## Auditing versioning events

Audit events are available on the Microsoft Purview portal to help you monitor version history activities. Audit events are logged for the following activities:

- Changes made to organization version history limits.
- Changes made to site version history limits.
- Changes made to library version history limits.
- User queues a job to generate a version storage usage report.
- User queues a job to update the version history limits on all libraries of a site.
- User queues a job to bulk delete version history of files on a library or site.
- User deletes versions from the version history of a file.
- Versions deleted when expired or bulk deleted.