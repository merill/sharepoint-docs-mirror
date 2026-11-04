---
layout: Conceptual
title: Restrict SharePoint site access with Microsoft 365 groups and Microsoft Entra security groups - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/restricted-access-control
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-07-30T00:00:00.0000000Z
ms.reviewer: nibandyo
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
customer-intent: As a SharePoint administrator, I want to restrict access to specific SharePoint sites and content by security groups.
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.custom:
- has-azure-ad-ps-ref
ms.collection:
- M365-collaboration
- M365-sam
- Highpri
- Tier2
- ContentEngagementFY24
- trust-pod
search.appverid: 
description: Learn how to restrict access to SharePoint sites to members of a Microsoft 365 or Microsoft Entra security group.
locale: en-us
document_id: d2a6bba1-8b74-6bf5-ba60-3871122334d6
document_version_independent_id: c607ed10-e61d-ed04-3b44-d7e07ca8d934
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/restricted-access-control.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: restricted-access-control
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/restricted-access-control.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
platformId: 95895a5a-633e-873d-e38f-b97ebecf78cb
---

# Restrict SharePoint site access with Microsoft 365 groups and Microsoft Entra security groups - SharePoint in Microsoft 365 | Microsoft Learn

Restricted site access control (also referred to as *restricted access control* or *site access restriction*) helps prevent oversharing by designating access of SharePoint sites and its content to users in the specific control group. Users not in the specified group can't access the site or its content, even if they had prior permissions or a shared link. You can apply this policy on Microsoft 365 group-connected, Teams-connected, nongroup connected sites, and OneDrive by using Microsoft 365 groups or Microsoft Entra security groups.

Site access restriction policy take effect when a user attempts to open a site or access a file. Copilot and organization wide search results also honor the policy. Users with direct permissions to the file but not in the specified control group will not be able to view the file in search or Copilot experiences.

