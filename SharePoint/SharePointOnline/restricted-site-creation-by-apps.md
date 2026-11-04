---
layout: Conceptual
title: Restrict OneDrive and SharePoint site creation by apps - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/restricted-site-creation-by-apps
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-05-14T00:00:00.0000000Z
ms.reviewer: vgaddam
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
customer-intent: As a SharePoint administrator, I want to restrict apps from creating specified types of SharePoint and OneDrive sites.
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
description: Learn how to restrict apps from creating specified types of OneDrive and SharePoint sites using restricted site creation.
locale: en-us
document_id: f757fadb-c9f7-7c9a-a7e2-1944d064cb03
document_version_independent_id: 6955b3ee-300e-61dd-0b14-45117ed0cf4d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/restricted-site-creation-by-apps.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: restricted-site-creation-by-apps
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/restricted-site-creation-by-apps.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: e4d63948-8d4f-f2cb-20ba-ad147a567a01
---

# Restrict OneDrive and SharePoint site creation by apps - SharePoint in Microsoft 365 | Microsoft Learn

The **Restricted Site Creation by Apps** feature lets SharePoint Administrators use the [SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell#getting-started-with-sharepoint-online-powershell) to designate which third-party apps can create SharePoint sites in your organization.

You can choose between two ways to manage site creation for apps within your tenant:

- **Deny** mode (the specified apps are unable to create sites)
- **Allow** mode (only the specified apps are allowed to create sites).

When you enable restricted site creation for apps in your tenant, the default mode is set to **deny**.

Keep in mind that these policies only control which apps can create new sites; these policies don't affect site access permissions for users or apps.

Note

- The Restrict OneDrive and SharePoint site creation by apps feature is currently in preview.
- Admins can create separate configurations for the following categories of sites: All sites (including OneDrives), all SharePoint sites (not including OneDrives), OneDrives, Team sites (Group connected and classic), and Communication sites.
- The Restricted site creation for apps feature has a simulation mode parameter to test hypothetical scenario for policy configuration. -The Restricted site creation for apps feature only affects only non-Microosft (third-party) apps. First-party apps aren't affected.

## Prerequisites for restricted site creation

- Your organization must have **SharePoint Advanced Management Plan 1**, an add-on for Microsoft 365. See [Prerequisites for SharePoint Advanced Management](sharepoint-advanced-management-prerequisites), including requirements for the [SharePoint Online PowerShell module](sharepoint-advanced-management-prerequisites#sharepoint-online-powershell-module)
- Make sure you can configure apps that are allowed to create SharePoint sites.

## To get App IDs

Some of the PowerShell commands you'll use call for App IDs. To create your list, follow these steps:

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com/) as at least a [Cloud Application Administrator](/en-us/entra/identity/role-based-access-control/permissions-reference#cloud-application-administrator).
2. Browse to **Entra ID** &gt; **Enterprise apps** &gt; **All applications**.
3. Select the application you want, and view its Application ID.

## Connect to the SharePoint Online Management Shell

1. If you haven't already done so, [download the latest SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588).

    Note

    If you installed a previous version of the SharePoint Online Management Shell, go to **Add or remove programs** and uninstall "SharePoint Online Management Shell" first. Then, install the latest version.
2. Connect to SharePoint as a SharePoint Administrator or SharePoint Advanced Management Administrator. For more information, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

## Use the restricted site creation PowerShell commands

### To enable site access restriction

```powershell
Set-SPORestrictedSiteCreationForApps –Enabled $true
```

### To allow apps to create sites

```powershell
Set-SPORestrictedSiteCreationForApps –Mode Allow
```

### To prevent apps from creating sites

```powershell
Set-SPORestrictedSiteCreationForApps –Mode Deny
```

### To add or reconfigure the App ID list

```powershell
Set-SPORestrictedSiteCreationForApps -SiteType <SiteType> -RestrictedSiteCreationApps <comma separated app IDs>
```

### To view your Restricted Sites App list

```powershell
Get-SPORestrictedSiteCreationForApps -SiteType <SiteType>
```

## Site types for restricted site creation for apps

Specify `SiteType` parameter when you update and view the App ID list. Here's the SiteType parameter list:

| Site type | Applies to |
| --- | --- |
| All | OneDrive and all SharePoint sites |
| SharePoint | All SharePoint sites (but not OneDrive) |
| OneDrive | Only OneDrive |
| Team | Only SharePoint team sites (group-connected and classic) |
| Communication | Only SharePoint communication sites |

Note

**All Sites** includes all sites except for any template listed in the following table. The *All Sites* SiteType overrides all others.

| Type | Template Name | Template ID | Reason |
| --- | --- | --- | --- |
| SharePoint Embedded | `CSPCONTAINER` | 70 | SharePoint Embedded experience is managed separately |
| Redirect site | `REDIRECTSITE` | 301 | Critical SharePoint functionality |
| My Site Host | `MYSITEHOST` | 54 | Core site |
| Tenant Admin | `TENANTADMIN` | 16 | Core site |

## How deny and allow modes work

The restricted site creation for apps mode is shared across all site type policies. It isn't possible to use deny mode for one site type and allow mode for a different site type.

When restricted site creation for apps is in **deny** mode, an app is blocked from creating a site if its App ID is in any list configured with any site type, which applies to the site it's attempting to create. For example, an app is blocked from creating a SharePoint communication site if its App ID is in any list configured with the All, SharePoint, or Communication site types.

When restricted site creation for apps is in **allow** mode, an app is only allowed to create a site if its App ID is in a list configured with a site type, which applies to the site it's attempting to create. For example, an app can create a OneDrive if its App ID is in a list configured with the All or OneDrive site types.

Note

Changing the mode from deny to allow prompts a message: "Are you sure you want to switch from Deny to Allow? Switching will remove all current configuration of restrictions." A similar message appears when you switch from allow to deny mode as well.

## Specify the App IDs in the Restricted Sites App list

When you specify App IDs in the Restricted Sites App list, the command replaces the current list with the app IDs that you specify. You can't add or remove individual app IDs. Each time you run the command, it replaces the previous list with a new list for that site type.

**To avoid removing access for other apps, always include all app IDs you want to allow in your command.**

Here are some examples.

### Example 1: Allow only one app to create sites

Suppose we want to allow only one app to create sites. The app has ID `281e395b-7316-4cb2-b5bb-8881426ee411`. We'd use the following command:

```powershell
Set-SPORestrictedSiteCreationForApps –SiteType "All" -RestrictedSiteCreationApps "281e395b-7316-4cb2-b5bb-8881426ee411"
```

This command replaces the existing list with just the specified app ID. Only this app is able to create sites of type "All".

### Example 2: Update the list of apps that are allowed to create team sites

Suppose we want to update the list of apps that can create team sites. We'd use the following command:

```powershell
Set-SPORestrictedSiteCreationForApps –SiteType "Team" -RestrictedSiteCreationApps "78159241-04a9-41d2-8dd4-ac568e9766a3,1f95829b-e1c8-4406-b2be-508c36f4bca5"
```

This command replaces the current list of allowed apps for Team sites with only the specified app IDs.