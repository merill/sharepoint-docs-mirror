---
layout: Conceptual
title: Manage Data access governance reports using SharePoint Online PowerShell - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/powershell-for-data-access-governance
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-07-30T00:00:00.0000000Z
ms.reviewer: pullabhk
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
f1.keywords: NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Strat_SP_admin
- Highpri
- Tier2
- M365-sam
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
search.appverid: MET150
description: Learn about how to use SharePoint Online PowerShell module to manage Data access governance reports
ai-usage: ai-assisted
locale: en-us
document_id: e9e539e4-579f-2de6-5111-4a40fbb760be
document_version_independent_id: ef312b6e-73fb-1cd8-8c69-37daa230a011
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/powershell-for-data-access-governance.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: powershell-for-data-access-governance
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/powershell-for-data-access-governance.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/5cf46315-b33f-4e99-8224-a1592697eff9
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/715d24c3-3683-4219-82c5-1e3c813fb7fc
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: 1da07f55-fdee-fe2c-8878-0b2ef9fde7d8
---

# Manage Data access governance reports using SharePoint Online PowerShell - SharePoint in Microsoft 365 | Microsoft Learn

While [Data access governance](/en-us/sharepoint/data-access-governance-reports) is available in the SharePoint admin center, some organizations prefer to use PowerShell to manage settings at scale through scripting and automation. This article describes how to use the SharePoint Online PowerShell module to manage Data access governance reports.

## Before you begin

