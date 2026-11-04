---
layout: Conceptual
title: SharePoint app in Teams analytics - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/homesites/sharepoint-app-in-teams-analytics
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-10-06T00:00:00.0000000Z
ms.reviewer: evanatkin
ms.author: dipadur
author: divyachapan
manager: elizapo
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: sites-pages
ms.localizationpriority: high
ms.collection:
- Strat_SP_modern
- M365-collaboration
- highpri
search.appverid:
- SPO160
- MET150f
ms.custom: intro-overview
description: View usage data for SharePoint app in Teams to learn more about usage trends.
locale: en-us
document_id: da682e02-6b9a-2ebd-48cc-cce8a2991760
document_version_independent_id: 6693c4d0-519d-7580-554d-e08b2d3625c6
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/homesites/sharepoint-app-in-teams-analytics.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: homesites/sharepoint-app-in-teams-analytics
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/homesites/sharepoint-app-in-teams-analytics.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 89070dd5-d383-d986-96b7-c6e1411e114c
---

# SharePoint app in Teams analytics - SharePoint in Microsoft 365 | Microsoft Learn

Understand how and when users engage with components of the SharePoint app in Teams experience by using analytics. Review data on overall traffic, usage, and engagement across each of your organization's SharePoint app in Teams experiences. Data can be further filtered to view a specified range or downloaded as an analytics report in Excel.

Note

