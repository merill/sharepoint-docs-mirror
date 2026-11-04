---
layout: Conceptual
title: Create change history reports - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/change-history-report
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-05-14T00:00:00.0000000Z
ms.reviewer: daminasy
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
customer-intent: As a SharePoint administrator, I want to create and view change history reports to monitor site actions and organization setting changes.
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Highpri
- Tier2
- trust-pod
- M365-sam
description: Learn how to create and view SharePoint site change history reports in SharePoint admin center.
locale: en-us
document_id: e9d922e9-41b0-ba8c-a86f-9a8cca39b916
document_version_independent_id: a01256c5-e401-568d-9107-5856bb1ec2fc
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/change-history-report.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: change-history-report
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/change-history-report.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 4592f2e8-45b8-3ad8-2d09-c5a7fe17a60f
---

# Create change history reports - SharePoint in Microsoft 365 | Microsoft Learn

Aa a SharePoint administrator, you can create custom change history reports in the [SharePoint admin center](get-started-new-admin-center) to review CSV reports of site actions or organization setting changes made within the last 180 days.

Change history reports can increase visibility and let you monitor changes made to the SharePoint configuration across various levels of your organization.

Create up to 10 reports that track what changed, when it happened, and who initiated the change across the site and organization settings.

[![Screenshot of change history report dashboard.](sharepointonline/media/sam-overview/6-change-history-report.png)](sharepointonline/media/sam-overview/6-change-history-report.png#lightbox)

## Prerequisites

See [SharePoint Advanced Management prerequisites](sharepoint-advanced-management-prerequisites).

Also turn on **Audit logging** in the Microsoft Purview portal. Audit logs are essential for tracking user and admin activities across your SharePoint environment. See [Turn audit logging on or off](/en-us/purview/audit-log-enable-disable).

## How do I create a change history report?

1. Go to the SharePoint admin center, and sign in.
2. In the navigation pane, expand **Reports** and select **Change history**. Then select **Create report**.
3. Choose the type of report you want to generate and select **Site settings/Organization settings**.
4. A panel appears where you can specify the type of information you want to include in your change history report. Select **Create report** to generate a new report.
5. The new report is listed on the change history page. Select the report to open the change history report panel and monitor its status.
6. Once the report is created, select **Download report** to export the data as a CSV file. The **Create a copy** button allows you to create more reports with similar parameters.

Note

- The report takes a few hours to generate depending on the search criteria selected when creating the report.
- You can export data for up to 180 days with a change history report depending on the user license. The report may contain data for users that go back 180 days and data for others that don't. Since the type of user license isn't shown on the report, it might appear as if data is missing for some users.
- Admins assigned the [global reader role](/en-us/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&amp;preserve-view=true%3Do365-worldwide) don't have the permissions to create or delete a report, but can download to review the changes.

### View a change history report

To view change history reports, in the SharePoint admin center, expand **Reports**, and select **Change history**.

You can create new reports, delete, and refresh their statuses from the change history page. This page can only show 10 reports at a time. The best practice is to delete a previous report before creating a new one.

[![Screenshot of change history dashboard with a prefilled new report panel.](sharepointonline/media/change-history/2-change-history-dashboard-panel-expanded.png)](sharepointonline/media/change-history/2-change-history-dashboard-panel-expanded.png#lightbox)

## What types of change history reports can I create?

You can create two types of change history reports to monitor different aspects of your SharePoint environment. Site settings reports track changes made to individual SharePoint sites, including changes to site properties and configurations performed by Site Administrators and SharePoint Administrators. Organization settings reports monitor changes made at the tenant level through the SharePoint Admin Center, helping you ensure your organization-wide policies and configurations remain aligned with your governance requirements.

### Site settings report

Generate a site settings report for a given date range and filter by sites and users. You can download the report as a CSV file to view the site property changes. All site actions performed by Site Administrators and SharePoint Administrators are captured in the report.

### Organization settings report

Note

The audited organization settings table listed later in this article reflects the list of settings that are currently tracked under organization settings reports.

You can also generate an organization settings report tracking changes made to organization settings from the SharePoint Admin Center. You can generate these reports for custom date ranges while filtering for specific users of interest. A best practice is to review the downloaded reports to ensure there are no deviations in settings from the desired state.

Any changes made to the following organization settings are reflected in the reports. We're continuously working to bring more settings under the ambit of these reports.

#### Current audited organization settings

The following table lists the latest set of supported settings found under the **Settings** node:

| Name | Description |
| --- | --- |
| **SharePoint Pages** | Allow commenting on modern pagesAllow users to create new modern pages |
| **SharePoint Site creation** | Users can create SharePoint siteCreate teams sites underDefault time zoneDefault storage limit for new sites |
| **SharePoint Notifications** | Allow notifications |
| **SharePoint Site storage limits** | AutomaticManual |
| **OneDrive Notifications** | Allow notifications |
| **OneDrive Retention** | Days to retain a deleted user's OneDrive |
| **OneDrive Storage limit** | Default storage limit |
| **OneDrive Sync** | Show Sync button on the OneDrive websiteAllow syncing only on computers joined to specific domainsBlock download of specific file types |
| **SharePoint Version history limits** | Set version history limits |

The following table lists the latest set of supported settings found in **Access Control** under the **Policies** node:

| Name | Description |
| --- | --- |
| **Unmanaged devices** | Restrict access from devices that aren't compliant or joined to a domain |
| **Idle session sign out** | Automatically sign out users from inactive browser sessions |
| **Network location** | Allow access only from specific IP addresses |
| **Apps that don't use modern authentication** | Block access from Office 2010 and other apps that can't enforce device-based restrictions |
| **SharePoint access restriction** | Restrict access to SharePoint sites & content by security group |
| **OneDrive access restriction** | Restrict access to OneDrive content by security group |

The following table lists the latest set of supported settings found in **Sharing** under the **Policies** node:

| Name | Description |
| --- | --- |
| **External Sharing** | Content can be shared withMore external sharing settingsOther settings |
| **File and folder settings** | Choose the type of link selected by default when users share files and folders in SharePoint and OneDriveChoose the permission selected by default for sharing linksChoose who can access files with the URL to a file copied from the browser address bar |