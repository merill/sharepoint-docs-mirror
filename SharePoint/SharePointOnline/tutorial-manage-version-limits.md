---
layout: Conceptual
title: 'Tutorial: Manage version history limits on a site, library, or OneDrive account - SharePoint in Microsoft 365 | Microsoft Learn'
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/tutorial-manage-version-limits
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
description: This article provides guidance on how to manage Version history limits for a site, library, or OneDrive account.
locale: en-us
document_id: 5a38e167-2173-1e07-3a4f-b7663b9b77c7
document_version_independent_id: 32b44126-f06d-4f0a-9119-23a3c84e5200
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/tutorial-manage-version-limits.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: tutorial-manage-version-limits
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/tutorial-manage-version-limits.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 88262b51-8cb1-6935-2165-9068cfb82dbe
---

# Tutorial: Manage version history limits on a site, library, or OneDrive account - SharePoint in Microsoft 365 | Microsoft Learn

In this tutorial, you will learn how to manage the version history limits for a site, document library, or OneDrive account. You will learn how to:

- Set Version history limits settings on the site.
- Stop an in-progress settings update job.

## Before you begin

- Review your **organization’s recovery objectives** and **version storage use quota targets** along with the **site-specific version storage needs** to evaluate if a break of inheritance of version settings at site, library, or OneDrive account level is needed.
- If needed **run an impact analysis** with the desired setting, to understand the impact the new setting would have using current version storage usage patterns.
- For setting site level version limits, evaluate the scope of document libraries that should be updated. Depending on business need, you can choose one of the following:

    - Update new libraries only without impacting existing library settings.
    - Update existing libraries only and inherit organization default settings for new libraries.
    - Update both existing and all new libraries for consistent version storage at the site level.

## Set version limits for a site

You can set version limits on a site by running the [**Set-SPOSite**](/en-us/powershell/module/sharepoint-online/set-sposite) command to break inheritance from the organization version history limits.

- Use the `–ApplyToNewDocumentLibraries` parameter to apply the changes only to new libraries created in the site.
- Use the `–ApplyToExistingDocumentLibraries` to only update the Version history limits on existing libraries on a site. Any new library created inherits the default organization limits.

### Example: Apply automatic version history limits to all document libraries on a site

Run the following commands to **apply Automatic setting** to all document libraries on a site.

```PowerShell
Set-SPOSite -Identity https://contoso.sharepoint.com/sites/site1 -EnableAutoExpirationVersionTrim $true  
```

### Example: Apply automatic version history limits to new document libraries on a site

In the following example, Automatic Version history limits are applied to all new document libraries created on the site. The settings on existing libraries will not be impacted.

```PowerShell
 Set-SPOSite -Identity https://contoso.sharepoint.com/sites/site1 -EnableAutoExpirationVersionTrim $true -ApplyToNewDocumentLibraries
```

### Example: Apply manual setting with count and time version history limits to existing libraries only on a site

In the following example, Version history limits of all existing libraries on a site are updated to Manual Version history limits.

```PowerShell
Set-SPOSite -Identity https://contoso.sharepoint.com/sites/site1 -EnableAutoExpirationVersionTrim $false -MajorVersionLimit 500 -ExpireVersionsAfterDays 30 -ApplyToExistingDocumentLibraries
```

## Cancel an in-progress request to update version history limits on existing libraries

If required, you can cancel the update job that is currently `<InProgress>` using the `Remove-SPOSiteVersionPolicyJob`.

Note

Cancelling the job doesn't revert the change for document libraries where the update is already processed.

In the example below, the in-progress job to update settings on site will be stopped.

```PowerShell
Remove-SPOSiteVersionPolicyJob -Identity https://contoso.sharepoint.com/sites/site1
```

## Learn More

- Track progress of version settings update request for existing document libraries on a site using [Get-SPOSiteVersionPolicyJobProgress](/en-us/powershell/module/sharepoint-online/get-spositeversionpolicyjobprogress).
- Cancel further processing of version settings update on existing document libraries on the site collection using [Remove-SPOSiteVersionPolicyJob](/en-us/powershell/module/sharepoint-online/remove-spositeversionpolicyjob).