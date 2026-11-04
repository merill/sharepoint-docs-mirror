---
layout: Conceptual
title: SharePoint Admin Agent overview - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/content-governance-agent
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-10-09T00:00:00.0000000Z
ms.reviewer: daminasy
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
customer-intent: As a SharePoint administrator, I want to use the SharePoint Admin Agent in SharePoint Advanced Management to help me manage permissions, storage, and site lifecycle tasks more efficiently.
f1.keywords: NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: ai-copilot
ms.localizationpriority: medium
ms.collection:
- Strat_SP_admin
- Highpri
- Tier2
- M365-sam
- M365-collaboration
- M365-sam
ms.custom:
- admindeeplinkSPO
search.appverid: 
description: In this article, you learn about how to use the SharePoint Admin Agent in SharePoint Advanced Management to help you manage permissions, storage, and site lifecycle tasks more efficiently.
locale: en-us
document_id: d420782f-9f4d-961a-54fe-0dbdb7ff04a5
document_version_independent_id: 8456f12a-24f1-d130-e086-9a59e936cd61
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/content-governance-agent.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: content-governance-agent
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/content-governance-agent.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 88779be4-8be4-5f52-04f0-87fb1029f249
---

# SharePoint Admin Agent overview - SharePoint in Microsoft 365 | Microsoft Learn

The SharePoint Admin Agent is an AI-powered governance experience that helps your administrators assess and remediate content-related risks across your SharePoint and OneDrive environments. Instead of running reports manually, use natural language queries to investigate tenant-level conditions and take guided remediation actions.

**Video: Overview of the SharePoint Admin Agent**

The following video provides an overview of the SharePoint Admin Agent:

[Microsoft Copilot](/en-us/microsoft-365/copilot/microsoft-365-copilot-overview) (Copilot) and [Agents](/en-us/microsoft-365/copilot/extensibility/agents-overview) work best when SharePoint and OneDrive content is well-governed, relevant, and securely accessible. The SharePoint Admin Agent helps by enabling your administrators to move quickly from assessment to action using a conversational interface. It analyzes data drawn from SharePoint and [SharePoint Advanced Management](/en-us/sharepoint/advanced-management) (SAM) to provide contextual insights aligned to governance priorities, such as:

- Managing content sprawl
- Managing the content lifecycle
- Preventing oversharing in search and AI responses
- Managing permissions and access to content and sites

## How the SharePoint Admin Agent helps with content governance

Use the SharePoint Admin Agent to get started with these important content governance tasks:

