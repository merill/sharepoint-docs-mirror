---
layout: Conceptual
title: SharePoint Advanced Management overview - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/advanced-management
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: false
ms.date: 2026-10-28T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.reviewer: daminasy
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
customer-intent: As an IT admin, I want to understand what SharePoint Advanced Management is and how it can help me govern SharePoint and OneDrive content.
f1.keywords:
- NOCSH
ms.topic: concept-article
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Highpri
- Tier2
- M365-sam
- M365-collaboration
search.appverid:
- MET150
description: Learn how SharePoint Advanced Management capabilities to govern SharePoint and OneDrive content by controlling content sprawl, managing the content lifecycle, and prevent oversharing.
ai-usage: ai-assisted
locale: en-us
document_id: e9aa1a91-e838-41c6-45cb-6a2a4dbf1a7a
document_version_independent_id: 5f5c1b99-126f-2a70-20c8-f00136927e31
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/advanced-management.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: advanced-management
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/advanced-management.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: e636fd6f-c981-6419-bc59-ebfc23f64c93
---

# SharePoint Advanced Management overview - SharePoint in Microsoft 365 | Microsoft Learn

SharePoint Advanced Management (SAM) provides administrative governance controls for SharePoint and OneDrive that help organizations:

- **Manage content sprawl**;
- **Manage the content lifecycle**; and
- **Prevent oversharing**.

**Video: SharePoint Advanced Management overview**

Watch the following video to get an overview of SharePoint Advanced Management:

Administrators primarily manage SAM through the SharePoint admin center. It's designed for SharePoint and Microsoft 365 administrators who are responsible for governance, risk reduction, and audit readiness. You can also use the [SharePoint Admin Agent](/en-us/sharepoint/content-governance-agent) to make your SharePoint administration more productive and efficient.