- Member level permissions (or higher) to the SharePoint Home site are required to view usage analytics for SharePoint app in Teams.
- Usage analytics data is aggregated and can't be tracked to an individual user.
- Users with a Microsoft 365 subscription (E, F, or A license) are limited to creating and using one experience. If you want to create or use two or more experiences (up to 50), then every user in your tenant must have a Microsoft Viva Suite or Viva Communications and Communities license. See [Microsoft Viva plans and pricing](https://www.microsoft.com/microsoft-viva/pricing) for more info.
- For tenants that are set up for more than one region, the option to access analytics will have to be disabled for each region using PowerShell commands. For more information, see how to disable analytics features.
- The analytics feature is unavailable in GCC, GCC High, and DoD environments. For more information, see the [list of platform features](/en-us/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government#platform-features).

## How to access the report

Users need member level permissions (or higher) for their SharePoint app in Teams experience to access and view the analytics data for that experience. For organizations that have more than one experience, you can view the analytics report for each experience by going to that experience and opening the report. Analytics data for SharePoint app in Teams can be accessed from your SharePoint home site or the SharePoint app in Teams.

### Access analytics data from a SharePoint home site

1. Navigate to your organization’s SharePoint home site.
2. Select the **Settings**![](../sharepointonline/media/homesites/viva-connections-analytics/sharepoint-setting-icon.png) icon.
3. Select **Manage home site**.
4. Go to the **SharePoint app in Teams analytics** section and select **View analytics**.

    ![Screenshot showing the analytics section with view report highlighted.](../sharepointonline/media/homesites/viva-connections-analytics/access-analytics-sharepoint.png)

### Access analytics data from Microsoft Teams

1. Navigate to your organization’s SharePoint app in Teams.
2. Select the **ellipsis** in the top-right corner.
3. Select **View Analytics**

    ![Screenshot showing options with view analytics highlighted.](../sharepointonline/media/homesites/viva-connections-analytics/access-analytics-teams-app.png)

## What’s in the usage report

The Analytics page contains charts and graphs providing data on overall traffic, usage, and engagement for your accessed SharePoint app for Teams experience. Data can be filtered down to the last 7, 30, or 90 days. Overall traffic data can be filtered to the last 12 months.

Note

- A Microsoft Viva suite or Viva Communications and Communities license is required to view data beyond 30 days. For more information, see [Microsoft Viva plans and pricing](https://www.microsoft.com/microsoft-viva/pricing).
- Data filtered to the previous 90 days and 12 months will be available in mid-June 2024. Historical data for these new filters won't be available.

### Overall traffic

This section provides usage data on unique users, engaged users, total views, and returning users. Activity for desktop, web, and mobile usage is combined in this section, regardless of the platform.

- **Unique users**: Total number of individual users regardless of how many times they visited across all platforms and devices.
- **Engaged users**: Total number of individual viewers who interact with the SharePoint app in Teams.
- **Total views**: Total number of views across all platforms and devices.
- **Returning users**: Can view by the percentage or number of users who engaged with SharePoint app in Teams content since the last month over a 12-month view. Select the dropdown to switch viewing data on returning users by percentage and individual user.

Note

A Microsoft Viva suite or Viva Communications and Communities license is required to view data on returning users. For more information, see [Microsoft Viva plans and pricing](https://www.microsoft.com/microsoft-viva/pricing).

[![Screenshot showing data covering overall traffic.](../sharepointonline/media/homesites/viva-connections-analytics/analytics-usage-report.png)](../sharepointonline/media/homesites/viva-connections-analytics/analytics-usage-report.png#lightbox)

### Usage details

This section breaks down usage data across the types of devices and apps used to access the SharePoint app in Teams experience, including activity from the Dashboard, News, and Resources web parts.

- **Total views by apps and devices**: Includes views for desktop, web, and mobile usage.
- **Engaged users by component**: Includes number of engaged users for the Dashboard, News and Resources web parts.
    - **Dashboard**: Includes usage from the Dashboard cards.
    - **News**: Includes usage from the News component.
    - **Resources**: Includes usage from the tab in the mobile app and the desktop app (The global navigation bar in SharePoint isn't included).

### Engagement details

- **Engaged users by dashboard card**: Includes usage data for each dashboard card on your dashboard, indicating how often each user engages with a card.

    [![Screenshot showing data covering engagement details.](../sharepointonline/media/homesites/viva-connections-analytics/analytics-engagement-details.png)](../sharepointonline/media/homesites/viva-connections-analytics/analytics-engagement-details.png#lightbox)

## Download report

Select **Download report** at the top of the analytics page to download an Excel spreadsheet that contains all the information on the analytics page across three separate tabs and sheets of data. The spreadsheet contains all data available that the account has access to (based on license).

[![Screenshot showing downloaded analytics report in a spreadsheet.](../sharepointonline/media/homesites/viva-connections-analytics/vc-analytics-spreadsheet.png)](../sharepointonline/media/homesites/viva-connections-analytics/vc-analytics-spreadsheet.png#lightbox)

## How to disable analytics features

Your organization might not want to see analytics data due to local data and compliance regulations or other reasons. Use the following steps to disable the SharePoint app in Teams analytics feature using PowerShell. For tenants that are set up for more than one region, the option to access analytics needs to be disabled for each region using the PowerShell command. Note: The SharePoint app in Teams was previously branded as "Viva Connections", thus you will see the former name still in these PowerShell commands.

1. Make sure any previous versions of SharePoint Online Management Shell are uninstalled on your device (Settings &gt; Apps &gt; Installed apps &gt; uninstall "SharePoint Online Management Shell").
2. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).
3. Connect to SharePoint as a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
4. Connect to the tenant's SharePoint service by running the following command:

    Run `Connect-SPOService -Url <sharepoint admin URL> -Credential <credentials>`
5. Enter the password in the password field.
6. Run `Get-SPOTenant` to view the tenant admin Settings.
7. Locate the "DisableVivaConnectionsAnalytics" setting.
8. Enable or disable the setting by running the following command:

    Run `Set-SPOTenant -DisableVivaConnectionsAnalytics $True`
9. Run `Get-SPOTenant` to confirm the setting is updated.

## Explanations for common report errors

You might see an error in the Analytics section. Review common errors to learn more about how to resolve them so you can download reports.

### Not enough data to generate a report

This message displays if there isn't enough usage data to generate a report. Finish setting up SharePoint app for Teams and try to access the report again.

![Screenshot showing error when there isn't enough usage data.](../sharepointonline/media/homesites/viva-connections-analytics/lack-data-error.png)

### General error

Sometimes due to connectivity issues or other technical problems, the analytics report might not be available. Check your network connection, refresh the page, and try loading the report again.

![Screenshot showing a general error when there's a problem generating a report.](../sharepointonline/media/homesites/viva-connections-analytics/general-error.png)

### Errors within the downloaded report

Within the downloaded Excel report, you might notice that certain sections aren't available due to insufficient usage data.

### The report is disabled

You might get the following message: "Viva Connections usage data has been disabled for your organization by your administrator." This message means you can't access usage reports unless your admin enables the feature for your organization.

![Screenshot showing error received when reports have been disabled.](../sharepointonline/media/homesites/viva-connections-analytics/data-disabled-error.png)