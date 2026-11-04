---
layout: Conceptual
title: Get Insights report on agents in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/insights-on-sharepoint-agents
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-05-13T00:00:00.0000000Z
ms.reviewer: pullabhk
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
f1.keywords: NOCSH
ms.topic: article
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Strat_SP_admin
- Highpri
- Tier2
- M365-sam
- M365-collaboration
- trust-pod
ms.custom:
- admindeeplinkSPO
search.appverid: 
description: In this article, you learn about how to create and view insights on agents created in SharePoint.
locale: en-us
document_id: 3f67b5d6-0be2-adef-6fc2-119c1d45c844
document_version_independent_id: 08cce8c5-bffa-25fb-1596-fbfed70b69eb
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/insights-on-sharepoint-agents.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: insights-on-sharepoint-agents
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/insights-on-sharepoint-agents.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: f8ab9473-3a3b-e6a7-6f7d-71c1dfe7f569
---

# Get Insights report on agents in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn

The insights report on agents in SharePoint provides SharePoint administrators with rich information on the recently created agents across all SharePoint sites and OneDrive sites within their organization. This report helps admins learn about the sites with the highest number of agents created. By using this report, SharePoint admins can further govern and maintain the integrity of the content used by agents as grounding data.

The insights report is based on the Microsoft audit data logged for the agents created in SharePoint through the FileCreated and FileRenamed events.

You can generate and manage the agent insights report in SharePoint Admin Center or by using SharePoint Online Management Shell.

## What you need to access agent insights report

See [SharePoint Advanced Management prerequisites](sharepoint-advanced-management-prerequisites).

Important

If you don't have a Microsoft SharePoint Advanced Management license, you're asked to enable data collection so that relevant audit data is collected to build the report. Once enabled, you can generate the reports 24 hours later and they contain data from the point of collection. Data is stored for 28 days. If you don't generate reports at least once in three months, data collection pauses and you need to enable it again. To enable data collection for these reports, see the Data collection for insights report on agents in SharePoint section (in this article).

## How to access agent insights report in SharePoint Admin Center

1. Sign in to the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219) with the [SharePoint administrator](/en-us/sharepoint/sharepoint-admin-role) credentials for your organization.
2. In the navigation pane, expand **Reports** and then select **Agent Insights**.

### How to create reports in SharePoint Admin Center

