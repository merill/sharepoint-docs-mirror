---
layout: Conceptual
title: Assess your organization's content management status - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/content-management-assessment
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-05-05T00:00:00.0000000Z
ms.reviewer: daminasy
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
customer-intent: As a SharePoint administrator, I want to assess my organization's current content management status.
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
description: In this article, you learn about how to assess your organization's current content management status and identify areas for improvement.
locale: en-us
document_id: e1503ee2-20de-1de2-65bf-08e678047038
document_version_independent_id: fc224ef0-3e2c-325e-e5cb-a32704c3032d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/content-management-assessment.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: content-management-assessment
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/content-management-assessment.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 4583bb36-42aa-b4f6-c732-cfe279041e96
---

# Assess your organization's content management status - SharePoint in Microsoft 365 | Microsoft Learn

[SharePoint Advanced Management](/en-us/sharepoint/advanced-management) (SAM) provides a comprehensive set of tools for assessing and improving your organization's content management practices with actionable insights and recommendations. Content Management Assessment is the hub for these capabilities.

![Screenshot of the SharePoint Advanced Management Content Management Assessment dashboard showing the assessment results with impacted sites on the left and report findings panel on the right.](sharepointonline/media/sam-content-management-assessment/sam-content-management-assessment.png)

## What is Content Management Assessment?

Content Management Assessment is a built-in, easy-to-use feature of SharePoint Advanced Management. With just one click, you can quickly check and improve how your organization manages content within SharePoint environments. Content Management Assessment provides a simple, guided process for administrators to:

- Identify potentially overshared content
- Find issues or risks (such as inactive or ownerless sites)
- Define Copilot readiness for the organization
- Ensure compliance and maintain data integrity
- Receive actionable recommendations for remediation
- Track progress over time with recurring assessments

The assessment uses the SharePoint Advanced Management (SAM) toolkit, running a suite of essential reports to surface key findings and categorize sites that might require attention. It makes content governance accessible and actionable, even for admins who might not have deep technical expertise.

## Included reports

Currently, the Content Management Assessment includes the following reports:

- **[Inactive sites report](/en-us/sharepoint/inactive-site-policy)**: Identifies sites with no activity in the past 180 days.
- **[Site ownership report](/en-us/sharepoint/site-ownership-policy)**: Detects sites without owners or with only one owner.
- **[Broken inheritance report](/en-us/sharepoint/what-is-permissions-inheritance)**: Finds sites where permission inheritance is broken.
- **[Unrestricted internal sharing via EEEU (Everyone Except External Users) report](/en-us/sharepoint/data-access-governance-reports#what-is-the-everyone-except-external-users-eeeu-report)**: Locates content shared with all internal users.
- **[Unrestricted sharing via sharing links](/en-us/sharepoint/data-access-governance-reports#what-is-the-sharing-links-report)**: Discovers content shared through overly permissive sharing links.

Note

- Depending on the size of the tenant, reports can take between 2 hours and 72 hours to run.
- Reports run on all sites across the organization. They don't take any action without the admin's consent.

## Why use Content Management Assessment?

Organizations face increasing complexity in managing content across large Microsoft 365 tenants. Common challenges include:

- Uncertainty about where to start with governance.
- Difficulty identifying whether there are actual problems or risks.
- Lack of clarity on whether existing governance measures are sufficient.
- The need for ongoing monitoring and improvement.

Content Management Assessment addresses these challenges by:

- **Automating discovery**: Automatically discover and categorize potentially impacted sites without manual intervention.
- **Clear, actionable findings**: Provide a clear list of issues with specific recommended next steps for each finding.
- **Eliminating manual work**: Reduce the need for custom scripts or manual audits, which can be time-consuming and error-prone.
- **On-demand reassessment**: Allow administrators to rerun the assessment monthly to ensure continuous improvement and compliance.

## What do you need to access Content Management Assessment?

See [SharePoint Advanced Management prerequisites](sharepoint-advanced-management-prerequisites).

## Where to find Content Management Assessment

You can access Content Management Assessment in the SharePoint Admin Center:

1. Sign in to the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219).
2. In the navigation pane, select **Advanced Management**.
3. Look for the new assessment starting screen, as shown in the following image:

    ![Screenshot of the SharePoint Advanced Management Content Management Assessment dashboard showing the start assessment button.](sharepointonline/media/sam-content-management-assessment/start-content-management-assessment.png)

    (Previously, the menu-based view was available under **All Features**).
4. Select **Start assessment**.

The assessment automatically runs the relevant SAM reports, analyzes the results, and presents findings in a user-friendly dashboard, which includes:

- Visual summary of impacted sites
- Report findings, which list impacted sites, specific findings, and recommended actions for remediation. You can select each of the findings to see more details and related Microsoft Learn documentation to address the issue.
- The latest guidelines and documentation related to these policies.

## Next steps after running the assessment

1. **Review findings**: Examine the list of sites flagged as potentially impacted. The dashboard shows both the number and details of these sites.
2. **Take action**: For each finding, follow the recommended steps provided. These steps might include:

    - Creating or adjusting site policies, such as for potential oversharing, inactivity, or ownership.
    - Using built-in tools to fix problems.
    - Consulting linked documentation for further guidance.
3. **Monitor progress**: Rerun the assessment every 30 days to track improvements and catch new problems.