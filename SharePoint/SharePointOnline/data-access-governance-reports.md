---
layout: Conceptual
title: Data access governance reports for SharePoint sites - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/data-access-governance-reports
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-07-09T00:00:00.0000000Z
ms.reviewer: pullabhk
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
customer-intent: As a SharePoint administrator, I want to access data access governance reports to discover sites that contain potentially overshared or sensitive content.
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
description: In this article, you learn about reports that can help you govern access to data in SharePoint.
ai-usage: ai-assisted
locale: en-us
document_id: bd05a015-115f-0e1d-e607-64a0c08a77a1
document_version_independent_id: 6ac538e0-2010-34db-7b06-d31272bfae28
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/data-access-governance-reports.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: data-access-governance-reports
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/data-access-governance-reports.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: cc2d9349-ac7e-06dd-f9bc-6653c502a74d
---

# Data access governance reports for SharePoint sites - SharePoint in Microsoft 365 | Microsoft Learn

As sprawl and oversharing of SharePoint sites increase with exponential data growth, organizations need help with governing their data. Data access governance reports can help you govern access to SharePoint data. The reports let you discover sites that contain potentially overshared or sensitive content. You can use these reports to assess and apply the appropriate security and compliance policies.

## What you need to create a data access governance report

See [Prerequisites for SharePoint Advanced Management](sharepoint-advanced-management-prerequisites).

The reports are currently unavailable for Microsoft 365 operated by 21Vianet, even if you have the required licenses.

## How to access the Data access governance reports in the SharePoint admin center