1. As a SharePoint Administrator, select **Create a report** to create the report.

    [![Screenshot showing how to create a report on SharePoint agent insights.](sharepointonline/media/agent-insights/create-report.png)](sharepointonline/media/agent-insights/create-report.png#lightbox)
2. Enter the report name. Under **Report duration**, specify the time frame for the report.

    [![Screenshot showing how to specify the report time frame.](sharepointonline/media/agent-insights/create-report-time-frame.png)](sharepointonline/media/agent-insights/create-report-time-frame.png#lightbox)
3. Select **Create and run**.

Note

You can create a report for the past 1, 7, 14, or 28 days.

### View report status in SharePoint Admin Center

To check if a report is ready or when it was last updated, see the **Status** column.

[![Screenshot showing report status.](sharepointonline/media/agent-insights/reports-status.png)](sharepointonline/media/agent-insights/reports-status.png#lightbox)

### View report in SharePoint Admin Center

When a report is ready, select it to view the data. You can view the top 100 records hosting the highest number of agents. You can search for sites or filter on the site template, and governance policies.

[![Screenshot showing the agent report.](sharepointonline/media/agent-insights/agent-report.png)](sharepointonline/media/agent-insights/agent-report.png#lightbox)

### Apply content governance policies in SharePoint Admin Center

You can apply content governance policies on the sites from the insights report. The available policies are [Restrict site access policy](/en-us/SharePoint/restricted-access-control) and [Restrict Content Discovery policy](/en-us/sharepoint/restricted-content-discovery).

[![Screenshot showing how to apply RCD.](sharepointonline/media/agent-insights/rcd-lightbox.png)](sharepointonline/media/agent-insights/rcd-lightbox.png#lightbox)

Note

After you apply a policy to the site from the insights report, the policy status on the existing report doesn't update. To view the updated status of the policy on the site, select the policy to view the latest status or access the Active site panel and review the site settings.

## Agent insights report in SharePoint Online Management Shell

You can generate and manage agent insights reports by using SharePoint Online Management Shell.

1. If you haven't already done so, download and install the latest version of [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588).
2. Connect to SharePoint Online as at least a [SharePoint administrator](/en-us/sharepoint/sharepoint-admin-role) in Microsoft 365. For more information, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
3. To generate and view these reports, ensure the organization has the SharePoint Advanced Management add-on SKU or Microsoft Copilot license.

With permissions of at least a SharePoint administrator, you can generate and view the insights report by using the following commands:

1. To generate a report for the default one-day report duration, run the following command:

    ```powershell
    Start-SPOCopilotAgentInsightsReport
    ```
2. To generate a report for any other duration (7, 14, or 28 days), run the following command:

    ```powershell
    Start-SPOCopilotAgentInsightsReport -ReportPeriodInDays
    ```

    For example, to generate a report for the past 28 days, run the command:

    ```powershell
    Start-SPOCopilotAgentInsightsReport -ReportPeriodInDays <28>
    ```
3. To check the status of all active and available reports, run the following command:

    ```powershell
    Get-SPOCopilotAgentInsightsReport
    ```
4. To check the status of a specific report, run the following command:

    ```powershell
    Get-SPOCopilotAgentInsightsReport –ReportId
    ```
5. To download and view the report, run the following command:

    ```powershell
    Get-SPOCopilotAgentInsightsReport –ReportId -Action Download
    ```

    Note

    PowerShell displays up to 100 records, but downloaded reports can contain up to 1 million records.

    ```powershell
    Get-SPOCopilotAgentInsightsReport –ReportId -Action View
    ```
6. To view more detailed reports, use the following options:

    1. `CopilotAgentsOnSites`: Provides the name of all the agents currently available on all sites. This report contains up to 1,000,000 records.

        Note

        The default value for the `-Content` parameter is `CopilotAgentsOnSites`.

        ```powershell
        Get-SPOCopilotAgentInsightsReport –ReportId -Content CopilotAgentsOnSites
        ```
    2. `TopSites`: Provides a list of 100 sites with the number of agents available on each site.

        ```powershell
        Get-SPOCopilotAgentInsightsReport –ReportId -Content TopSites
        ```
    3. `SiteDistribution`: Provides the summarized view of agents across all types of sites like Communication sites, Microsoft 365 Group connected sites, OneDrive sites, and more.

        ```powershell
        Get-SPOCopilotAgentInsightsReport –ReportId -Content SiteDistribution
        ```

### Data collection for insights report on agents in SharePoint

If you don't have a Microsoft SharePoint Advanced Management license, you need to enable data collection. This section explains how to enable and check the status of data collection for the Insights report on agents in SharePoint.

#### Enable data collection

This PowerShell command starts collecting audit data for reports on activities from the last 28 days.

```powershell
Start-SPOAuditDataCollectionForActivityInsights  
```

#### Disable data collection

This PowerShell command stops collecting audit data for reports on activities from the last 28 days.

```powershell

Stop-SPOAuditDataCollectionForActivityInsights  
```

#### Check the data collection status

After you enable data collection, you can generate the reports after 24 hours. To check whether you can generate reports, use the PowerShell command `Get-SPOAuditDataCollectionStatusForActivityInsights`. The command returns the current data collection status, which can be `NotInitiated`, `InProgress`, or `Paused`. You can generate reports when the status is `InProgress`.

```powershell
Get-SPOAuditDataCollectionStatusForActivityInsights 
```

## Known experiences with agent insights reports in SharePoint

The following experiences are known with agent insights reports generated in SharePoint Admin Center or by using SharePoint Online Management Shell:

- You can rerun a report only after 24 hours since the last report generated.
- In large tenants, it might take up to 48 hours for the data to be available.
- Only one report can exist for each report range value (1, 7, 14, or 28 days). This limitation means you can see a maximum of four reports at a given point.
- The newly generated report replaces the previously created report with the same date range. To preserve the previously created report, download the report first before creating a new report for the same date range.
- These reports use Microsoft 365 unified audit data and might not cover all audit events.