[![Screenshot of advanced management in the SharePoint admin center.](sharepointonline/media/sam-overview/advanced-management.png)](sharepointonline/media/sam-overview/advanced-management.png#lightbox)

## Manage content sprawl

SAM helps administrators identify, assess, and reduce unnecessary or unmanaged SharePoint and OneDrive content to help strengthen your governance posture, improve storage utilization, and enhance the relevance of Copilot and Agentic responses.

- **[Create a site ownership policy](/en-us/sharepoint/site-ownership-policy)**: Define who should be responsible for each site, set minimum owner or admin counts, and automate notifications when sites don't meet your criteria.
- **[Manage inactive SharePoint sites](/en-us/sharepoint/inactive-site-policy)**: Detect inactive sites and notify site owners via email.
- **[Request site attestations](/en-us/sharepoint/request-site-attestations)**: Request regular reviews by site owners or admins to check and confirm the accuracy of site information, including the site's necessity, its owners, members, permissions, and sharing settings.

## Manage the content lifecycle

SAM provides administrators with auditability and traceability over SharePoint configuration changes, supporting compliance, operational reviews, and incident investigation.

- **[Use catalog management to group SharePoint sites](/en-us/sharepoint/catalog-management)**: Organize and govern SharePoint sites by grouping them into logical categories based on regions, departments, users, information barriers, and custom properties.
- **[Create change history reports](/en-us/sharepoint/change-history-report)**: Use history reports to track changes made to individual SharePoint sites or settings over the last 180 days.
- **[Review recent changes to SharePoint site properties](/en-us/sharepoint/recent-actions-panel)**: Review and monitor recent changes admins made to a SharePoint site's properties (such as renaming a site, deleting a site, or changing the storage quota) within the last 30 days.
- **[Restrict site creation by apps](/en-us/sharepoint/restricted-site-creation-by-apps)**: Specify the non-Microsoft applications that can create SharePoint sites in your organization.

## Prevent oversharing

SAM provides layered controls to manage permissions and access, and enforce least-privilege access across SharePoint and OneDrive. SAM capabilities help prevent oversharing by empowering your administrators with reports, insights, and policies that help protect your organization's sensitive information.

- **[Use Conditional Access policies](/en-us/sharepoint/authentication-context-example)**: Use authentication contexts to connect a Microsoft Entra Conditional Access policy to a SharePoint site.
- **[Use restricted access control (RAC)](/en-us/sharepoint/restricted-access-control)**: Restrict access to SharePoint or OneDrive sites to specific groups.
- **[Use the content management assessment](/en-us/sharepoint/content-management-assessment)**: This hub provides a comprehensive set of tools for assessing and improving your organization's content management practices with actionable insights and recommendations.
- **[Set up a "block download" policy](/en-us/sharepoint/block-download-from-sites)**: Create and manage policies to block the ability to move or download files in SharePoint and OneDrive sites, and Teams meeting recordings.
- **[Generate app insights](/en-us/sharepoint/app-insights)**: Gain insights on the various non-Microsoft applications registered to your Microsoft Entra admin center and how they access your SharePoint content.
- **[Get AI insights](/en-us/sharepoint/ai-insights)**: Use the **Get AI insights** button next to various reports in the SharePoint admin center. The AI insights feature extracts patterns from the report and offers a list of potential actions.
- **[Get insights on agents in SharePoint](/en-us/sharepoint/insights-on-sharepoint-agents)**: Use this report to identify recently created agents across SharePoint and OneDrive sites, and identify sites with the highest number of agents created.
- **[Use restricted content discovery (RCD)](/en-us/sharepoint/restricted-content-discovery)**: Prevent high-risk SharePoint sites and files from surfacing in Microsoft Copilot and Agentic experiences.
- **[Use data access governance (DAG) reports for SharePoint and OneDrive sites](/en-us/sharepoint/data-access-governance-reports)**: Identify sites that might contain overshared or sensitive content. AI insights can be generated from DAG reports to highlight access risk patterns and recommend next steps. You can also initiate site access reviews from a DAG report. DAG reports include:
    - **[Permission state reports for sites, OneDrive sites, and files](/en-us/sharepoint/data-access-governance-site-permissions-report)**: Use this report to get a snapshot of your organization's current permission structure across all SharePoint and OneDrive sites, helping you understand how broadly your data is exposed and identify potential oversharing risks.
    - **[Site permissions for a given user report](/en-us/sharepoint/data-access-governance-site-permissions-users-report)**: Use this report to get a list of all the sites a user can access and how access is granted.
    - **[Sensitivity label snapshot report](/en-us/sharepoint/data-access-governance-sensitivity-label-report)**: Use this report to get a snapshot of sensitivity label distribution across all SharePoint and OneDrive sites.
    - **[Sharing links activity reports](/en-us/sharepoint/data-access-governance-sharing-links-report)**: Use these reports to identify sites where users have created the most new sharing links within the last 28 days.
    - **[Everyone except external users (EEEU) insights](data-access-governance-everyone-except-external-user-report)**: Identify the top items or groups shared with EEEU in the last 28 days and policies applied to those sites.
    - **[DAG reports and PowerShell](/en-us/sharepoint/powershell-for-data-access-governance)**: You can use the SharePoint Online PowerShell module to generate DAG reports.
- **[Initiate site access reviews](/en-us/sharepoint/site-access-review)**: Initiate site access reviews to delegate the process of reviewing DAG reports to site owners of overshared sites.
- **[Use site policy comparison reports](/en-us/sharepoint/site-policy-comparison)**: Select one or more sites as your baseline, and then compare them to up to 10,000 target sites using AI.
- **[Monitor agent access to SharePoint and OneDrive sites](/en-us/sharepoint/insights-on-agent-access)**: Use the agent access insights report to see how agents interact with SharePoint and OneDrive content.
- **[Restrict access to OneDrive sites with security groups](/en-us/sharepoint/limit-access)**: If necessary, you can restrict certain users from accessing or sharing OneDrive content by using security groups in Microsoft Entra ID.
- **[Restrict access to a specific user's OneDrive site](/en-us/sharepoint/onedrive-site-access-restriction)**: If necessary, you can restrict access to an individual's OneDrive site by using a security group in Microsoft Entra ID.
- **[Restrict OneDrive and SharePoint site creation](/en-us/sharepoint/restricted-site-creation)**: Using PowerShell, you can designate who can create OneDrive or SharePoint sites by using security groups in Microsoft Entra ID.

## SAM prerequisites

To see the prerequisites for SAM, including the required licenses, roles, and PowerShell module, see [SharePoint Advanced Management prerequisites](sharepoint-advanced-management-prerequisites).