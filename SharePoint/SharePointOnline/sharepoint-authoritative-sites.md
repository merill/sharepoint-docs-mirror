---
layout: Conceptual
title: SharePoint Authoritative Sites in Copilot Search - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/sharepoint-authoritative-sites
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
description: Learn how to designate Authoritative SharePoint Sites so users can identify trusted organizational sources in Copilot Search.
author: Shlata0203
ms.author: shlata
ms.reviewer: karlha
manager: dansimp
ms.service: sharepoint-online
ms.subservice: ai-copilot
ms.topic: how-to
ms.date: 2026-08-26T00:00:00.0000000Z
ms.update-cycle: 180-days
audience: Admin
ms.localizationpriority: medium
ms.collection:
- m365-sam
- M365-collaboration
- m365copilot
f1.keywords:
- NOCSH
search.appverid:
- MET150
locale: en-us
document_id: 3c20ad42-c47e-2e6c-ee87-7c7760684dd5
document_version_independent_id: 5c198893-cac0-b1c9-1e86-710a50d540d3
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/sharepoint-authoritative-sites.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: sharepoint-authoritative-sites
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/sharepoint-authoritative-sites.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
platformId: e2fb72af-207a-6332-3cda-e49b7417cefc
---

# SharePoint Authoritative Sites in Copilot Search - SharePoint in Microsoft 365 | Microsoft Learn

Authoritative sites help administrators identify official, organization-managed SharePoint sources. When you mark a site as authoritative, Copilot Search experiences recognize its content as trusted.

For users, this recognition improves confidence in search results. Visual signals, such as the **From your organization** label, make trusted items easier to identify.

Important

In the current release, configure authoritative sites through PowerShell and CSOM APIs. The configuration supports site-level designation but doesn't support personal sites.

## Prerequisites

See [Prerequisites for SharePoint Advanced Management](sharepoint-advanced-management-prerequisites).

## Why use authoritative sites

Use authoritative sites to:

- Improve trust in Copilot Search by promoting verified organizational sources.
- Help users quickly identify official content.
- Reduce time spent validating whether content is reliable.
- Maintain centralized admin control over authoritative source designation.

## Configure authoritative sites with SharePoint Online Management Shell

Use SharePoint Online Management Shell when you want a straightforward admin workflow.

1. Install and import the module.
2. Connect to your SharePoint admin center.
3. Mark the site as authoritative.

```powershell
Install-Module -Name Microsoft.Online.SharePoint.PowerShell -Force
Import-Module -Name Microsoft.Online.SharePoint.PowerShell

Connect-SPOService -Url "https://<tenant>-admin.sharepoint.com"
Set-SPOSite -Identity "https://<tenant>.sharepoint.com/sites/<siteName>" -IsAuthoritative $true
```

## Configure authoritative sites with CSOM (advanced)

Use CSOM when you need automation or bulk operations.

Note

CSOM version 16.1.26914.12004 or later is required.

### Step 1: Install PnP PowerShell

```powershell
Install-Module PnP.PowerShell -Scope CurrentUser -Force
```

### Step 2: Register a Microsoft Entra ID app

Register an app for interactive authentication and copy the client ID from the output.

```powershell
$tenant = "<TenantName>.onmicrosoft.com"
Register-PnPEntraIDAppForInteractiveLogin -ApplicationName "PnP Interactive (SPO Admin)" -Tenant $tenant -SharePointDelegatePermissions "AllSites.FullControl" -SharePointApplicationPermissions "Sites.FullControl.All" -GraphDelegatePermissions "Sites.FullControl.All" -GraphApplicationPermissions "Sites.FullControl.All" -Interactive
$clientId = "<FROM ABOVE OUTPUT>"
```

### Step 3: Install SharePoint Online CSOM

```powershell
Install-Package Microsoft.SharePointOnline.CSOM -Source nuget.org -Scope CurrentUser
```

### Step 4: Load CSOM assemblies

```powershell
$dllPath = "C:\Users\<USER_NAME>\AppData\Local\PackageManagement\NuGet\Packages\Microsoft.SharePointOnline.CSOM.<VERSION>\lib\netstandard2.0"
Add-Type -Path "$dllPath\Microsoft.SharePoint.Client.dll"
Add-Type -Path "$dllPath\Microsoft.SharePoint.Client.Runtime.dll"
Add-Type -Path "$dllPath\Microsoft.Online.SharePoint.Client.Tenant.dll"
```

### Step 5: Connect to SharePoint Online

```powershell
$tenantDomain = "<TenantName>.onmicrosoft.com"
Connect-PnPOnline -Url "https://<TenantName>-admin.sharepoint.com" -ClientId $clientId -Tenant $tenantDomain -Interactive
```

### Step 6: Initialize tenant object and verify API availability

```powershell
$ctx = Get-PnPContext
$tenant = New-Object Microsoft.Online.SharePoint.TenantAdministration.Tenant($ctx)
$ctx.ExecuteQuery()

$tenant.GetType().GetMethod("GetAuthoritativeResources")
```

### CSOM operations

#### Get authoritative sites

```powershell
$authResources = $tenant.GetAuthoritativeResources()
$ctx.ExecuteQuery()
```

#### Mark a site as authoritative

```powershell
$siteId = [Guid]"<SiteId>"
$result = $tenant.SetResourceAsAuthoritative($siteId)
$ctx.ExecuteQuery()
$result.Value
```

#### Remove a site from authoritative sites

```powershell
$siteId = [Guid]"<SiteId>"
$result = $tenant.RemoveResourceAsAuthoritative($siteId)
$ctx.ExecuteQuery()
```

If the site is removed successfully, the response is empty. If the operation fails, PowerShell returns an exception.

#### Bulk mark sites as authoritative

```powershell
[System.Guid[]]$siteIds = @([Guid]"<SiteId1>", [Guid]"<SiteId2>", [Guid]"<SiteId3>")
$results = $tenant.BulkSetResourceAsAuthoritative($siteIds)
$ctx.ExecuteQuery()
$results
```

#### Bulk remove authoritative sites

```powershell
[System.Guid[]]$siteIds = @([Guid]"<SiteId1>", [Guid]"<SiteId2>", [Guid]"<SiteId3>")
$results = $tenant.BulkRemoveResourceAsAuthoritative($siteIds)
$ctx.Load($results)
$ctx.ExecuteQuery()
$results
```

## Lifecycle and maintenance

Maintain authoritative sites as a living set of trusted sources:

- Review the list regularly and remove outdated or no-longer-official sites.
- Validate behavior after site deletion or restore events.
- Plan for propagation time after updates.

## Limitations

- You can mark up to 100 sites as authoritative.
- Changes can take up to 72 hours to appear in supported experiences.
- Designation is currently site-level only.
- Multi-geo tenants manage authoritative site data per geo.
- Personal sites can't be marked as authoritative.

## Troubleshooting

If changes don't appear as expected, check the following items:

- **Licensing**: A Microsoft Copilot license is required. (See [Prerequisites for SharePoint Advanced Management](sharepoint-advanced-management-prerequisites).)
- **Feature availability**: Make sure the feature is enabled in your tenant.
- **Site eligibility**: Make sure the URL is valid and references a supported SharePoint site.
- **Timing**: Allow enough time for propagation (up to 72 hours).