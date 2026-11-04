---
layout: Conceptual
title: Restrict access to a user's OneDrive content to people in a group - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/onedrive-site-access-restriction
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-07-01T00:00:00.0000000Z
ms.reviewer: nibandyo
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
customer-intent: As a SharePoint administrator, I want to restrict access to an individual user's OneDrive content to users in a security group or Microsoft 365 group by using a site access restriction policy.
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: onedrive
ms.localizationpriority: medium
ms.collection:
- Strat_OD_admin
- Highpri
- Tier2
- M365-sam
- M365-collaboration
- essentials-compliance
- essentials-security
search.appverid: 
ms.assetid: 
ms.custom:
- admindeeplinkSPO
description: Learn how to allow only users in specified security groups to access a user's OneDrive content.
locale: en-us
document_id: 7eb588d2-15ce-4f3f-7b4b-b70bd30b23c7
document_version_independent_id: a9a7e6a2-f7aa-f12f-dd16-b936f812e154
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/onedrive-site-access-restriction.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: onedrive-site-access-restriction
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/onedrive-site-access-restriction.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 3b0599ca-c42c-e227-4e5b-95100d0fb7db
---

# Restrict access to a user's OneDrive content to people in a group - SharePoint in Microsoft 365 | Microsoft Learn

You can restrict access to an individual user's OneDrive content to users in a security group or Microsoft 365 group by using a site access restriction policy. Users not in the specified group can't access the content, even if they had prior permissions or shared link.

Apply the policy by using [Microsoft Entra security groups](/en-us/azure/active-directory/fundamentals/how-to-manage-groups) or Microsoft 365 groups that contain the people who should be able to access files in that OneDrive.

When you apply the policy, the people in the specified groups aren't granted permissions to any files directly. The OneDrive owner must share the content as they normally would. The site access restriction policy prevents anyone who isn't in the security group or the Microsoft 365 group from accessing the OneDrive content even if it's shared with them.

Access restriction policies are applied when a user attempts to access a file. Users can still see files in search results if they have direct permissions to the file, but they can't access the file if they're not part of the specified group.

You can also restrict access to the OneDrive service itself to people in a security group. For more information, see [Restrict OneDrive access by security group](limit-access).

## Before you begin

