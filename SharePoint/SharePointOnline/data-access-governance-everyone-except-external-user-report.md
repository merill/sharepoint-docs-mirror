---
layout: Conceptual
title: Data access governance reports - get the 'Everyone except external users' (EEEU) activity report for SharePoint sites - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/data-access-governance-everyone-except-external-user-report
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-05-12T00:00:00.0000000Z
ms.reviewer: pullabhk
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
customer-intent: As a SharePoint administrator, I want to get the 'Everyone except external users' (EEEU) activity report so that I can monitor ongoing sharing activities and identify potential oversharing risks in my organization.
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
- trust-pod
ms.custom:
- admindeeplinkSPO
search.appverid: 
description: In this article, you learn how to get the 'Everyone except external users' (EEEU) activity report to monitor sharing activities for SharePoint sites in your organization.
locale: en-us
document_id: a5704c50-b1a0-529b-9563-04eb64ad2301
document_version_independent_id: 3502750c-6fcd-65f1-6935-11e2cb94cd4b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/data-access-governance-everyone-except-external-user-report.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: data-access-governance-everyone-except-external-user-report
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/data-access-governance-everyone-except-external-user-report.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
platformId: 17528942-b4d0-2968-7bb0-6a6b6c5142f1
---

# Data access governance reports - get the 'Everyone except external users' (EEEU) activity report for SharePoint sites - SharePoint in Microsoft 365 | Microsoft Learn

"Everyone except external users" (EEEU) is a built-in SharePoint group that automatically includes all internal users but excludes any external users (guests). The EEEU report is one of the two types of [data access governance activity reports](data-access-governance-reports) that are available with [SharePoint Advanced Management](advanced-management).

![Screenshot of data access governance reports in the SharePoint admin center.](sharepointonline/media/data-access-governance/data-access-governance-reports.png)

EEEU activity reports help you identify sites where content is shared with your entire organization in the past 28 days. You can run the [site permissions report](data-access-governance-site-permissions-report) first to understand your organization's current EEEU sharing baseline, and then use the EEEU activity report to monitor ongoing EEEU sharing activities.

## Understand EEEU sharing through public sites and files

Content can be shared with EEEU in two ways:

- **Public sites**: When a site is configured as public, the EEEU group becomes part of the site's membership (owners, members, or visitors). Setting a site as public makes all site content visible to everyone in your organization.
- **Public items**: Individual files or folders can be shared directly with EEEU using the people picker. Setting a file or folder as public makes it accessible to your entire organization, while keeping the rest of the site private.

## Monitor EEEU sharing to identify potential risks

Sharing with EEEU can lead to unintended data exposure because it grants access to all current and future employees. You can use EEEU activity reports together with the [site permissions report](data-access-governance-site-permissions-report) to help you:

- Discover sites with the most EEEU sharing activity in the last 28 days
- Identify potential oversharing risks before they impact your organization
- Take appropriate actions to limit access when necessary

### Information shown in EEEU activity reports

Each EEEU activity report shows:

- **Top 100 sites**: Sites with the highest number of items or groups shared with EEEU in the last 28 days
- **Security policies**: Current policies applied to each site:
    - [Site sensitivity labels](/en-us/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)
    - Site privacy settings
    - [Site external sharing settings](external-sharing-overview)
- **Primary administrator**: The designated admin responsible for each site

### Snapshot and activity reports

Use EEEU reports together with other data access governance reports, such as the site permissions report, to get a complete and ongoing picture of your organization's data access landscape.

1. **Start with snapshot reports**: Run site permissions reports first to understand your baseline permission structure. Specifically, get the current state of EEEU sharing.
2. **Follow up with activity reports**: Run the EEEU activity reports to monitor recent EEEU sharing activities and catch emerging risks. Run these reports monthly to stay on top of ongoing sharing activities.

## Before you begin

Review [Prerequisites for SharePoint Advanced Management](sharepoint-advanced-management-prerequisites).

Keep these important points in mind:

- The EEEU report in the SharePoint admin center covers SharePoint sites only. To get an EEEU report for items in OneDrive, use [Identify content shared with "Everyone except external users" in last 28 days](powershell-for-data-access-governance#identify-content-shared-with-everyone-except-external-users-in-last-28-days).
- You can have up to 10 reports.
- Reports might take up to 24 hours to complete.
- Reports capture data from up to 24 hours before report generation.
- You can run reports again every 24 hours.

## Create an EEEU report

1. In the SharePoint admin center, in the navigation pane, expand **Reports**, and then select **Data access governance**.
2. In the **Activity reports** section, under **Shared with 'Everyone except external users'**, select **View reports**.
3. Select **Create report**. The **Create a report** panel opens.

    [![Screenshot that shows create an everyone except external users report.](sharepointonline/media/data-access-governance/eeeu-addreport.png)](sharepointonline/media/data-access-governance/eeeu-addreport.png#lightbox)
4. Configure your report as follows:

    - **Report name**: Enter a unique name to identify this report.
    - **Template**: Select which SharePoint site templates to include. You can select multiple template types or choose **All sites**:
        - **Classic sites**
        - **Communication sites**
        - **Team sites**
        - **Others**
    - **Privacy**: For Team sites, filter by privacy setting:
        - **Private**
        - **Public**
        - **All** (both private and public)
    - **Site sensitivity**: Choose specific sensitivity labels to focus on sites with particular security classifications. For example, you can identify files shared with EEEU within sites labeled as "Confidential" in the last 28 days.
    - **Report type**: Select which EEEU scenario to analyze:
        - **Specific files, folders and lists**: Individual files or folders shared with EEEU.
        - **Site membership**: Sites where EEEU is part of the site membership.
5. Select **Create and run**. It might take a few hours for the report to run.

## Use the **Shared with 'Everyone except external users'** report

To view the latest data, run each report manually. The **Status** column indicates whether the report is running or ready to view.

[![Screenshot showing shared with everyone except external users reports and their status.](sharepointonline/media/data-access-governance-everyone-except-external-users-report/shared-with-everyone-except-external-users-reports.png)](sharepointonline/media/data-access-governance-everyone-except-external-users-report/shared-with-everyone-except-external-users-reports.png#lightbox)

1. In the SharePoint admin center, in the navigation pane, expand **Reports**, and then select **Data access governance reports**.
2. In the **Activity reports** section, under **Shared with 'Everyone except external users'**, select **View reports**.
3. Select one or more reports, and then select **Run**.
4. After your report completes, the **Status** column updates.
5. Select a report to view insights about EEEU sharing activity:

    [![Screenshot that shows eeeu report details.](sharepointonline/media/data-access-governance/dag-eeeu-report.png)](sharepointonline/media/data-access-governance/dag-eeeu-report.png#lightbox)
6. To download a report, select **Download detailed report**. You get a CSV file that you can use for detailed analysis.

    The downloaded report contains the following information:

    - Up to 1 million sites sorted by EEEU sharing activity (highest first)
    - Complete site information including:
        - Primary administrator name and email
        - Site template type
        - Privacy settings
        - Sensitivity labels
        - Additional site metadata

## Take action based on EEEU report findings

After discovering potential oversharing through EEEU reports, take action to remediate risks and improve your organization's data access governance. For more information, see [Data access governance reports for SharePoint and OneDrive sites](/en-us/sharepoint/data-access-governance-reports#remedial-actions-from-data-access-governance-reports).