---
layout: Conceptual
title: Restrict discovery of SharePoint sites and content - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/restricted-content-discovery
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-10-11T00:00:00.0000000Z
ms.reviewer: nibandyo
manager: dansimp
ms.author: deniseb
author: denisebmsft
audience: Admin
customer-intent: As a SharePoint administrator, I want to restrict the discovery of specific SharePoint sites and content.
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.custom:
- has-azure-ad-ps-ref
ms.collection:
- M365-collaboration
- M365-sam
- Tier2
- trust-pod
search.appverid: 
description: Learn how to restrict the discovery of SharePoint sites from Microsoft Copilot and tenant-wide search.
locale: en-us
document_id: 7cfd7903-7802-3e73-8ee4-0f75328ad89a
document_version_independent_id: ed410f8b-b775-4882-09e3-ecf509e96469
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/restricted-content-discovery.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: restricted-content-discovery
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/restricted-content-discovery.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
platformId: 568ea04b-ef55-f5ee-1dcd-033a8190f9d3
---

# Restrict discovery of SharePoint sites and content - SharePoint in Microsoft 365 | Microsoft Learn

Organizations preparing for Microsoft Copilot often need time to review SharePoint sites, validate permissions, and implement governance controls before making content broadly discoverable. Restricted Content Discovery helps you limit discovery of content from specific SharePoint sites, including recently interacted files, in organization-wide search results and Microsoft Copilot responses while those reviews are taking place.

Restricted Content Discovery also removes AI-powered entry points from these SharePoint sites. Users don't see entry points such as the Copilot button, AI actions menus (including creating agents), or **Create pages with AI**. This restriction helps reduce the likelihood of accidental discovery of content while permissions and governance controls are being evaluated.

When a site has a Restricted Content Discovery policy applied to it, a Restricted tag is visible, as shown in the following screenshot:

