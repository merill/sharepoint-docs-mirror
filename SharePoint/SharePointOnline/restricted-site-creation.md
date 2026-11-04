---
layout: Conceptual
title: Restrict OneDrive and SharePoint site creation by users - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/restricted-site-creation
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-09-02T00:00:00.0000000Z
ms.reviewer: vgaddam
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
customer-intent: As a SharePoint administrator, I want to restrict users from creating specified types of OneDrive and SharePoint sites.
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Highpri
- Tier2
- M365-sam
- M365-collaboration
- essentials-manage
- trust-pod
search.appverid: 
description: Learn how to restrict users from creating specified types of OneDrive and SharePoint sites using restricted site creation.
locale: en-us
document_id: 5a7391a7-5bba-35b6-880e-33979a9c4ebc
document_version_independent_id: a1759ab6-bc45-4e3a-5fd5-85730fbe1259
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/restricted-site-creation.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: restricted-site-creation
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/restricted-site-creation.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
platformId: be3c07ee-b9a7-b178-9c32-426d17667b5d
---

# Restrict OneDrive and SharePoint site creation by users - SharePoint in Microsoft 365 | Microsoft Learn

The restricted site creation feature IT administrators use [SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell#getting-started-with-sharepoint-online-powershell) to designate which Microsoft Entra security groups in their tenant can create OneDrive and SharePoint sites.

You can choose between two ways to manage site creation within your tenant: deny mode (the specified groups can't create sites) and allow mode (only the specified groups can create sites). When you enable this feature for your tenant, restricted site creation defaults to **deny** mode.

Restricted site creation policies only control site provisioning capabilities and not site access permissions.

## Prerequisites

Your organization needs **SharePoint Advanced Management Plan 1**. See [Prerequisites: SharePoint Advanced Management Plan 1 add-on](sharepoint-advanced-management-prerequisites#microsoft-copilot-or-the-sharepoint-advanced-management-plan-1-add-on).

Also see the requirements for the [SharePoint Online PowerShell module](sharepoint-advanced-management-prerequisites#sharepoint-online-powershell-module).

## Site types for restricted site creation by users

Each restricted site creation policy includes a *site type* specifying the types of sites users in the specified groups are either allowed or denied from creating.

| Site type | Applies to |
| --- | --- |
| All | OneDrive and all SharePoint sites |
| SharePoint | All SharePoint sites (but not OneDrive) |
| OneDrive | Only OneDrive |
| Team | Only SharePoint team sites (classic) |
| Communication | Only SharePoint communication sites |

You can specify up to 10 Microsoft Entra security groups for each site type.

## How do restricted site creation deny and allow modes work?

The restricted site creation by users mode is shared across all site type policies. You can't use deny mode for one site type and allow mode for a different site type.

When you set restricted site creation by users to **deny** mode, users can't create a site if they belong to any security group configured for a site type that matches the site they want to create. For example, if a user is in a group listed under the All, SharePoint, or Communication site types, they can't create a SharePoint communication site.

When you set restricted site creation by users to **allow** mode, users can only create a site if they belong to a security group configured for a site type that matches the site they want to create. For example, a user can create a OneDrive site only if they're in a group listed under the All or OneDrive site types.

## Current limitations of restricted site creation by users

- Only Microsoft Entra security groups (mail-enabled or non-mail-enabled) are supported at this time.
- You can configure up to 10 security groups per site type.
- This feature isn't currently available for Microsoft 365 government cloud environments, such as GCC, GCC-High, DoD, or Microsoft 365 operated by 21Vianet.

## Manage restricted site creation by users

The [Set-SPORestrictedSiteCreation](/en-us/powershell/module/microsoft.online.sharepoint.powershell/set-sporestrictedsitecreation?view=sharepoint-ps&amp;preserve-view=true) and [Get-SPORestrictedSiteCreation](/en-us/powershell/module/microsoft.online.sharepoint.powershell/get-sporestrictedsitecreation?view=sharepoint-ps&amp;preserve-view=true) commands allow administrators to configure and view the restricted site creation feature and policies for the tenant.

Important

You must use version 16.0.25513.12000 (published November 2024) or later of the SharePoint Online Management Shell for these commands to function properly. Earlier versions don't have the current list of site types and don't operate correctly.

### Enable restricted site creation by users

To enable restricted site creation by users, run the following command in the SharePoint Online Management Shell:

```powershell
Set-SPORestrictedSiteCreation -Enabled $true
```

Restricted site creation by users starts in deny mode without any policies, and doesn't affect any users by default.

### Set Allow or Deny mode for restricted site creation by users

After you turn on the restricted site creation by users feature, decide whether you want to deny certain groups of users from creating sites or allow certain groups to create sites.

For example, the following command sets restricted site creation to deny mode:

```powershell
Set-SPORestrictedSiteCreation -Mode Deny
```

Important

Swapping between the two modes removes all existing site type configurations. The restricted site creation feature only supports either all deny or all allow configurations.

### Configure policies for site types

You can specify a comma-separated list of up to 10 Microsoft Entra security groups for each site type. For example, if restricted site creation is in deny mode, the following command creates a policy blocking users in either of the following two groups from creating any SharePoint site.

```powershell
Set-SPORestrictedSiteCreation -SiteType SharePoint -RestrictedSiteCreationGroups "00aa00aa-bb11-cc22-dd33-44ee44ee44ee,11bb11bb-cc22-dd33-ee44-55ff55ff55ff"
```

Note

You must specify Microsoft Entra security groups by using the Object ID shown in the [Microsoft Entra admin center](/en-us/entra/fundamentals/how-to-manage-groups).

To clear the configuration for a site type, specify **""** for the RestrictedSiteCreationGroups:

```powershell
Set-SPORestrictedSiteCreation -SiteType All -RestrictedSiteCreationGroups ""
```

### View configuration

Use the following command to view the existing restricted site creation configurations:

```powershell
Get-SPORestrictedSiteCreation
```

## What messages do users see when restricted from site creation?

When a user is blocked from creating a site by a restricted site creation by users policy, they receive a message depending on the type of site they're creating and how they're creating it. See the following examples for reference:

### Example 1: User can't create a communication site

When a user creates a communication site from the web, they see the error message "Due to organizational policies, you can't create this type of site."

[![Screenshot of failed communication site creation.](sharepointonline/media/restricted-site-creation/1-restricted-site-creation-sharepoint.png)](sharepointonline/media/restricted-site-creation/1-restricted-site-creation-sharepoint.png#lightbox)

### Example 2: User can't create a team site

When a user creates a team site from the web, the user sees the message "We're still setting up the site for this group," but the site isn't created.

[![Screenshot of failed OneDrive site creation if created from admin UI.](sharepointonline/media/restricted-site-creation/3-restricted-site-creation-onedrive-created-admin-ui.png)](sharepointonline/media/restricted-site-creation/3-restricted-site-creation-onedrive-created-admin-ui.png#lightbox)

### Example 3: User can't access OneDrive

When first signing in to their OneDrive from the web, the user sees the error message "You can't make a OneDrive. If you need one, contact your administrator or help desk."

[![Screenshot of failed OneDrive site creation.](sharepointonline/media/restricted-site-creation/2-restricted-site-creation-onedrive.png)](sharepointonline/media/restricted-site-creation/2-restricted-site-creation-onedrive.png#lightbox)

### Example 4: User can't create a site using PowerShell

When creating sites through the SharePoint Online Management Shell, the cmdlet fails with the exception "Due to organizational policies, you can't create this type of site."