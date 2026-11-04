---
layout: Conceptual
title: Restricted SharePoint Search Admin PowerShell Scripts - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/restricted-sharepoint-search-admin-scripts
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-07-06T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.reviewer: 
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: administrator
customer-intent: As a SharePoint Administrator or higher in Microsoft 365, I want to use PowerShell scripts to manage Restricted SharePoint Search settings and the allowed list.
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- M365-collaboration
- m365copilot
- magic-ai-copilot
- trust-pod
- M365-sam
description: Learn how to use PowerShell scripts as a SharePoint Administrator or higher in Microsoft 365 to get current mode of Restricted SharePoint Search, enable/disable Restricted SharePoint search, add to or remove from the allowed list, and get the list of current sites in the allowed list.
locale: en-us
document_id: e27389f2-43cf-c7c1-7cd3-dfd2d4f2a4da
document_version_independent_id: 173dfe6a-75b6-134d-e8e5-f96228d1ecc9
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/restricted-sharepoint-search-admin-scripts.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: restricted-sharepoint-search-admin-scripts
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/restricted-sharepoint-search-admin-scripts.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
platformId: c2e6fd00-c32e-150b-5c53-8bc010eaa7b9
---

# Restricted SharePoint Search Admin PowerShell Scripts - SharePoint in Microsoft 365 | Microsoft Learn

Important

Restricted SharePoint Search is retiring. Starting July 31, 2026, new enablement is blocked. Use comprehensive data controls such as [Restricted Content Discovery](/en-us/sharepoint/restricted-content-discovery) (RCD) for content discoverability.

[Restricted SharePoint Search](/en-us/sharepoint/restricted-sharepoint-search) is designed for customers of Microsoft Copilot Chat and agentic experiences. It's designed as a short-term solution to allow time for your organization's administrators to thoroughly review and audit site and file permissions, but it's not intended or scalable for long-term use. Comprehensive data security solutions are available, including [SharePoint Advanced Management](/en-us/sharepoint/advanced-management) and [Microsoft Purview](/en-us/purview/ai-microsoft-purview).

## How to enable and manage restricted SharePoint Search by using PowerShell scripts

By default, Restricted SharePoint Search isn't enabled. To enable and set up restricted SharePoint Search, you need to have at least the permissions of a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) in Microsoft 365. Depending on the scenario, some actions you need to take are:

- Get the current mode of restricted Search
- Enable and disable restricted Search
- Add sites to the allowed list by providing URL
- Remove sites from the allowed list by providing URL
- Get the existing list of URLs that are added in allow list

This article covers how to use admin scripts in PowerShell for these actions.

## Before you begin

You must be a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or have equivalent permissions in Microsoft 365 to run the PowerShell admin scripts.

See [Prerequisites for SharePoint Advanced Management](sharepoint-advanced-management-prerequisites).

