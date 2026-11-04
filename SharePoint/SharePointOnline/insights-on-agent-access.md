---
layout: Conceptual
title: Monitor agent access to SharePoint and OneDrive - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/insights-on-agent-access
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-05-13T00:00:00.0000000Z
ms.reviewer: nibandyo
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
customer-intent: As a SharePoint admin, I want to monitor all agents' access to SharePoint and OneDrive, including agents in SharePoint, Declarative agents, Custom agents, and more, so that I can ensure security and compliance for my organization's content.
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- M365-sam
- trust-pod
ms.custom: 
search.appverid: 
ms.assetid: 0ecb2cf5-8882-42b3-a6e9-be6bda30899c
description: Learn how to monitor all agents' access to SharePoint and OneDrive, including agents in SharePoint, Declarative agents, Custom agents, and more, using the agent access insights report in the SharePoint admin center or SharePoint Online Management Shell.
locale: en-us
document_id: e998c1e6-a22b-bd30-a1a6-71e31b07b38b
document_version_independent_id: 5f0b476a-6600-8181-ddc8-bd3e9c750bf4
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/insights-on-agent-access.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: insights-on-agent-access
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/insights-on-agent-access.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 8a4ae095-29ec-9722-12e6-d7fb800a804c
---

# Monitor agent access to SharePoint and OneDrive - SharePoint in Microsoft 365 | Microsoft Learn

The agent access insights report provides SharePoint administrators with rich information on how the agents access content across all SharePoint and OneDrive sites in your organization. The report includes all registered and activated agents, such as:

- [Agents created in SharePoint](/en-us/sharepoint/get-started-sharepoint-agents)
- [Declarative agents](/en-us/microsoft-365-copilot/extensibility/overview-declarative-agent)
- [Custom agents](/en-us/microsoft-365-copilot/extensibility/overview-custom-engine-agent)
- ... and more

By using this report, you can see how agents interact with your content, spot access patterns, and view agent distribution across sites. Use these insights to strengthen your security and apply governance controls like [Restricted access control](/en-us/sharepoint/restricted-access-control) and [Restricted content discovery](/en-us/sharepoint/restricted-content-discovery).

Agent access insights use Microsoft 365 unified audit logs to track how agents access your SharePoint sites and OneDrive accounts. These logs capture signals like reading, searching, and interacting with content, giving you a clear view of agent activity.

You can generate and manage the agent access insights report in the SharePoint Admin Center or by using SharePoint Online Management Shell. You must have an appropriate role assigned, such as [SharePoint administrator](/en-us/sharepoint/sharepoint-admin-role), to create or view agent access reports.

## Before you begin

See [SharePoint Advanced Management prerequisites](sharepoint-advanced-management-prerequisites).

Important

If you don't have a Microsoft SharePoint Advanced Management license, you're asked to enable data collection, so that the product starts to collect the relevant audit data to build this report. Once enabled, the reports can be generated 24 hours later and contain data from the point of collection. Data is stored for 28 days. If no reports are generated at least once in three months, data collection is paused and should be enabled again. To enable data collection for these reports, refer to the Data collection for agent access insights report section in this article.

## How do I access the agent access insights report in the SharePoint admin center?

1. Go to the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219) and sign in.
2. In the navigation pane, expand **Reports**, and then select **Agent insights**.
3. Select **Agent access**.
4. Review the report details, including agent activity, access patterns, and site distribution.

    ![Screenshot showing Agent Insights in the SharePoint admin center.](sharepointonline/media/sam-insights-agent-access/create-agent-access-report.jpg)

## How to create agent access reports in the SharePoint admin center

Note

You can create reports for the past 1, 7, 14, or 28 days. Data older than 28 days is automatically rolled off.

