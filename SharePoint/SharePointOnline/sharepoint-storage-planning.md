---
layout: Conceptual
title: Plan for SharePoint storage - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/sharepoint-storage-planning
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-09-29T00:00:00.0000000Z
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

# Plan for SharePoint storage - SharePoint in Microsoft 365 | Microsoft Learn

SharePoint is the most trusted and flexible platform for your content, providing enterprise-grade security and compliance tooling, built-in high availability and disaster recovery, point-in-time restore, and much more. Depending on your business scenarios, it's important that you plan your content storage strategy to maximize user value and to optimize storage costs. This article highlights ways to gather data for insights into storage usage, tools to help manage or reduce storage footprint of less valuable content, and premium offerings for a richer experience.

Note

Storage values can differ across SharePoint experiences because they measure different aspects of content. For example, a document library typically shows the size of the current file, while Storage Metrics and other storage reports reflect the total storage consumed by that content. Storage consumption can include version history and other storage-related data associated with a file. As a result, the storage reported for a site, library, or folder might be larger than the combined size of the current files displayed in a document library.

## Understand storage drivers

As storage grows over time, it's important to understand what drives storage growth and to identify the areas that could need your attention. There are options to review storage trends, ranging from usage reports in the Microsoft 365 admin center, which provide easy-to-consume visuals, to rich datasets available through Microsoft Graph Data Connect (MGDC).

- Review storage used by active sites, archived sites, and deleted sites in the [SharePoint admin center](https://go.microsoft.com/fwlink/p/?linkid=2185219). The upper right side of the [Active sites](https://go.microsoft.com/fwlink/p/?linkid=2185220) page shows the amount of storage used across all sites, and the total storage for your subscription. If your organization has configured Multi-Geo in Microsoft 365, the bar also shows the amount of storage used across all geo locations.
- Use [SharePoint dataset from Microsoft Graph Data connect](https://aka.ms/SharePointData) to analyze site lifecycle, ownership, and storage used by SharePoint sites and OneDrive accounts. Answer questions such as which type of site uses the most storage, how much storage was used by previous versions, and how many sites haven't changed in the past year. File level data is also available now through the [SharePoint Files dataset.](https://techcommunity.microsoft.com/t5/microsoft-graph-data-connect-for/update-on-the-sharepoint-files-dataset/ba-p/4189538)^**(\*)**^
- Explore storage trends through the [SharePoint Admin Agent](/en-us/SharePoint/content-governance-agent). The storage skill can help analyze your SharePoint storage usage and provide actionable insights for storage management. ^**(\*)**^

Note

Deleted sites in the Recycle Bin do not count toward the organization's total storage usage. It takes up to 48 hours for the storage usage to update.

## Set up storage configurations

Configure the site storage limits, version history limits, and retention policies that meet your organization's needs. Whether that's automatic limits for simplicity or custom limits for maximum control, setting up these limits is fundamental for storage management.

- Set [site storage limits](/en-us/sharepoint/manage-site-collection-storage-limits) to **Automatic** to simplify site storage management, or to **Manual** for custom limits. Site limits cap the allocation of pooled tenant storage resources among sites within the organization.
- Update [organization version history limits](https://aka.ms/versioning-overview) to **Automatic** for optimal version restore and storage.
- Review [retention policies for SharePoint](/en-us/purview/retention-policies-sharepoint) to manage compliance requirements with storage use.

## Optimize storage usage

Increase available storage by cleaning up low-value versions and inactive sites or by moving inactive content to a lower cost archive storage solution.

- Archive inactive content to reduce active storage costs using [Microsoft 365 Archive.](https://aka.ms/M365Archive)
- [Trim existing low-value versions](/en-us/sharepoint/trim-versions) to reduce storage.
- Recover storage from deleted items by [emptying site recycle bin](https://support.microsoft.com/en-us/office/delete-items-or-empty-the-recycle-bin-of-a-sharepoint-site-2e713599-d13e-40d6-96dc-66f0a366f74e).
- Leverage [retention settings](/en-us/purview/retention-policies-sharepoint) to automatically delete files after a specified period.
- Manage site lifecycle policies through [SharePoint Advanced Management](/en-us/sharepoint/advanced-management). Set up an [inactive site policy](/en-us/sharepoint/inactive-site-policy) to automatically detect inactive sites and send notifications to site owners via email. ^**(\*)**^

## Purchase additional storage

To increase SharePoint storage capacity, purchase additional storage in one-gigabyte increments or acquire more SharePoint licenses.

- Purchase SharePoint user licenses, adding 10 GB per license to the storage limit. SharePoint user licenses are included in plans, such as Microsoft 365 for business or enterprise.^**(\*)**^
- Set up [Microsoft 365 SharePoint Storage](/en-us/microsoft-365/commerce/add-storage-space), a pay-as-you-go solution for additional storage usage above the tenant quota. (\*)
- Purchase [additional storage](/en-us/microsoft-365/commerce/add-storage-space) at a cost per gigabyte (GB) per month.^**(\*)**^

^**(\*)**^: Additional licensing/charges might apply

## FAQs

1. How is the SharePoint storage quota calculated? SharePoint storage quota for the tenant starts at 1 TB and each additional SharePoint license purchased adds 10 GB. For more information, see [SharePoint limits - Service Descriptions](/en-us/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits).
2. What happens if my tenant exceeds the SharePoint storage quota? When the SharePoint storage quota is exceeded, you might need to purchase additional storage or manage existing storage more efficiently through deletion or archival. In addition, classic site creation and site creation through PowerShell is blocked.
3. How does version trimming work with the preservation hold library? Version trimming doesn't impact the files in the preservation hold library since the original copies of the files are preserved. For more information on how retention settings work in SharePoint, see [Learn about retention for SharePoint and OneDrive](/en-us/purview/retention-policies-sharepoint).