[![Screenshot showing the Restricted marker for a site covered by Restricted Content Discovery.](sharepointonline/media/restricted-content-discovery/restricted-marker.png)](sharepointonline/media/restricted-content-discovery/restricted-marker.png#lightbox)

Restricted Content Discovery is designed as a temporary governance control that gives organizations time to review and right-size access while continuing their Copilot deployment.

Note

- Restricted Content Discovery doesn't change existing permissions. Users who already have access to content can continue to access that content directly.
- You can only apply this feature to SharePoint sites. It's not supported for OneDrive sites.
- Restricted Content Discovery doesn't affect searches that originate from site context or other intelligent experiences such as Microsoft 365 Feed and Recommendations.

Caution

Use Restricted Content Discovery selectively. Excessive use can reduce the amount of content available to organization-wide search and Microsoft Copilot experiences, which can affect the completeness and relevance of search results and AI-generated responses.

## When to use Restricted Content Discovery

Use Restricted Content Discovery for sites that might need extra review before they become broadly discoverable through organization-wide search and Microsoft Copilot experiences.

Common scenarios include:

- Sites with a high risk of oversharing.
- Sites undergoing permissions review.
- Phased Microsoft Copilot rollouts.
- Governance initiatives that require content validation before wider discovery.

For example, you might temporarily apply Restricted Content Discovery to a group of Finance or Human Resources sites while site owners review permissions and access. After the review is complete, you can remove the restriction and allow the sites to become discoverable again.

Before enabling Restricted Content Discovery, consider using one or more of the following tools and reports to identify sites that require review:

- [SharePoint Admin Agent](content-governance-agent)
- [Content management assessment](content-management-assessment)
- [Data Access Governance reports](data-access-governance-reports)
- [Catalog management](/en-us/sharepoint/catalog-management)

## How Restricted Content Discovery works

Restricted Content Discovery is a site-level setting. When you turn on the setting, Microsoft 365 search systems propagate it so that content from the site doesn't appear in organization-wide discovery experiences.

Even when Restricted Content Discovery is enabled:

- Site permissions stay the same.
- Users can continue to access content they already have permission to access.
- The feature doesn't remove content from the Microsoft 365 search index.

Because the setting must propagate across indexing systems, updates can take time to become fully effective. The amount of time depends on site size, the number of files in each site, and the number of concurrent updates being processed.

## Prerequisites

Before configuring Restricted Content Discovery:

1. Review the [SharePoint Advanced Management prerequisites](sharepoint-advanced-management-prerequisites), including:

    - [SharePoint Online PowerShell module requirements](sharepoint-advanced-management-prerequisites#sharepoint-online-powershell-module)
    - [Role-based access control (RBAC) role assignments](sharepoint-advanced-management-prerequisites#role-based-access-control-rbac-role-assignments)
2. Ensure your organization has a [Microsoft Copilot license](/en-us/microsoft-365/copilot/microsoft-365-copilot-licensing). Restricted Content Discovery is intended for Microsoft Copilot deployment and governance scenarios.
3. Review your organization's existing categories, and if necessary, add categories. See [Catalog management](/en-us/sharepoint/catalog-management).

## Enable Restricted Content Discovery for a site

You can enable Restricted Content Discovery from the SharePoint admin center or by using PowerShell.

Note

Updates can take time to propagate throughout search and Microsoft Copilot experiences.

### Use the SharePoint admin center

1. In the SharePoint admin center, expand **Sites** and select **Active sites**.
2. Select the site you want to configure.
3. Open the **Settings** tab, and then turn **Restrict content from Microsoft Copilot** on.

    [![Screenshot of the settings tab where you can enable Restricted Content Discovery.](sharepointonline/media/restricted-content-discovery/settings-tab-active-site.png)](sharepointonline/media/restricted-content-discovery/settings-tab-active-site.png#lightbox)
4. Select **Save**.

### Use PowerShell

Open PowerShell as an administrator and run the following command:

```powershell
Set-SPOSite -Identity <site-url> -RestrictContentOrgWideSearch $true
```

## Remove Restricted Content Discovery from a site

To disable Restricted Content Discovery for a site, open PowerShell as an administrator and run the following command:

```powershell
Set-SPOSite -Identity <site-url> -RestrictContentOrgWideSearch $false
```

## Delegate management to site administrators

By default, only SharePoint administrators can manage Restricted Content Discovery.

If you want site administrators to manage the setting for their own sites, enable delegation by using the following PowerShell command:

```powershell
Set-SPOTenant -DelegateRestrictedContentDiscoverabilityManagement $true
```

To verify delegation status, run:

```powershell
Get-SPOTenant | Select-Object DelegateRestrictedContentDiscoverabilityManagement
```

When delegation is enabled, site administrators can manage Restricted Content Discovery for their sites.

[![Screenshot showing the Restrict content from Microsoft Copilot setting.](sharepointonline/media/restricted-content-discovery/configuration-by-site-admin.png)](sharepointonline/media/restricted-content-discovery/configuration-by-site-admin.png#lightbox)

If a site administrator makes a change to Restricted Content Discovery settings, they must provide a justification for the change.

[![Screenshot showing the Justication required dialog box.](sharepointonline/media/restricted-content-discovery/justification-by-site-admin.png)](sharepointonline/media/restricted-content-discovery/justification-by-site-admin.png#lightbox)

## Check Restricted Content Discovery status for a site

Open PowerShell as an administrator and run the following command:

```powershell
Get-SPOSite -Identity <site-url> | Select RestrictContentOrgWideSearch
```

## Monitor Restricted Content Discovery across your tenant

Administrators can use PowerShell to generate reports that identify sites where Restricted Content Discovery is enabled.

### Generate a report

Open PowerShell as an administrator and run the following command:

```powershell
Start-SPORestrictedContentDiscoverabilityReport
```

### View report status

Open PowerShell as an administrator and run the following command:

```powershell
Get-SPORestrictedContentDiscoverabilityReport
```

### Download a report

Open PowerShell as an administrator and run the following command:

```powershell
Get-SPORestrictedContentDiscoverabilityReport -Action Download -ReportId <ReportGUID>
```

Tip

If a site is configured for Restricted Content Discovery but continues to appear in search results, allow time for index propagation and review the number of items stored in the site. Large sites can require extra processing time before changes are fully reflected.

## Auditing

You can view audit events through [Microsoft Purview audit log activities](/en-us/purview/audit-log-activities) for activities involving Restricted Content Discovery.

These events include:

- Enabling Restricted Content Discovery.
- Disabling Restricted Content Discovery.
- Justifications provided when updates are made to the setting.

## Frequently asked questions

### Is my organization eligible to use Restricted Content Discovery?

You can configure Restricted Content Discovery if your organization is licensed for Copilot and has SharePoint Advanced Management available. See [Prerequisites for SharePoint Advanced Management](sharepoint-advanced-management-prerequisites).

### Does Restricted Content Discovery change user permissions?

No. Restricted Content Discovery affects discoverability, not access permissions. Users who already have access to content can continue to access it.

### What search experiences are affected?

Restricted Content Discovery affects organization-wide search experiences (SharePoint home, Office.com, Bing) and Microsoft Copilot discovery scenarios, including experiences that rely on tenant-wide content discovery. Restricted Content Discovery doesn't affect experiences that operate on content that's already in use by the user, such as summarizing an open document.

### How does Restricted Content Discovery affect the end user experience in SharePoint?

Restricted Content Discovery restricts usage of AI-powered features in SharePoint. Users don't see entry points such as the Copilot button, AI actions menus (including creating agents), or **Create pages with AI**.

### Does Restricted Content Discovery affect Microsoft Purview features?

No. Restricted Content Discovery doesn't remove content from the search index. Microsoft Purview capabilities such as eDiscovery and auto-labeling continue to function.

### How long does it take for updates to Restricted Content Discovery to take effect?

Restricted Content Discovery is a site-level property. Index update latency is highly dependent on the number of items in the site and the number of sites getting updated at the same time. For sites with more than 500,000 items, an update to Restricted Content Discovery could take more than a week to fully process and reflect in search and Copilot experiences.

### How does Restricted Content Discovery fit into a Copilot readiness strategy?

Restricted Content Discovery helps organizations temporarily limit discovery of selected sites while permissions, ownership, and governance controls are reviewed. It's one component of a broader SharePoint governance and Copilot readiness strategy. See [Secure and govern Microsoft Copilot: Foundational deployment guidance](/en-us/microsoft-365/copilot/secure-govern-copilot-foundational-deployment-guidance).