- **Assess whether your organization is ready for Copilot** with [content management assessment](/en-us/sharepoint/content-management-assessment) capabilities
- **Control your content structure** with [catalog management](/en-us/sharepoint/catalog-management) capabilities
- **Manage the content lifecycle** with site lifecycle management policies, such as the [site ownership policy](/en-us/sharepoint/site-ownership-policy), [inactive sites policy](/en-us/sharepoint/inactive-site-policy), and [site attestations](/en-us/sharepoint/request-site-attestations), and archive stale content using [Microsoft 365 Archive](/en-us/microsoft-365/archive/archive-overview)
- **Prevent accidental oversharing** with [data access governance reports](/en-us/sharepoint/data-access-governance-reports) and policies
- **Control access to content** with reports, [site access reviews](/en-us/sharepoint/site-access-review), and policies like [Conditional Access](/en-us/sharepoint/authentication-context-example), [restricted access control](/en-us/sharepoint/restricted-access-control), and [restricted content discovery](/en-us/sharepoint/restricted-content-discovery)
- **Implement content resilience** with [Baseline Security Mode settings](/en-us/microsoft-365/baseline-security-mode/baseline-security-mode-settings), [Microsoft 365 Backup](/en-us/microsoft-365/backup/backup-overview), and [version history](/en-us/sharepoint/version-overview)
- **Manage data residency compliance** with [Multi-Geo capabilities](/en-us/microsoft-365/enterprise/m365-dr-service-spo#multi-geo-capabilities-in-sharepoint--onedrive), such as cross-geography content move status reports (*Preview*)

## SharePoint Admin Agent prerequisites

Your organization must have SharePoint Advanced Management. See [SharePoint Advanced Management prerequisites](sharepoint-advanced-management-prerequisites).

To use the SharePoint Admin Agent, you must have the [SharePoint Advanced Management Administrator](/en-us/entra/identity/role-based-access-control/permissions-reference#sharepoint-advanced-management-administrator) role assigned in Microsoft Entra ID.

## Open the SharePoint Admin Agent

[![Screenshot showing the SharePoint Admin Agent experience in the SharePoint admin center.](sharepointonline/media/content-governance-agent/copilot-sharepoint-admin-center.png)](sharepointonline/media/content-governance-agent/copilot-sharepoint-admin-center.png#lightbox)

Open the SharePoint Admin Agent by using any of the following methods:

- Open the SharePoint Admin Agent in the Microsoft Copilot app
- Access content governance skills for Copilot in the SharePoint admin center
- Open the SharePoint Admin Agent in Microsoft Teams

### Open the SharePoint Admin Agent in Microsoft Copilot

In the Microsoft Copilot app, expand **Agents**, and search for the SharePoint Admin Agent.

[![Screenshot depicting how to add the SharePoint Admin Agent in the Microsoft Copilot app.](sharepointonline/media/content-governance-agent/admin-agent-copilot.png)](sharepointonline/media/content-governance-agent/admin-agent-copilot.png#lightbox)

Use the agent in the Copilot app.

[![Screenshot showing the SharePoint Admin Agent open in the Copilot app](sharepointonline/media/content-governance-agent/admin-agent-open-in-copilot.png)](sharepointonline/media/content-governance-agent/admin-agent-open-in-copilot.png#lightbox)

### Access content governance skills in Copilot in the SharePoint admin center

Copilot in the SharePoint admin center includes content governance skills.

[![Screenshot showing the Copilot in the SharePoint Admin Center.](sharepointonline/media/content-governance-agent/copilot-sharepoint-admin-center.png)](sharepointonline/media/content-governance-agent/copilot-sharepoint-admin-center.png#lightbox)

Select the **Copilot** button, and then select the **View prompts** button to view and use governance skills.

![Image of the Content governance prompts button.](sharepointonline/media/content-governance-agent/prompts.png)

### Open the SharePoint Admin Agent in Microsoft Teams

In Microsoft Teams, select **Apps**, and then search for *SharePoint Admin Agent*.

[![Screenshot showing how to find the SharePoint Admin Center in Microsoft Teams.](sharepointonline/media/content-governance-agent/search-sharepoint-admin-agent-teams.png)](sharepointonline/media/content-governance-agent/search-sharepoint-admin-agent-teams.png#lightbox)

## Get started with example prompts

To help you get started, the SharePoint Admin Agent suggests prompts that you can try in your environment.

[![Screenshot showing how to get started with example prompts using the SharePoint Admin Agent.](sharepointonline/media/content-governance-agent/getting-started-sp-admin-agent.png)](sharepointonline/media/content-governance-agent/getting-started-sp-admin-agent.png#lightbox)

As you submit a question, the SharePoint Admin Agent responds by gathering the relevant data and reports, offering analysis and recommendations, and suggesting other prompts. You can choose appropriate next steps from there.

The following sections include other example prompts to try.

### Content distribution

```console
Show me how my content is distributed across my tenant
```

### Storage information

```console
Show me storage information. Include my storage quota, storage used, and site counts
```

### Sites with low activity

```console
Identify sites with low activity by department
```

### Overshared sites and risk

```console
Which sites are overshared and what are the risk levels for these sites?
```

### Overshared Teams-connected sites

```console
Give me details about Teams-connected sites that are overshared
```

### Top 10 agents accessing content

```console
Show me a list of the top 10 agents that are accessing my SharePoint and OneDrive content
```

### Baseline security mode

```console
Is Baseline Security Mode enabled in my tenant?
```

### Recovery options

```console
What recovery options are available for my SharePoint and OneDrive sites?
```

### OneDrive libraries to move to another geo

(This feature is available for [multi-geo organizations](/en-us/microsoft-365/enterprise/microsoft-365-multi-geo).)

```console
Show me users whose OneDrive libraries need to be moved to another location
```

### Cross-geo moves that failed

(This feature is available for [multi-geo organizations](/en-us/microsoft-365/enterprise/microsoft-365-multi-geo).)

```console
Show me cross geo moves that have failed
```

### Status of cross-geo moves

(This feature is available for [multi-geo organizations](/en-us/microsoft-365/enterprise/microsoft-365-multi-geo).)

```console
Show me the status of all cross geo moves initiated in past 7 days
```