Make sure your organization meets the [Prerequisites for SharePoint Advanced Management](sharepoint-advanced-management-prerequisites), including requirements for [SharePoint Online PowerShell module](sharepoint-advanced-management-prerequisites#sharepoint-online-powershell-module).

## Enable site access restriction for your organization

You must enable site access restriction for your organization before you can configure it for a user's OneDrive.

To enable site access restriction for your organization in SharePoint admin center:

1. Expand **Policies** and select **Access control**.
2. Select **Site access restriction**.
3. Select **Allow access restriction** and then select **Save**.

    [![screenshot of site access restriction in sharepoint admin center dashboard.](sharepointonline/media/rac-spac/1-rac-spac-dashboard-feb-2024.png)](sharepointonline/media/rac-spac/1-rac-spac-dashboard-feb-2024.png#lightbox)

To enable site access restriction for your organization using PowerShell, run the following command:

```Powershell
Set-SPOTenant -EnableRestrictedAccessControl $true
```

It might take up to one hour for command to take effect.

Note

For Microsoft 365 Multi-Geo users, run this command separately for each desired geo-location.

## Restrict access to a user's OneDrive content

Assign up to 10 Microsoft Entra security or Microsoft 365 groups to each OneDrive. After you add a group, only users in the groups can access content in that OneDrive that you shared with them. Use [dynamic security groups](/en-us/azure/active-directory/enterprise-users/groups-create-rule) if you want to base group membership on user properties.

Important

The owner of the OneDrive must be included in one of the security or Microsoft 365 groups that you specify or they lose access to their OneDrive and its contents.

To manage access restriction for OneDrive, use the PowerShell commands in this section.

### Enable access restriction for a given OneDrive library

Run the following command before adding security or Microsoft 365 groups.

```powershell
Set-SPOSite -Identity <siteurl> -RestrictedAccessControl $true
```

### Add a security group or a Microsoft 365 group

Run the following command:

```powershell
Set-SPOSite -Identity <siteurl> -AddRestrictedAccessControlGroups <comma separated group GUIDS>
```

### Edit a security group or a Microsoft 365 group

Run the following command:

```powershell
Set-SPOSite -Identity <siteurl> -RestrictedAccessControlGroups <comma separated group GUIDS>
```

### View a security group or a Microsoft 365 group

Run the following command:

```powershell
Get-SPOSite -Identity <siteurl> Select RestrictedAccessControl, RestrictedAccessControlGroups
```

### Remove a security group or a Microsoft 365 group

Run the following command:

```powershell
Set-SPOSite -Identity <siteurl> -RemoveRestrictedAccessControlGroups <comma separated group GUIDS>
```

### Reset site access restriction

Run the following command:

```powershell
Set-SPOSite -Identity <siteurl> -ClearRestrictedAccessControl
```

## Site sharing and restricted site access policies

Block OneDrive site sharing for users and groups who aren't allowed as per the restricted access control policy.

The sharing control functionality is disabled by default. To enable it, run the following command:

```powershell
Set-SPOTenant -AllowSharingOutsideRestrictedAccessControlGroups $false 
```

### Sharing with users

Allow sharing only with users who are part of restricted access control groups. Block sharing with anyone outside of the restricted access control groups as shown in the following image:

### Sharing with groups

You can share with Microsoft Entra Security or Microsoft 365 groups that are part of the restricted access control groups list. You can't share with all other groups, including Everyone except external users or SharePoint groups.

Note

Currently, you can't share a site and its content with nested security groups that are part of the restricted access control groups.

## Configure learn more link for access denial error page

Configure your "learn more" link to inform users who were denied access to a OneDrive site because of a restricted site access control policy. By using this customizable error link, you can provide more information and guidance to your users.

Note

The "learn more" link is a tenant-level setting that applies to all OneDrive sites that have restricted access control policy enabled.

### Configure the "learn more" link

Run the following command:

```powershell
Set-SPOTenant -RestrictedAccessControlForSitesErrorHelpLink "<Learn more URL>" 
```

### Fetch the value of the link

Run the following command:

```powershell
Get-SPOTenant | select RestrictedAccessControlForSitesErrorHelpLink 
```

The configured learn more link launches when the user selects the **Know more about your organization's policies here** link.

## Restricted site access policy insights

As an IT administrator, you can view the following reports to gain more insight about OneDrive sites protected with restricted site access policy:

- Sites protected by restricted site access policy (RACProtectedSites)
- Details of access denials due to restricted site access (ActionsBlockedByPolicy)

Note

It can take a few hours to generate each report.

### Sites protected by restricted site access policy report

Use the following commands to generate, view, and download reports.

#### Generate a report

Run the following command:

```powershell
Start-SPORestrictedAccessForSitesInsights -RACProtectedSites
```

This command generates a list of sites protected by restricted site access policy.

#### View a report

Run the following command:

```powershell
Get-SPORestrictedAccessForSitesInsights -RACProtectedSites -ReportId <Report GUID>
```

This command creates a report that shows the top 100 sites with the highest page views that are protected by the policy.

#### Download a report

Run the following command:

```powershell
Get-SPORestrictedAccessForSitesInsights -RACProtectedSites -ReportId <Report GUID> -Action Download
```

This command must be run as an administrator. The downloaded report is located in the path where the command was run.

#### View the percentage of sites protected with restricted site access

Run the following command:

```powershell
Get-SPORestrictedAccessForSitesInsights -RACProtectedSites -ReportId <Report GUID> -InsightsSummary
```

This report shows the percentage of sites that are protected by the policy out of the total number of sites.

### Access denials due to restricted site access policy

Use the commands in this section to create, fetch, and view reports for access denials due to restricted site access reports.

### To create an access denials report

Run the following command:

```powershell
Start-SPORestrictedAccessForSitesInsights -ActionsBlockedByPolicy
```

This command creates a new report for fetching access denial details.

### To get the status of an access denials report

Run the following command:

```powershell
Get-SPORestrictedAccessForSitesInsights -ActionsBlockedByPolicy
```

This command fetches the status of the generated access denials report.

### To see the latest access denials in the past 28 days

Run the following command:

```powershell
Get-SPORestrictedAccessForSitesInsights -ActionsBlockedByPolicy -ReportId <Report ID> -Content AllDenials
```

This command creates a list of the most recent 100 access denials that occurred in the past 28 days.

### To view a list of top users who were denied access

Run the following command:

```powershell
Get-SPORestrictedAccessForSitesInsights -ActionsBlockedByPolicy -ReportId <Report ID> -Content TopUsers
```

This command creates a list of the top 100 users who received the most access denials.

### To view a list of top sites that received the most access denials

Run the following command:

```powershell
Get-SPORestrictedAccessForSitesInsights -ActionsBlockedByPolicy -ReportId <Report ID> -Content TopSites
```

This command creates a list of the top 100 sites that had the most access denials.

### To see the distribution of access denials across different types of sites

Run the following command:

```powershell
Get-SPORestrictedAccessForSitesInsights -ActionsBlockedByPolicy -ReportId <Report ID> -Content SiteDistribution
```

This command shows the distribution of access denials across different types of sites.

Note

To view up to 10,000 denials, download the reports. Run the download command as an administrator. The downloaded reports are located in the path from where the command was run.

## Auditing

The [Microsoft Purview portal](https://purview.microsoft.com) provides audit events that help you monitor site access restriction activities. The system logs audit events for the following activities:

- Applying site access restriction for a site
- Removing site access restriction for a site
- Changing site access restriction groups for a site