---
layout: Conceptual
title: Generate Enterprise App Insights reports - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/app-insights
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: false
ms.date: 2025-11-21T00:00:00.0000000Z
ms.reviewer: goagarwal
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
customer-intent: As a SharePoint admin, I want to generate App insights reports to monitor non-Microsoft applications accessing SharePoint content.
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
- SAM-FY25
search.appverid: 
description: Learn how to generate App insights reports to view how non-Microsoft applications registered on your Microsoft Entra admin center access your SharePoint content.
locale: en-us
document_id: 8d4afccf-4c57-fe47-6a3c-abcb0314b840
document_version_independent_id: f13de7dd-52c6-5576-5cf8-d386e54726e8
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/app-insights.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: app-insights
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/app-insights.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 1eab0828-ed84-9f21-bbd7-e733e0e07707
---

# Generate Enterprise App Insights reports - SharePoint in Microsoft 365 | Microsoft Learn

App insights is a [SharePoint Advanced Management](advanced-management) feature that lets [IT administrators](/en-us/microsoft-365/admin/add-users/about-admin-roles) gain insights on the various non-Microsoft applications registered to your Microsoft Entra admin center and how they access your SharePoint content. This report can help you maintain and protect the integrity of your content.

The report is based on the Microsoft audit data logged when a non-Microsoft application accesses content through the following set of events:

- `FileAccessed`
- `FileDownloaded`
- `FileModified`
- `FileUploaded`

## Prerequisites to generate App insights reports

See [SharePoint Advanced Management prerequisites](sharepoint-advanced-management-prerequisites), including requirements for [SharePoint Online PowerShell module](sharepoint-advanced-management-prerequisites#sharepoint-online-powershell-module).

## App insights reports in SharePoint admin center

### Data collection for Enterprise App Insight report

Important

As a one time activity you will see a pop up on the UI to enable data collection for 'Enterprise App Insight' reports, so that the product starts to collect the relevant audit data to build this report. Once enabled, the reports can be generated 24 hours later and contains data from the time of data collection. Data is stored for 28 days. If no reports are generated even once in three months, data collection is paused and should be enabled again.

### Create report

1. In to SharePoint admin center, in the navigation pane, expand **Reports** and then select **App insights**.
2. Once on the **App insights** landing page, select **Add a report** to generate a new report.

    [![Screenshot of the create reports page for app insights dashboard in SharePoint admin center.](sharepointonline/media/app-insights/1-enterprise-app-insights-landing-page.png)](sharepointonline/media/app-insights/1-enterprise-app-insights-landing-page.png#lightbox)
3. Under **Report range**, you can specify and filter data from a respective time frame for your report. [![Screenshot of the report range for app insights in SharePoint admin center.](sharepointonline/media/app-insights/2-enterprise-app-insights-create-new-report.png)](sharepointonline/media/app-insights/2-enterprise-app-insights-create-new-report.png#lightbox)
4. Select **Add and run**.

Note

- It can take up to several hours for generated reports to be available.
- Only one report is allowed per report range.
- Reports can be rerun after 24 hours.

### Manage reports in SharePoint admin center

#### View report status

To check if a report is ready or when it was last updated, see the **Status** column. When a report is ready, select it to view the data.

[![Screenshot of created app insight report in SharePoint admin center.](sharepointonline/media/app-insights/3-enterprise-app-insights-view-report.png)](sharepointonline/media/app-insights/3-enterprise-app-insights-view-report.png#lightbox)

You're able to see the top 100 (by request volume) results on the screen.

You can also filter by **App name**, **App permissions**, and **Site sensitivity** to view relevant results from the top 100 rows.

[![Screenshot of list of insight reports in SharePoint admin center.](sharepointonline/media/app-insights/4-enterprise-app-insights-manage-reports.png)](sharepointonline/media/app-insights/4-enterprise-app-insights-manage-reports.png#lightbox)

Important

To view up to 1 million results, you must select **Download detailed report**.

#### Delete report

To delete a report, select the existing report you want to delete, and then select **Delete report**.

#### Rerun a report

To get updated data for a given report range, select an existing report, and then select **Run**.

Tip

A rerun prompt also appears if you select **Add a report** and select a report range for which there already exists a report.

## App insights reports in SharePoint PowerShell Module

You can generate and manage App insights reports using SharePoint Online Management Shell.

### Create a one-day default duration report

To generate report for the default duration of one day, run the following command:

```powershell
Start-SPOEnterpriseAppInsightsReport
```

### Create report for any other duration

To generate report for any other duration, run the following command:

```powershell
Start-SPOEnterpriseAppInsightsReport -ReportPeriodInDays $ReportPeriodInDays (possible values = 1, 7, 14, 28) 
```

### Check status of all active and available reports

To check status of all active and available reports, run the following command:

```powershell
Get-SPOEnterpriseAppInsightsReport
```

### Check status of a specific report

To check status of a specific report, run the following command:

```powershell
Get-SPOEnterpriseAppInsightsReport -reportID $reportID (for the given report ID)
```

### View a specific report

To view a specific report, run the following command:

```powershell
Get-SPOEnterpriseAppInsightsReport -reportID $reportID
```

### Download a report

To download the report, run the following command:

```powershell
Get-SPOEnterpriseAppInsightsReport -reportID $reportID -action download
```

Important

Rerun and delete report capabilities are unavailable for PowerShell. The Create report cmdlets can be used with relevant report duration.

## Known issues

- In new tenants, it can take a few days for data to be available and for these reports to be generated successfully. In large tenants, the data can be delayed by up to 48 hours (about two days).
- A report can be rerun only after 24 hours since the last report generation.
- There can only be one report for each value of **Report range**. This means that you can see a maximum of four reports in the **Enterprise Application Insights** homepage.
- These reports are powered by Audit data and don't include all audit events.
- You might see App ID of a non-Microsoft app, but App name of a middle-tier app in some cases.