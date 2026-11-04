---
layout: Conceptual
title: Data access governance reports - get sensitivity label snapshot report for SharePoint sites - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/data-access-governance-sensitivity-label-report
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
customer-intent: As a SharePoint administrator, I want to get the sensitivity label snapshot report so that I get the baseline of sensitivity labels for SharePoint sites in my organization to help govern data access.
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
description: In this article, you learn how to get sensitivity label snapshot report to get the baseline of sensitivity labels for SharePoint sites in your organization.
locale: en-us
document_id: db02afeb-b28a-d5d7-275f-0191f1eea293
document_version_independent_id: 6386f3de-81df-fd67-736c-2c1683055ff8
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/data-access-governance-sensitivity-label-report.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: data-access-governance-sensitivity-label-report
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/data-access-governance-sensitivity-label-report.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 98e0c1c8-c1be-158a-714a-42627171e1df
---

# Data access governance reports - get sensitivity label snapshot report for SharePoint sites - SharePoint in Microsoft 365 | Microsoft Learn

Sensitivity label for files report is one of the Data access governance snapshot reports available with [SharePoint Advanced Management](advanced-management). This report provides a snapshot of your organization's current sensitivity label distribution across all SharePoint and OneDrive sites, helping you understand how your data is classified and protected. This snapshot approach helps you quickly assess your overall data protection posture and identify sites that need immediate attention.

## What does the sensitivity label report show me?

The sensitivity label report includes the following information:

- **Sites with labeled files**: Lists sites containing the highest number of [Office files with the selected sensitivity label applied](/en-us/microsoft-365/compliance/sensitivity-labels-sharepoint-onedrive-files)
- **Applied policies**: Shows which security policies are active on each site:
    - [Site sensitivity labels](/en-us/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)
    - [Site unmanaged device access controls](control-access-from-unmanaged-devices)
    - [Site external sharing settings](external-sharing-overview)

![Screenshot of a CSV table of SharePoint sites showing site details, admin contacts, document sensitivity, and policy settings for governance.](sharepointonline/media/details-screen.png)

This data helps you verify that sites containing sensitive content have appropriate security policies in place.

## When to use the sensitivity label report?

We recommend running the sensitivity label report in combination with other Data access governance reports, to get a complete and ongoing picture of your organization's data access landscape. Here's how to use them together effectively:

1. **Start with snapshot reports**: Run site permissions reports and sensitivity label reports first to understand your baseline permission structure and identify sites with the broadest exposure. We recommend running these quarterly to maintain a comprehensive view of your organization's data access.
2. **Follow up with activity reports**: Use sharing links and EEEU activity reports to monitor recent oversharing activities and catch emerging risks. We recommend running these monthly to stay on top of ongoing sharing activities.

## How to add sensitivity label reports?

Important

Review these important details before creating your first report:

- Reports are created for SharePoint sites only (OneDrive is not currently supported)
- Reports may take up to 24 hours to complete
- Reports capture data from up to 120 hours before generation
- You can run reports again every 24 hours

You can create a sensitivity label report for each label you want to monitor. When you add a report, the system automatically runs it for the first time.

Note

You can only create reports for sensitivity labels that have 'File' included in their scope.

![Screenshot of the Add sensitivity label reports panel](sharepointonline/media/sensitivity-labels-screen.png)

## Run sensitivity label reports

To get the latest data for each report, you need to manually run it. You can run all reports at once or select individual reports to run. To check if a report is ready or see when it was last updated, check the **Status** column.

![Screenshot showing reports for sites with files labeled Confidential and Highly confidential](sharepointonline/media/sensitivity-labels-reports-link.png)

## Download the sensitivity label reports

After running a report, you can download the data as a CSV file for offline analysis. Here's how:

1. Select the report name to access the download option
2. Download the CSV file containing up to 10,000 sites

## Take action based on sensitivity label report findings

After discovering potential oversharing through sensitivity label reports, you can take action to remediate risks and improve your organization's data access governance. See [Data access governance reports](data-access-governance-reports#remedial-actions-from-data-access-governance-reports).