[![Screenshot of saved changes for restricted access control for SharePoint sites.](sharepointonline/media/sam-overview/3-restricted-access-control-sharepoint-sites.png)](sharepointonline/media/sam-overview/3-restricted-access-control-sharepoint-sites.png#lightbox)

Note

Shared channel sites and private channel sites are separate site collections from the Microsoft 365 group-connected site used by standard channels. Restricted site access policies applied to a team-connected site don't automatically apply to its shared or private channel sites. Configure site access restriction separately for each shared or private channel site.

## Prerequisites for restricted site access

See [Prerequisites for SharePoint Advanced Management](sharepoint-advanced-management-prerequisites).

## Enable site-level access restriction for your organization

You must enable site-level access restriction for your organization before you can configure it for individual sites. You can also delegate site access restriction control to all the site admins of your organization.

To enable site-level access restriction for your organization in the SharePoint admin center, follow these steps:

1. Expand **Policies** and select **Access control**.
2. Select **Site-level access restriction**.
3. Select **Allow access restriction** and then select **Save**.

    [![Screenshot showing how to set up site level access control.](sharepointonline/media/restricted-access-control/access-control-site-level-restriction.png)](sharepointonline/media/restricted-access-control/access-control-site-level-restriction.png#lightbox)

To enable site-level access restriction for your organization using PowerShell, run the following command:

```Powershell
Set-SPOTenant -EnableRestrictedAccessControl $true
```

It might take up to one hour for the command to take effect.

## Delegate management of restricted access control to site admins

As a SharePoint administrator, you can also delegate management of restricted access control to site administrators. If they update the policy, they need to provide appropriate justification on why the policy is being updated.

By default, the delegation is turned off. If you decide to enable it, run the following command:

```Powershell
Set-SPOTenant -DelegateRestrictedAccessControlManagement $true
```

Once restricted access control is delegated to all the site admins, they can manage the policy.

## Check status of delegate management of restricted access control to site admins

To check the delegation status, run the following command:

```Powershell
Get-SPOTenant | Select-Object DelegateRestrictedAccessControlManagement
```

Note

For Microsoft 365 Multi-Geo users, run this command separately for each desired geo-location.

## Restrict access to all SharePoint sites using Microsoft 365 group or Microsoft Entra security groups

You can restrict access to a SharePoint site by specifying Microsoft Entra security groups or Microsoft 365 groups as the restricted access control group. The control group should include the users who are allowed access to the site and its content.

For a site, you can configure up to 10 Microsoft Entra security groups or Microsoft 365 groups. Once you apply the policy, users in the specified group who have access permission to the content are granted access.

Important

- Adding people to the restricted access control group (Microsoft Entra security group or Microsoft 365 group) doesn't automatically give the users access permission to the site or the content. For a user to access the content protected by this policy, the user needs both the site or content access permission and be a member of the restricted access control group.
- You can also use dynamic security groups as a restricted access control group if you want to base group membership on user properties.

### Manage site access for a site

To manage site access for a site, follow these steps:

1. In SharePoint admin center, expand **Sites** and select **Active sites**.
2. Select the site you want to manage. The site details panel appears.
3. In the **Settings** tab, select **Edit** in the **Restricted site access** section.
4. Select the **Restrict SharePoint site access to only users in specified groups** check box.
5. Add or remove your security groups or Microsoft 365 groups and select **Save**.

### Apply site access restriction to a site

To apply site access restriction to the site, you must add at least one group to the site access restriction policy.

[![screenshot showing site access restriction security groups being added to nongroup connected sites.](sharepointonline/media/rac-spac/non-group-connected-sites/restricted-access-control-non-group-connected-site-page.png)](sharepointonline/media/rac-spac/non-group-connected-sites/restricted-access-control-non-group-connected-site-page.png#lightbox)

For a group connected site, the Microsoft 365 group connected to the site is the default restricted access control group. You can choose to keep this group and add more Microsoft 365 or Microsoft Entra Security groups as a restricted access control group.

[![screenshot showing site access restriction security groups being added to connected sites.](sharepointonline/media/rac-spac/7-rac-group-connected.png)](sharepointonline/media/rac-spac/7-rac-group-connected.png#lightbox)

Note

- This behavior doesn't apply to shared channel sites or private channel sites because they aren't connected to the parent team's Microsoft 365 group. Configure restricted access control separately for those sites. See the section Shared and private channel sites (in this article).
- A **Default group** tag is listed for the Microsoft 365 group connected to the site, as shown in the preceding image.

## Manage site access restriction by using PowerShell

To manage site access restriction for a SharePoint site by using PowerShell, use the PowerShell commands described in this section.

### Enable site access restriction

```powershell
Set-SPOSite -Identity <siteurl> -RestrictedAccessControl $true
```

### Add group

```powershell
Set-SPOSite -Identity <siteurl> -AddRestrictedAccessControlGroups <comma separated group GUIDS>
```

### Edit group

```powershell
Set-SPOSite -Identity <siteurl> -RestrictedAccessControlGroups <comma separated group GUIDS>
```

### View group

```powershell
Get-SPOSite -Identity <siteurl> | Select RestrictedAccessControl, RestrictedAccessControlGroups
```

### Remove group

```powershell
Set-SPOSite -Identity <siteurl> -RemoveRestrictedAccessControlGroups <comma separated group GUIDS>
```

### Reset site access restriction

```powershell
Set-SPOSite -Identity <siteurl> -ClearRestrictedAccessControl
```

## Search and Copilot experience

Restricted site access control policy is honored in organization-wide search experiences and Microsoft Copilot experiences. Users who are denied access due to this policy can't view content from this site in either search or Microsoft Copilot experiences. It can take some time for search and Copilot experiences to reflect Restricted site access control policies. The search index update latency depends on the number of items in a site. For example, larger sites with more items can take longer for Restricted site access control policies to be honored in search and Copilot experiences.

## Shared and private channel sites

Shared and private channel sites are separate from the Microsoft 365 group-connected site that standard channels use. Because shared and private channel sites aren't connected to the parent team's Microsoft 365 group, Restricted access control policies configured on the team-connected site don't apply to those channel sites. You must enable site access restriction for each shared or private channel site separately as nongroup connected sites.

For shared channel sites, restricted access control applies only to internal users in the resource tenant. External participants accessing the shared channel from another tenant aren't evaluated against the restricted access control policy. Their access continues to be determined by the permissions granted to the shared channel and the associated SharePoint site.

This means that adding an external shared channel participant to, or removing them from, a restricted access control group doesn't affect their ability to access the shared channel site.

Important

Adding people to the security group or Microsoft 365 group doesn't give users access to the channel in Teams. Add or remove the same users of the Teams channel in Teams and the security group or Microsoft 365 group, so users have access to both Teams and SharePoint sites.

## Site admin experience

After you delegate the site access restriction control to site admins, they can configure the site access restriction setting at the **Site Information** panel.

[![Screenshot showing the Restricted Site Access setting.](sharepointonline/media/restricted-access-control/site-admin.png)](sharepointonline/media/restricted-access-control/site-admin.png#lightbox)

### Restrict access to a SharePoint site

1. Limit who can access a site by using Microsoft Entra security groups or Microsoft 365 groups.
2. Add the groups that contain the users who should have access.
3. Add up to 10 groups for each site.
4. When you save the site access restriction setting configuration, only users in those groups and users who already have permission to the content can access the site.
5. Provide justification whenever you update the site access restriction setting.

### Site owner experience

After you apply the policy to the site, the **Site access** panel displays the policy status and all configured control groups for site owners, in addition to the **Site Information** and **Permissions** panels.

[![screenshot showing site access restriction panel.](sharepointonline/media/rac-spac/8-rac-site-access-panel.png)](sharepointonline/media/rac-spac/8-rac-site-access-panel.png#lightbox)

## Auditing

The Microsoft Purview portal provides audit events that help you monitor site access restriction activities. The system logs audit events for the following activities:

- Applying site access restriction for a site
- Removing site access restriction for a site
- Changing site access restriction groups for a site
- Site admin's justification for updating site access restriction

## Insights

### Restricted site access policy insights

As an IT administrator, you can view the following reports to gain more insight about SharePoint sites protected with restricted site access policy:

- Sites protected by restricted site access policy (`RACProtectedSites`)
- Details of access denials due to restricted site access policy (`ActionsBlockedByPolicy`)

Reports are currently unavailable for Microsoft 365 operated by 21Vianet, even if you have the required licenses.

Note

It can take a few hours to generate each report.

### Sites protected by restricted site access policy report

Run the following commands in SharePoint PowerShell to generate, view, and download the reports.

#### Generate report

```powershell
Start-SPORestrictedAccessForSitesInsights -RACProtectedSites
```

This command generates a list of sites protected by restricted site access policy.

#### View report

```powershell
Get-SPORestrictedAccessForSitesInsights -RACProtectedSites -ReportId <Report GUID>
```

The report shows the top 100 sites with the highest page views that are protected by the policy.

#### Download report

```powershell
Get-SPORestrictedAccessForSitesInsights -RACProtectedSites -ReportId <Report GUID> -Action Download
```

Run this command as an administrator. The downloaded report is located on the path where the command was run.

#### Percentage of site protected with restricted site access report

```powershell
Get-SPORestrictedAccessForSitesInsights -RACProtectedSites -ReportId <Report GUID> -InsightsSummary
```

This report shows the percentage of sites that are protected by the policy out of the total number of sites.

### Access denials due to restricted site access policy report

Run the following commands to create, fetch, and view a report for access denials due to restricted site access reports.

#### Create access denials report

```powershell
Start-SPORestrictedAccessForSitesInsights -ActionsBlockedByPolicy
```

This command creates a new report for fetching access denial details.

#### Fetch access denials report status

```powershell
Get-SPORestrictedAccessForSitesInsights -ActionsBlockedByPolicy
```

This command fetches the status of the generated report.

#### Latest access denials in the past 28 days

```powershell
Get-SPORestrictedAccessForSitesInsights -ActionsBlockedByPolicy -ReportId <Report ID> -Content AllDenials
```

This command gets a list of the most recent 100 access denials that occurred in the past 28 days.

#### View list of top users who were denied access

```powershell
Get-SPORestrictedAccessForSitesInsights -ActionsBlockedByPolicy -ReportId <Report ID> -Content TopUsers
```

This command gets a list of the top 100 users who received the most access denials.

#### View list of top sites that received the most access denials

```powershell
Get-SPORestrictedAccessForSitesInsights -ActionsBlockedByPolicy -ReportId <Report ID> -Content TopSites
```

This command gets a list of the top 100 sites that had the most access denials.

#### Distribution of access denials across different types of sites

```powershell
Get-SPORestrictedAccessForSitesInsights -ActionsBlockedByPolicy -ReportId <Report ID> -Content SiteDistribution
```

Shows the distribution of access denials across different types of sites.

Note

To view up to 10,000 denials, you must download the reports. Run the download command as an administrator. The downloaded reports are located on the path where you run the command.

## Sharing of site and content with users outside of restricted access control groups (opt-in capability)

By default, sharing SharePoint sites and their content doesn't follow the restricted site access policy. The SharePoint administrator can choose to restrict sharing of a site and its content with users who aren't members of the restricted access control group.

To restrict the sharing capability to users outside of the restricted access control group, run the following PowerShell command in SharePoint Online Management Shell as an administrator:

```powershell
Set-SPOTenant -AllowSharingOutsideRestrictedAccessControlGroups $false
```

### Sharing with users

When you apply the sharing restriction, it blocks sharing for users who aren't members of the restricted access control group.

[![screenshot of sharing with users message.](sharepointonline/media/rac-spac/rac-share-with-users.png)](sharepointonline/media/rac-spac/rac-share-with-users.png#lightbox)

### Sharing with groups

Sharing is allowed with Microsoft Entra Security or Microsoft 365 groups that are part of the restricted access control groups list. Sharing isn't allowed with all other groups, including Everyone except external users or SharePoint groups.

[![screenshot of sharing with groups message.](sharepointonline/media/rac-spac/rac-share-with-groups.png)](sharepointonline/media/rac-spac/rac-share-with-groups.png#lightbox)

Note

Sharing of a site and its content is now allowed for the nested security groups that are part of the restricted access control groups.

## Configure the Learn more link for access denial error page (opt-in capability)

Configure the **Learn more** link to inform users who are denied access to a SharePoint site due to the restricted site access control policy. By customizing this error link, you can provide more information and guidance to your users.

Note

The **Learn more** link is a tenant-level setting that applies to all sites with the restricted access control policy enabled.

To configure the link, run the following command in SharePoint PowerShell:

```powershell
Set-SPOTenant -RestrictedAccessControlForSitesErrorHelpLink "<Learn more URL>" 
```

To fetch the value of the link, run the following command:

```powershell
Get-SPOTenant | select RestrictedAccessControlForSitesErrorHelpLink 
```

The configured **Learn more** link launches when the user selects the **Know more about your organization's policies here** link.

[![Screenshot showing the learn more link.](sharepointonline/media/rac-spac/2-rac-learn-more-link.png)](sharepointonline/media/rac-spac/2-rac-learn-more-link.png#lightbox)