Before you use the PowerShell scripts in this article, see [SharePoint Online PowerShell module requirements](sharepoint-advanced-management-prerequisites#sharepoint-online-powershell-module).

## Get the current mode of Restricted SharePoint Search

Restricted SharePoint Search is disabled by default. To verify this feature's current mode, you can run the following command:

```powershell
Get-SPOTenantRestrictedSearchMode
```

**Module**: [Microsoft.Online.SharePoint.PowerShell](/en-us/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell)

**Applies to:** SharePoint Online

**Syntax**

```powershell
Get-SPOTenantRestrictedSearchMode
```

**Example**

```powershell
Get-SPOTenantRestrictedSearchMode
```

This example lets the admin get the existing allowed list in the tenant. Result can be "Enabled" or "Disabled" based on the current setting.

## Enable or disable Restricted Search

Enable or disable the Restricted Search setting. The default is disabled. The first time you enable the setting, the allow list is empty. To enable or disable the Restricted SharePoint Search, run this command:

```powershell
Set-SPOTenantRestrictedSearchMode
```

**Module**: [Microsoft.Online.SharePoint.PowerShell](/en-us/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell)

Applies to: SharePoint Online

**Syntax**

```powershell
Set-SPOTenantRestrictedSearchMode 
[-Mode] {Disabled | Enabled}
 [<CommonParameters>]
```

**Example 1**

```powershell
Set-SPOTenantRestrictedSearchMode -Mode Enabled  
```

Note

Once enabled, any new sites are excluded unless you add them to the allow list.

Example 1 sets or enables the Restricted Tenant Search mode for the tenant.

**Example 2**

```powershell
Set-SPOTenantRestrictedSearchMode – Mode Disabled  
```

Example 2 disables the Restricted Tenant Search mode for the tenant.

**Parameters**

`-Mode`

Sets the mode for the Restricted Tenant Search.

| Type | String |
| --- | --- |
| Position: | `0` |
| Default Value: | `Disabled` |
| Required: | `True` |
| Accept Pipeline input: | `False` |
| Accept wildcard characters: | `False` |

## Add sites to the allow list

When you enable Restricted SharePoint Search, add site URLs to the allow list in a string or CSV file by using this command:

```powershell
Add-SPOTenantRestrictedSearchAllowedList
```

**Module:**[Microsoft.Online.SharePoint.PowerShell](/en-us/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell)

**Applies to:** SharePoint Online

**Syntax**

```powershell
Add-SPOTenantRestrictedSearchAllowedList -SitesList <List[string]> [<CommonParameters>]
```

```powershell
Add-SPOTenantRestrictedSearchAllowedList -SitesListFileUrl <string> [-ContainsHeader <bool>]  
 [<CommonParameters>]
```

**Example 1**

```powershell
Add-SPOTenantRestrictedSearchAllowedList -SitesList @("[https://contoso.sharepoint.com/sites/Marketing](https://contoso.sharepoint.com/sites/Marketing)", "[https://contoso.sharepoint.com/sites/Benefits](https://contoso.sharepoint.com/sites/Benefits)")
```

This example shows the admin how to add the sites to the allow list.

**Example 2**

```powershell
Add-SPOTenantRestrictedSearchAllowedList  -SitesListFileUrl C:\Users\admin\Downloads\UrlList.csv
```

Note

To generate a list of all your SharePoint site URLs, go to your SharePoint online admin center, go to **Active Sites**, and select **export**. The exported list includes classic sites as well. Remove any sites from this list that you don't want indexed. You can include up to 100 URLs.

This example shows the admin how to add the sites to the allow list by providing a CSV file. Add the list of site URLs in the URL column.

**Parameters**

`-SitesList`

Site list for allow list.

| Type | String |
| --- | --- |
| Position: | `0` |
| Default Value: | `None` |
| Required: | `True` |
| Accept Pipeline input: | `False` |
| Accept wildcard characters: | `False` |

`-SitesListFileURL`

File that has list of site URLs that you can add to an allow list when the tenant is set to Restricted Tenant Search Mode.

| Type | String |
| --- | --- |
| Position: | `0` |
| Default Value: | `None` |
| Required: | `True` |
| Accept Pipeline input: | `False` |
| Accept wildcard characters: | `False` |

## Remove sites from the allow list

Remove sites from the allow list by providing the site URL in a string or CSV file by using the following PowerShell command:

```powershell
Remove-SPOTenantRestrictedSearchAllowedList
```

**Module:**[Microsoft.Online.SharePoint.PowerShell](/en-us/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell)

**Applies to:** SharePoint Online

**Syntax**

```powershell
Remove-SPOTenantRestrictedSearchAllowedList -SitesList <List[string]> [<CommonParameters>]
```

```powershell
Remove-SPOTenantRestrictedSearchAllowedList -SitesListFileUrl <string> [-ContainsHeader <bool>]
 [<CommonParameters>]
```

**Example 1**

```powershell
Remove-SPOTenantRestrictedSearchAllowedList -SitesList @("[https://contoso.sharepoint.com/sites/Marketing](https://contoso.sharepoint.com/sites/Marketing)", "[https://contoso.sharepoint.com/sites/HR](https://contoso.sharepoint.com/sites/HR)")
```

Example 1 shows how the admin removes the sites from the allow list.

**Example 2**

```powershell
Remove-SPOTenantRestrictedSearchAllowedList -SitesListFileUrl C:\Users\admin\Downloads\UrlList.csv
```

Example 2 shows how the admin adds the sites to the allow list by providing a CSV file.

**Parameters**

`-SitesList`

Site list that you want to remove from the allow list.

| Type | String |
| --- | --- |
| Position: | `0` |
| Default Value: | `None` |
| Required: | `True` |
| Accept Pipeline input: | `False` |
| Accept wildcard characters: | `False` |

`-SitesListFileURL`

File that has list of sites that you can remove from an allow list when the tenant is set to Restricted Tenant Search Mode.

| Type | String |
| --- | --- |
| Position: | `0` |
| Default Value: | `None` |
| Required: | `True` |
| Accept Pipeline input: | `False` |
| Accept wildcard characters: | `False` |

## Get the existing list of URLs in the allow list

To get the existing list of URLs in the allow list, run the following PowerShell command:

```powershell
Get-SPOTenantRestrictedSearchAllowedList
```

**Module:**[Microsoft.Online.SharePoint.PowerShell](/en-us/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell)

**Applies to:** SharePoint Online

**Syntax**

```powershell
Get-SPOTenantRestrictedSearchAllowedList
```

**Example**

```powershell
Get-SPOTenantRestrictedSearchAllowedList
```

This example shows how the admin gets the existing allow list in the tenant.