Make sure your organization meets the [Prerequisites for SharePoint Advanced Management](sharepoint-advanced-management-prerequisites), including [SharePoint Online PowerShell module requirements](sharepoint-advanced-management-prerequisites#sharepoint-online-powershell-module).

PowerShell support for Data access governance is available from module `Microsoft.Online.SharePoint.PowerShell` and version `16.0.25409` or later.

When you connect to SharePoint, run the [Connect-SPOService](/en-us/powershell/module/microsoft.online.sharepoint.powershell/connect-sposervice?view=sharepoint-ps&amp;preserve-view=true) command *without* the **Credential** parameter. In line with security best practices, signing in by using the credential parameter isn't supported.

## Create reports by using PowerShell

For general PowerShell syntax, parameters, and examples, see [Start-SPODataAccessGovernanceInsight](/en-us/powershell/module/microsoft.online.sharepoint.powershell/start-spodataaccessgovernanceinsight?view=sharepoint-ps&amp;preserve-view=true).

For specific report examples, see the following sections in this article.

## Generate a site permission state report

You need to understand the permissions setup in your organization, particularly in the wake of Copilot adoption, as it respects user and content permissions. Copilot's data exposure risk increases with the number of users having permissions or access. The site permission state report provides deep insights into potential exposure, based on the unique number of users who have permissions to every SharePoint and OneDrive site in your organization.

Run this report first to get a quick overview of permissions in your organization. This report is a snapshot report. It provides the latest snapshot or status of the entire organization as of the report generation date.

To generate a report for all your SharePoint sites, run the following command:

```powershell
Start-SPODataAccessGovernanceInsight -ReportEntity PermissionedUsers -ReportType Snapshot -Workload SharePoint -CountOfUsersMoreThan 0  -Name "OrgWidePermissionedUsersReportSharePoint"
```

To generate a report for all your OneDrive for business accounts, run the following command:

```powershell
Start-SPODataAccessGovernanceInsight -ReportEntity PermissionedUsers -ReportType Snapshot -Workload OneDriveForBusiness -CountOfUsersMoreThan 0  -Name "OrgWidePermissionedUsersReportODB"
```

Keep these important points in mind about the report:

- Because these reports are comprehensive and likely to cover all data in your tenant, you can create up to two reports. You can create one report per workload.
- The first report always takes up to five days to complete, regardless of the size of your organization. Subsequent reports complete within 24 hours.
- These reports capture data up to 48 hours before the report generation.
- Once generated, you can run these reports again once every 30 days.

These commands generate a list of all sites where at least one user can access any content within the site. For more information about how to interpret the report, see [How to view the site permissions for your organization report](/en-us/sharepoint/data-access-governance-site-permissions-report#how-to-view-the-site-permissions-for-your-organization-report).

Once you understand the extent of oversharing in your tenant, you can track further deviations specifically from active sites in last 28 days. You can generate reports on sites that are active in key factors of potential oversharing such as "Sharing links" or content shared with "Everyone except external users" in the last 28 days.

## Generate a user permission state report

While the site permission report for the entire organization helps you understand the current state of permissions in the entire tenant, some scenarios require discovering sites accessible to a given user. For more information, see [Get your organization's site permissions baseline with the snapshot report](/en-us/sharepoint/data-access-governance-site-permissions-users-report). The following section describes how data access governance helps you generate such a report by using PowerShell.

First, fetch the UPN or User principal name of the user for whom you want to generate the report by using the [Get-MgUser](/en-us/powershell/module/microsoft.graph.users/get-mguser) command. Then run the following PowerShell command, which triggers the report listing SharePoint sites accessible to those users.

```powershell
Start-SPODataAccessGovernanceInsight -ReportEntity PermissionsReport -ReportType Snapshot -Workload SharePoint -Name "UserSharePointReport" -UserEmailList "a@contoso.com","b@contoso.com"
```

Important

While the parameter is named `UserEmailList`, the report requires user principal names. You can include up to 100 users in a single request.

To list OneDrive accounts accessible to the given users, specify the workload as `OneDriveForBusiness`.

```powershell
Start-SPODataAccessGovernanceInsight -ReportEntity PermissionsReport -ReportType Snapshot -Workload OneDriveForBusiness -Name "UserOneDriveReport" -UserEmailList "a@contoso.com","b@contoso.com"
```

## Generate a report on sites and files shared via special SharePoint groups

The site permission reports tell you which sites are overshared. To find the exact items where the special groups "Everyone except external users" (EEEU) or "Everyone" are the recipients, generate this report. For more information about the report and how to interpret its output, see [Get item-level permission details for "Everyone except external users" and "Everyone"](data-access-governance-detailed-eeeu-everyone-permissions-report).

Important

This report requires module `Microsoft.Online.SharePoint.PowerShell` version `16.0.27215.12000` or later, published April 30, 2026. You also need the SharePoint Advanced Management Administrator role, which a Global administrator must assign. For more information, see [Assign the SharePoint Advanced Management Administrator role](/en-us/sharepoint/sharepoint-advanced-management-prerequisites?branch=pr-en-us-8933#role-based-access-control-rbac-role-assignments).

To generate the report for EEEU, run the following command:

```powershell
Start-SPODataAccessGovernanceInsight -ReportEntity EveryoneExceptExternalUsers -ReportType Snapshot
```

To generate the report for Everyone, change the **ReportEntity** parameter value:

```powershell
Start-SPODataAccessGovernanceInsight -ReportEntity Everyone -ReportType Snapshot
```

Keep these important points in mind about the report:

- The report doesn't take a **Workload** parameter. The output covers both SharePoint and OneDrive.
- The output file is limited to 1 million rows.
- Permissions granted to EEEU or Everyone for system files and system groups aren't included.

To track the report and download the results, see Track reports by using PowerShell and View and download reports by using PowerShell.

## Generate a sensitivity label in files report with PowerShell

Run this PowerShell command to trigger the report to list sites where specific items were labeled with a given label, as of the report generation date.

First, retrieve the label name or label GUID by using the [Security & Compliance PowerShell module](/en-us/powershell/exchange/scc-powershell?view=exchange-ps&amp;preserve-view=true).

```powershell
Get-Label | Format-Table -Property DisplayName, Name, GUID, ContentType
```

Then, use the name and GUID to retrieve sites with files labeled with the given label name or GUID.

```powershell
Start-SPODataAccessGovernanceInsight -ReportEntity SensitivityLabelForFiles -Workload SharePoint -ReportType Snapshot -FileSensitivityLabelGUID "a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1" -FileSensitivityLabelName Secret
```

Note

Currently, the report for `OneDriveForBusiness` accounts with labeled files isn't supported.

## Generate sharing link activity reports

Use sharing link activity reports to identify sites that are active in collaboration and need quicker intervention to mitigate any potential oversharing risk. These recent activity based reports identify sites that generate the most sharing links in the last 28 days.

Generate the following sharing link activity reports:

- Sites that created **Anyone** sharing links in the last 28 days
- Sites that created **People in your organization** sharing links in the last 28 days
- Sites that created **Specific people** (guests) sharing links in the last 28 days

### Report on **Anyone** sharing links created in last 28 days

```powershell
Start-SPODataAccessGovernanceInsight -ReportEntity SharingLinks_Anyone -Workload SharePoint -ReportType RecentActivity
```

Provide the workload value as `OneDriveForBusiness` to get all OneDrive accounts with the same criteria.

### Report on PeopleInYourOrg sharing links created in the last 28 days

```powershell
Start-SPODataAccessGovernanceInsight -ReportEntity SharingLinks_PeopleInYourOrg -Workload SharePoint -ReportType RecentActivity
```

Provide the workload value as `OneDriveForBusiness` to get all OneDrive accounts with the same criteria.

### Report on specific people (guests) sharing links created in the last 28 days

```powershell
Start-SPODataAccessGovernanceInsight -ReportEntity SharingLinks_Guests -Workload SharePoint -ReportType RecentActivity
```

Provide the workload value as `OneDriveForBusiness` to get all OneDrive accounts with the same criteria.

## Identify content shared with "Everyone except external users" in last 28 days

While sharing links can contribute to potential oversharing, another key contributor is "Everyone except external users" (EEEU). EEEU makes content public (visible to the entire organization) and makes it easy for others to discover content and get access. These reports identify sites that actively used EEEU at various scopes in the last 28 days.

You can generate the following EEEU activity reports:

- Sites shared with Everyone except external users in last 28 days
- Items shared with Everyone except external users in last 28 days

Important

Currently, the EEEU report for OneDrive for Business only supports the item level. EEEU reports for OneDrive for Business at the site level aren't supported. If you don't have a Microsoft SharePoint Advanced Management license, you must enable data collection for recent activity based reports so that relevant audit data is collected to build the report. After you enable it, the data is collected and stored for 28 days. You can generate the report 24 hours later, and it contains data from the point of collection. If you don't generate reports even once in three months, data collection is paused and you must enable it again. To enable data collection for these reports, see the section Manage data collection for recent activity based reports.

### Identify sites shared with "Everyone except external users" in last 28 days

When you add EEEU to a site membership (owners, members, or visitors), the entire content of the site becomes public and more prone to oversharing. Run the following PowerShell command to trigger the report to capture such sites in the last 28 days for SharePoint sites:

```powershell
Start-SPODataAccessGovernanceInsight -ReportEntity EveryoneExceptExternalUsersAtSite -Workload SharePoint -ReportType RecentActivity -Name "PublicSiteViaEEEU"
```

### Identify items shared with "Everyone except external users" in last 28 days

Run the following PowerShell command to trigger the report to capture specific items (files, folders, or lists) that you shared with EEEU in the last 28 days for SharePoint sites:

```powershell
Start-SPODataAccessGovernanceInsight -ReportEntity EveryoneExceptExternalUsersForItems -Workload SharePoint -ReportType RecentActivity -Name "PublicItemsViaEEEU"
```

Note

Replace the workload value with `OneDriveForBusiness` to get items shared with "Everyone except external users" for all OneDrive accounts with the same criteria.

## Manage data collection for recent activity based reports

Important

If you don't have a Microsoft SharePoint Advanced Management license, you must enable data collection for recent activity based reports so that relevant audit data is collected to build the report. After you enable it, you can generate the report 24 hours later, and it will contain data from the point of collection. Data is stored for 28 days. If you don't generate reports even once in three months, data collection is paused and you must enable it again.

### Enable data collection for recent activity based reports

This PowerShell command starts collecting audit data for reports on activities from the last 28 days.

```powershell
Start-SPOAuditDataCollectionForActivityInsights -ReportEntity SharingLinks_Anyone
```

The applicable values for the ReportEntity parameter are SharingLinksAnyone, SharingLinksPeopleInYourOrg, SharingLinksGuests, EveryoneExceptExternalUsersAtSite, EveryoneExceptExternalUsersForItems, CopilotAppInsights

### Disable data collection for recent activity based reports

This PowerShell command stops collecting audit data for reports on activities from the last 28 days.

```powershell
Stop-SPOAuditDataCollectionForActivityInsights -ReportEntity SharingLinks_Anyone
```

### Check the data collection status for recent activity based reports

Once data collection is enabled, the reports can be generated after 24 hours. To check whether reports can be generated, use the PowerShell command [Get-SPOAuditDataCollectionStatusForActivityInsights](/en-us/powershell/module/microsoft.online.sharepoint.powershell/get-spoauditdatacollectionstatusforactivityinsights?view=sharepoint-ps&amp;preserve-view=true). The command returns the current data collection status, which can be `NotInitiated`, `InProgress`, or `Paused`. Reports can be generated when the status is `InProgress`.

```powershell
Get-SPOAuditDataCollectionStatusForActivityInsights -ReportEntity SharingLinks_Anyone
```

## Track reports by using PowerShell

Important

Each report creation returns a GUID that you can use to track the report status.

```powershell
Start-SPODataAccessGovernanceInsight -ReportEntity SensitivityLabelForFiles -Workload SharePoint -ReportType Snapshot -FileSensitivityLabelGUID "a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1" -FileSensitivityLabelName Secret
```

```console
ReportId                             Status
--------                             ------
a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1 NotStarted
```

Use the [Get-SPODataAccessGovernanceInsight](/en-us/powershell/module/microsoft.online.sharepoint.powershell/get-spodataaccessgovernanceinsight?view=sharepoint-ps&amp;preserve-view=true) command to get the current status of a specific Data access governance report by using the report ID.

```powershell
Get-SPODataAccessGovernanceInsight -ReportID a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1
```

```console
ReportId          : a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1
ReportEntity      : SharingLinks_Anyone
Status            : InQueue
Workload          : SharePoint
TriggeredDateTime : 11/13/2024 19:32:34
CreatedDateTime   : 11/13/2024 20:09:23
ReportStartTime   : 10/17/2024 19:32:33
ReportEndTime     : 11/13/2024 19:32:33
ReportType        : RecentActivity
SitesFound        : 120
```

The `ReportStartTime` and `ReportEndTime` show the period of data for the report. The status changes to `Completed` when the report generation finishes.

You can also view the current status of DAG reports by using the filter `ReportEntity` instead of ID. The `reportID` appears in the output and is needed later to download a specific report.

```powershell
Get-SPODataAccessGovernanceInsight -ReportEntity PermissionedUsers
```

```console
ReportId             : a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1
ReportName           : PermissionReportFor1AsOfSept
ReportEntity         : PermissionedUsers
Status               : Completed
Workload             : SharePoint
TriggeredDateTime    : 09/18/2024 11:06:16
CreatedDateTime      : 09/22/2024 12:12:48
ReportType           : Snapshot
CountOfUsersMoreThan : 1
CountOfSitesInReport : 7
CountOfSitesInTenant : 22
Privacy              : All
Sensitivity          : {All}
Templates            : {All}

ReportId             : b1b1b1b1-cccc-dddd-eeee-f2f2f2f2f2f2
ReportName           : PermissionReportFor1AsOfOct
ReportEntity         : PermissionedUsers
Status               : Completed
Workload             : SharePoint
TriggeredDateTime    : 10/09/2024 14:15:40
CreatedDateTime      : 10/09/2024 15:18:23
ReportType           : Snapshot
CountOfUsersMoreThan : 100
CountOfSitesInReport : 0
CountOfSitesInTenant : 26
Privacy              : All
Sensitivity          : {All}
Templates            : {All}
```

## View and download reports by using PowerShell

To download a specific report, you need the reportID. Get the reportID by using the [Get-SPODataAccessGovernanceInsight](/en-us/powershell/module/microsoft.online.sharepoint.powershell/get-spodataaccessgovernanceinsight?view=sharepoint-ps&amp;preserve-view=true) command. Then, use the [Export-SPODataAccessGovernanceInsight](/en-us/powershell/module/microsoft.online.sharepoint.powershell/export-spodataaccessgovernanceinsight?view=sharepoint-ps&amp;preserve-view=true) command to download the report to a path you specify.

```powershell
Export-SPODataAccessGovernanceInsight -ReportID a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1 -DownloadPath "C:\Users\TestUser\Documents\DAGReports"
```

This command downloads a CSV file to the path you specify. You can find details about the CSV and view for each report in [How to access the Data access governance reports in the SharePoint admin center](/en-us/sharepoint/data-access-governance-reports#how-to-access-the-data-access-governance-reports-in-the-sharepoint-admin-center).

Note

The default download path is the **Downloads** folder.

## Perform remedial actions by using PowerShell

After you generate data access governance reports, you can perform remedial actions as described in [Remedial actions from Data access governance reports](/en-us/sharepoint/data-access-governance-reports#remedial-actions-from-data-access-governance-reports).

The following section describes PowerShell commands to initiate and track site access reviews as a remedial action.

### Initiate site access review by using PowerShell

Use the [Start-SPOSiteReview](/en-us/powershell/module/microsoft.online.sharepoint.powershell/start-spositereview?view=sharepoint-ps&amp;preserve-view=true) command to initiate a site access review for a specific site, listed under a data access governance report. The data access governance report provides the context under which you should initiate the review. Retrieve the report ID and site ID from the CSV file and provide comments to give clarity to the site owner regarding the purpose of the review.

```powershell
Start-SPOSiteReview -ReportID a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1 -SiteID c2c2c2c2-dddd-eeee-ffff-a3a3a3a3a3a3 -Comment "Check for org wide access"
```

```console
ReviewId                : a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1
SiteId                  : c2c2c2c2-dddd-eeee-ffff-a3a3a3a3a3a3
ReviewInitiatedDateTime : 13-11-2024 20:55:41
ReportEntity            : PermissionedUsers
Status                  : Pending
AdminComment            : Check for org wide access
SiteName                : All Company
```

This command generates emails to site owner as described in [How to initiate a site access review](/en-us/sharepoint/site-access-review#how-to-initiate-a-site-access-review).

Important

You can initiate up to 1,000 site access reviews per calendar month from the **Site permissions across your organization** report. This limit resets at the start of each new month.

### Track site access reviews by using PowerShell

Use [Start-SPOSiteReview](/en-us/powershell/module/microsoft.online.sharepoint.powershell/start-spositereview?view=sharepoint-ps&amp;preserve-view=true) command to track the status of site access reviews. For specific reviews, use the `ReviewID` value as shown in the output. To retrieve all reviews related to a reporting module, use the `ReportEntity` parameter.

```powershell
Get-SPOSiteReview -ReportEntity PermissionedUsers
```

```console
ReviewId                : a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1
SiteId                  : c2c2c2c2-dddd-eeee-ffff-a3a3a3a3a3a3
ReviewInitiatedDateTime : 13-11-2024 20:55:41
ReviewCompletedDateTime :
ReportCreatedDateTime   : 13-11-2024 23:25:41
ReportEndDateTime       : 13-11-2024 23:25:41
ReportEntity            : PermissionedUsers
Status                  : Pending
AdminComment            : Check for org wide access
SiteName                : All Company
ReviewerEmail           :
ReviewerComment         :

ReviewId                : a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1
SiteId                  : c2c2c2c2-dddd-eeee-ffff-a3a3a3a3a3a3
ReviewInitiatedDateTime : 24-10-2024 11:07:39
ReviewCompletedDateTime : 15-11-2024 11:07:39
ReportCreatedDateTime   : 15-10-2024 09:24:47
ReportEndDateTime       : 15-10-2024 11:39:52
ReportEntity            : PermissionedUsers
Status                  : Completed
AdminComment            : Check for org wide access
SiteName                : All Company
ReviewerEmail           : Jon@contosofinance.com
ReviewerComment         : Removed EEEU for sensitive documents
```