1. Sign in to the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219) with the [SharePoint administrator](sharepoint-admin-role) credentials for your organization.
2. In the left pane, expand **Reports** and then select **Data access governance**.

    The following reports are currently available from the Data access governance landing page:

    - **[Snapshot reports](/en-us/sharepoint/data-access-governance-reports#what-are-snapshot-reports)**

        - [Site permissions across your organization](/en-us/sharepoint/data-access-governance-reports#what-is-the-site-permissions-report) (Recommended)
        - [Sensitivity label applied to files](/en-us/sharepoint/data-access-governance-reports#sensitivity-labels-for-files-reports)
    - **[Activity reports](/en-us/sharepoint/data-access-governance-reports#what-are-activity-reports)**

        - [Sharing links](/en-us/sharepoint/data-access-governance-reports#what-is-the-sharing-links-report)
        - [Shared with 'Everyone except external users'](/en-us/sharepoint/data-access-governance-reports#what-is-the-everyone-except-external-users-eeeu-report)

    [![Screenshot of the Data access governance landing page.](sharepointonline/media/data-access-governance/data-access-governance-home-page.png)](sharepointonline/media/data-access-governance/data-access-governance-home-page.png#lightbox)

Note

IT administrators with Microsoft 365 E5 licensing can access Data access governance reporting, but can't view or use the other [SharePoint Advanced Management features](advanced-management). The reports don't provide snapshot reports or remedial actions. Activity reports are available but can return only up to 10,000 sites.

## What are snapshot reports?

Snapshot reports give you a snapshot of your organization's current status based on specific reporting criteria. These reports show data as of the date they were generated.

Currently, three types of snapshot reports are available:

- **Site permissions report**: Provides a comprehensive snapshot of the permission structure across all SharePoint and OneDrive sites. It helps you identify sites with the broadest user access, such as sites with thousands of users, external guests, or "Everyone except external users" permissions.
- **Site permissions for users report**: Lists all sites a specified user can access. Admins can use this report to determine whether the user can access the entire site or specific sections, granted directly to the user or indirectly through groups.
- **Sensitivity label for files report**: Identifies SharePoint sites containing files with specific sensitivity labels applied. You can use this report to verify that appropriate security policies are in place for your most sensitive content.

## What are activity reports?

Activity reports help you track potential oversharing activities that occurred in the last 28 days. These reports focus on "recently active" sites where users created sharing links or shared content with large groups. For all activities tracked in activity reports, you can find corresponding "baseline" data in the snapshot reports.

Currently, two types of activity reports are available to help you identify potential oversharing:

- **Sharing links reports**: Identifies sites where users recently created the most sharing links (including "Anyone," "People in the organization," and "Specific people" links) to help you catch potential oversharing as it happens.
- **Shared with 'Everyone except external users' reports**: Tracks sites where content is shared with all internal users in your organization, helping you identify broad internal exposure that could lead to unintended data access.

Important

**For organizations without SharePoint Advanced Management:** You must enable data collection before you can generate activity reports. Here's what you need to know:

- After enabling data collection, the system starts collecting audit data
- Data is stored for 28 days
- Reports become available 24 hours after enabling collection
- Reports only contain data from when collection was enabled
- If no reports are generated for 3 months, data collection pauses and must be re-enabled

![Screenshot showing how to enable data collection for sharing link activity reports.](sharepointonline/media/data-access-governance/enable-data-collection-sharinglinks.png)

## How do you use snapshot and activity reports?

As part of your governance strategy, combine both snapshot and activity reports to get a complete picture of your organization's data access landscape. Here's how to use them together effectively:

1. **Start with snapshot reports**: Run site permissions reports first to understand your baseline permission structure and identify sites with the broadest exposure. Run these reports quarterly to maintain a comprehensive view of your organization's data access.
2. **Follow up with activity reports**: Use sharing links and EEEU activity reports to monitor recent oversharing activities and catch emerging risks. Run these reports monthly to stay on top of ongoing sharing activities.

This combination ensures you have both a complete picture of your current state and visibility into ongoing sharing activities that could create new exposure risks.

## What is the site permissions for your organization report?

The site permissions for your organization report is the first snapshot report that provides a comprehensive view of your organization's current permission structure across all SharePoint and OneDrive sites. This report analyzes every site to help you understand how broadly your data is exposed and identify potential oversharing risks. This snapshot approach helps you quickly assess your overall security posture and identify sites that need immediate attention.

Learn how to create and use the [site permissions for your organization report](data-access-governance-site-permissions-report).

## What is the site permissions for users report?

The site permissions for users report is the next snapshot report that provides a comprehensive view into permissions of the specified users across all SharePoint and OneDrive sites. This report lists all sites a user can access and allows admins to determine whether they can access the entire site or specific sections, granted directly to the user or indirectly through groups. This approach helps you quickly assess your overall security posture and identify sites that need immediate attention.

Learn how to create and use the [site permissions for users report](data-access-governance-site-permissions-users-report).

## What is the sites and files shared via special SharePoint groups report?

The sites and files shared via special SharePoint groups report is a snapshot report that identifies all sites, folders, and files across SharePoint and OneDrive that are effectively public because of the special SharePoint groups 'Everyone except external users' (EEEU) or 'Everyone'. While the site permissions for your organization report tells you which sites are overshared, this report tells you exactly which items are overshared and how access was granted, so you can accelerate cleanup through scripting instead of depending on site owners.

Learn how to run and use the [sites and files shared via special SharePoint groups report](data-access-governance-detailed-eeeu-everyone-permissions-report).

## What is the sensitivity labels for files report?

The sensitivity labels for files report is another snapshot report that helps you control access to sensitive content across your organization. This report identifies sites containing [files with sensitivity labels applied](/en-us/microsoft-365/compliance/sensitivity-labels-sharepoint-onedrive-files), allowing you to verify that appropriate security policies are applied.

Learn how to use the [sensitivity labels for files report](data-access-governance-sensitivity-label-report).

## What is the sharing links report?

The sharing links report is one of two activity reports that helps you identify sites where users created the most new sharing links in the last 28 days.

Learn how to create and use the [sharing links report](data-access-governance-sharing-links-report).

## What is the 'Everyone except external users' (EEEU) report?

EEEU is a built-in SharePoint group that automatically includes all internal users but excludes any external guests. The 'Everyone except external users' (EEEU) report is one of two activity reports that helps you identify sites where content is shared with your entire organization in the past 28 days. You can run the site permissions for your organization report first to understand your organization's current EEEU sharing status, then use this activity report to monitor ongoing EEEU sharing activities. See [Monitor 'Everyone except external users' (EEEU) sharing with the EEEU activity report](/en-us/sharepoint/data-access-governance-everyone-except-external-user-report).

## Limitations or known issues

- Reports might not work if you select nonpseudonymized report data for your organization. To change this setting, you must be a Global Administrator. Go to the [Reports setting in the Microsoft 365 admin center](https://admin.microsoft.com/#/Settings/Services/:/Settings/L1/Reports) and clear **Display concealed user, group, and site names in all reports**.

## Remedial actions from Data access governance reports

After discovering potential oversharing through Data access governance reports, take several actions to address these risks. When deciding which actions to take, consider:

- The sensitivity of the exposed content
- The amount of content at risk
- The potential disruption to users and workflows

### Available remediation options

**For immediate action:**

- Use [Restricted access control (RAC)](restricted-access-control) to limit access to a specific group.
- Review the ['Change history' report](change-history-report) to identify recent permission changes that might have led to oversharing.

**For collaborative remediation:**

- Use the [Site access review feature](site-access-review) to request that site owners review and update permissions.

This approach ensures you can balance security needs with minimal disruption to your organization's productivity.