1. In the SharePoint admin center, in the navigation pane, expand **Reports**, and then select **Agent insights**.
2. Select **Create a report**.
3. Specify a name for the report and the report duration (1, 7, 14, or 28 days).
4. Select **Create and run** (or **Create**).

    [![Screenshot showing how to create an agent access report in the SharePoint admin center.](sharepointonline/media/sam-insights-agent-access/create-agent-access-report.jpg)](sharepointonline/media/sam-insights-agent-access/create-agent-access-report.jpg#lightbox)

## View the agent access report status in the SharePoint admin center

1. In the SharePoint admin center, in the navigation pane, expand **Reports**, and then select **Agent insights**.
2. Check the **Status** column to see if a report is ready or when it was last updated.

    [![Screenshot showing a list of agent access reports.](sharepointonline/media/sam-insights-agent-access/view-report-status.png)](sharepointonline/media/sam-insights-agent-access/view-report-status.png#lightbox)

## View the agent access report details in the SharePoint admin center

1. In the SharePoint admin center, in the navigation pane, expand **Reports**, and then select **Agent insights**.
2. Check the **Status** column to see if a report is ready or when it was last updated.
3. Select a report to view the data. You can view the top 100 sites hosting the highest number of agents. You can search for sites or filter by site template and governance policies.

    [![Screenshot showing agent distribution in SharePoint.](sharepointonline/media/sam-insights-agent-access/agent-distribution.png)](sharepointonline/media/sam-insights-agent-access/agent-distribution.png#lightbox)

## View top 20 agents for a specific site

1. In the SharePoint admin center, in the navigation pane, expand **Reports**, and then select **Agent insights**.
2. Select **Agent access**.
3. Select a site to view the top 20 agents accessing the content across the selected site.

    [![Screenshot showing top agents for a specific SharePoint site in an agent insights report.](sharepointonline/media/sam-insights-agent-access/agent-distribution.png)](sharepointonline/media/sam-insights-agent-access/agent-distribution.png#lightbox)

## View agent distribution across sites

1. In the SharePoint admin center, in the navigation pane, expand **Reports**, and then select **Agent insights**.
2. Select **Agent access**.
3. Choose **Unique Agents found in SharePoint Sites** or **Unique Agents in OneDrive Account**.

    This view displays how agents are distributed across your organization's sites. You can quickly see the number of sites in each site template category and how many unique agents are accessing them.

    [![Screenshot showing agent distribution across SharePoint sites.](sharepointonline/media/sam-insights-agent-access/agent-distribution.png)](sharepointonline/media/sam-insights-agent-access/agent-distribution.png#lightbox)

## Apply content governance policies from the access report

You can apply content governance policies on the sites from the access insights report. The available policies are:

- [Restrict site access policy](/en-us/SharePoint/restricted-access-control)
- [Restrict Content Discovery policy](/en-us/SharePoint/restricted-content-discovery)

Important

After you apply a policy to the site from the insights report, the policy status on the existing report doesn't update. To view the updated status of the policy on the site, select the policy to view the latest status or access the **Active site** panel and review the site settings.

## Access the agent access insights report by using SharePoint Online Management Shell

You can generate, check, and manage agent access insights reports by using SharePoint Online Management Shell.

### Prerequisites

- If you didn't already, [download and install the latest version of SharePoint Online Management Shell](https://www.microsoft.com/en-us/download/details.aspx?id=35588).
- You must have at least a [SharePoint administrator](/en-us/sharepoint/sharepoint-admin-role) assigned in Microsoft 365.
- Connect to the SharePoint Online Management Shell. See [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
- Make sure your organization has a license for the SharePoint Advanced Management add-on or Microsoft Copilot.

### Create and view an agent access insights report with SharePoint Online Management Shell

With permissions of at least a SharePoint administrator, you can generate and view the insights report by using the following commands:

1. To generate a report for the default one-day report duration, run the following command:

    ```powershell
    Start-SPOM365AgentAccessInsightsReport
    ```

    This command generates an agent access insights report for the past one day by default.
2. You can specify a different duration (7, 14, or 28 days) by using the `-ReportPeriodInDays` parameter. For example, to create a report for the past 28 days, run:

    ```powershell
    Start-SPOM365AgentAccessInsightsReport -ReportPeriodInDays <28>
    ```
3. To check the status of all active and available reports, run the following command:

    ```powershell
    Get-SPOM365AgentAccessInsightsReport
    ```
4. To view the details of a specific report, run the following command:

    ```powershell
    Get-SPOM365AgentAccessInsightsReport -ReportId <ReportId>
    ```

    Replace `<ReportId>` with the actual Report ID obtained from the previous command.
5. To download and view the report, run the following command:

    ```powershell
    Export-SPOM365AgentAccessInsightsReport -ReportId <ReportId> -Action Download
    ```

    Note

    PowerShell displays up to 100 sites but downloaded reports can contain up to 1 million sites.

    ```powershell
    Export-SPOM365AgentAccessInsightsReport -ReportId <ReportId> -View Download
    ```

    Replace `<ReportId>` with the actual Report ID.
6. You can also view summarized insights of agents across all site types by running the following command:

    ```powershell
    Get-SPOM365AgentAccessInsightsReport –ReportId -Content SiteDistribution
    ```

    **SiteDistribution** provides the summarized view of agents across all types of sites like Communication sites, Microsoft 365 group connected sites, OneDrive accounts, and more.

## Data collection for agent access insights report

If you don't have a Microsoft SharePoint Advanced Management license, you need to enable data collection. This section explains how to enable and check the status of data collection for the agent access insights report.

### Enable data collection

The following PowerShell command starts collecting audit data for reports on activities from the previous day:

```PowerShell
Start-SPOAuditDataCollectionForActivityInsights –ReportEntity M365AgentInsights
```

### Check data collection status

After you enable data collection, you can generate the reports after 24 hours. To check whether you can generate reports, use the following PowerShell command:

```PowerShell
Get-SPOAuditDataCollectionStatusForActivityInsights -ReportEntity M365AgentInsights
```

This command returns the current data collection status, which can be `NotInitiated`, `InProgress`, or `Paused`. You can generate reports when the status is `InProgress`.

## Known experiences with Microsoft 365 agent access insights

Keep these important known experiences in mind when working with agent access insights reports in the SharePoint admin center or SharePoint Online Management Shell:

- You can run a report only after 24 hours pass since the last report generation.
- For large tenants, it can take up to 48 hours for data to become available.
- Only one report can exist for each report range value (1, 7, 14, or 28 days). This limitation means you can see a maximum of four reports at any given point.
- When you generate a new report for the same date range, it replaces the previous report. To keep the old report, download it before creating a new one.
- Reports use Microsoft 365 unified audit data, which might not include every audit event.