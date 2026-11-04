---
layout: Conceptual
title: Data access governance reports - get sharing links activity report for SharePoint sites - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/data-access-governance-sharing-links-report
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-04-03T00:00:00.0000000Z
ms.reviewer: pullabhk
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
customer-intent: As a SharePoint administrator, I want to get the sharing links activity report so that I can monitor sharing activities and identify potential oversharing risks in my organization.
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
description: In this article, you learn how to get sharing links activity report to monitor sharing activities for SharePoint sites in your organization.
locale: en-us
document_id: dabeea9b-39ab-aac5-e7cb-bce267a36ecc
document_version_independent_id: 93ec8ec0-ef0c-9bcf-3762-e354ca6d8e2b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/data-access-governance-sharing-links-report.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: data-access-governance-sharing-links-report
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/data-access-governance-sharing-links-report.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
platformId: a482b4c8-e2a1-fe9c-f4bc-8e4197ae01c0
---

# Data access governance reports - get sharing links activity report for SharePoint sites - SharePoint in Microsoft 365 | Microsoft Learn

Sharing links activity reports are one of the two types of Data access governance activity reports available with [SharePoint Advanced Management](advanced-management). These reports help you identify sites where users have created the most new sharing links in the last 28 days. Combined with other Data access governance reports, this report helps you monitor sharing activities and identify potential oversharing risks in your organization.

## What do sharing links activity reports show me?

Sharing links reports show information for the following types of links:

| Name of report | Description |
| --- | --- |
| **'Anyone' links** | This report provides a list of sites in which the highest number of "Anyone" links were created. "Anyone" links allow anyone to access files and folders without signing in. |
| **'People in the organization' links** | This report provides a list of sites in which the highest number of 'People in the organization' links were created. These links can be forwarded internally and allow anyone in the organization to access files and folders. |
| **'Specific people' links shared externally** | This report provides a list of sites in which the highest number of 'Specific people' links were created for people outside the organization. |

Note

We recommend running the [site permissions report](data-access-governance-site-permissions-report) first to understand your organization's current link sharing baseline, then use this activity report to monitor ongoing link sharing activities.

![Screenshot that shows the Sharing links page.](sharepointonline/media/sharing-links-screen.png)

## When to use sharing links reports?

We recommend running the sharing links reports in combination with other Data access governance reports, to get a complete and ongoing picture of your organization's data access landscape. Here's how to use them together effectively:

1. **Start with snapshot reports**: Run site permissions reports and sensitivity label reports first to understand your baseline permission structure and identify sites with the broadest exposure. We recommend running these quarterly to maintain a comprehensive view of your organization's data access.
2. **Follow up with activity reports**: Use sharing links and EEEU activity reports to monitor recent oversharing activities and catch emerging risks. We recommend running these monthly to stay on top of ongoing sharing activities.

## Run sharing links reports

Important

Review these important details before creating your first report:

- Reports are created for SharePoint sites only. OneDrive support is [available via PowerShell](powershell-for-data-access-governance)
- Reports may take up to 24 hours to complete
- Reports capture data from up to 24 hours before generation
- You can run reports again every 24 hours

To get the latest data for each report, you need to manually run it. You can run all reports at once or select individual reports to run. To check if a report is ready or see when it was last updated, check the **Status** column.

## View sharing links reports

After your report is ready, select the report name to view the data. Each sharing link report displays:

- **Top 100 sites**: Sites with the highest number of [sharing links](modern-experience-sharing-permissions) created in the last 30 days
- **Applied policies**: Security policies active on each site:
    - [Site sensitivity labels](/en-us/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)
    - [Site unmanaged device controls](control-access-from-unmanaged-devices)
    - [Site external sharing settings](external-sharing-overview)
- **Primary administrator**: The designated admin for each site

Note

OneDrive data is now [available via PowerShell](powershell-for-data-access-governance).

## Download sharing links reports

You can download any report as a CSV file for offline analysis, containing data for up to 1 million sites.

## Take action based on sharing links report findings

After discovering potential oversharing through sharing links reports, you can take action to remediate risks and improve your organization's data access governance. See [Data access governance reports](data-access-governance-reports#remedial-actions-from-data-access-governance-reports).