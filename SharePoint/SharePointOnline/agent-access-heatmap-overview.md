---
layout: Conceptual
title: Agent access heatmap overview (preview) - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/agent-access-heatmap-overview
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
description: Learn what the agent access heatmap is, the key concepts behind it, and how it shows which Microsoft 365 content agents use, whose content it is, how sensitive it is, and whether agents read or update it.
ms.date: 2026-11-11T00:00:00.0000000Z
ms.topic: concept-article
ms.service: sharepoint-online
ms.collection: bap-ai-copilot
author: nibandyo
ms.author: nibandyo
ms.reviewer: stephkent
manager: leeclontz
locale: en-us
document_id: f1e549e6-eda3-feb9-952f-68a2a7254972
document_version_independent_id: 082a4b63-d2ce-64cf-fd0c-2f06e81b8c8a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/agent-access-heatmap-overview.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: agent-access-heatmap-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/agent-access-heatmap-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 7f105a5f-9dd9-43f4-3ab6-07a46df71118
---

# Agent access heatmap overview (preview) - SharePoint in Microsoft 365 | Microsoft Learn

Important

The agent access heatmap is in preview. Features and terminology described in this article might change before general availability.

An agent is only as useful, and as risky, as the content it can reach. As agents become part of everyday work, you need a clear picture of which content they use, so you can keep useful access in place, govern the rest, and scale agents with confidence.

The agent access heatmap gives you that picture. It's a content-first view of agent activity across your Microsoft 365 content, available in the new [Agent governance](agent-governance-overview) node in the SharePoint admin center. For a period you choose, the heatmap shows which SharePoint sites, OneDrive accounts, and Teams-connected sites agents accessed, which business group owns that content, how sensitive it is, and whether agents only read it or also create and update it. From there, you can drill into a specific site, see which agents use it, and act without leaving the report.

Note

The business group and sensitivity views rely on two features that not every organization uses: business groups (departments) in catalog management and sensitivity labels applied to sites. Organizations that use both get the full heatmap experience. If your organization uses only one, the heatmap shows the view for that one.

## Questions the heatmap helps you answer

Admins tend to start with the same four questions. The heatmap is organized so that each one has a direct answer.

| **Question** | **Where the heatmap answers it** |
| --- | --- |
| Which content are agents using? | The dashboard and the heatmap show which SharePoint sites, OneDrive accounts, and Teams-connected sites agents accessed, and which kinds of agents accessed them. |
| Whose content is it? | The business group view groups activity by the business group that owns the content. The site view shows who owns each site. |
| How sensitive is it? | The sensitivity view groups activity by the sensitivity label applied to each site. |
| Do agents only read it, or also update it? | Actions show the operations agents performed, such as reading, modifying, or uploading files. |

## How the heatmap fits with Microsoft Agent 365

Microsoft Agent 365 is the control plane for agents. It helps you observe, govern, and secure the agents in your organization. The Agent 365 registry tells you which agents you have. The agent access heatmap tells you what content those agents use. Together, they give you an agent-first view and a content-first view of the same activity. You can open the heatmap from the Agent 365 experience or directly from the SharePoint admin center.

The heatmap is one part of [agent governance](agent-governance-overview) in the SharePoint admin center:

| **Capability** | **What it helps you do** |
| --- | --- |
| Overview | Get a summary of agent activity across your content and go to the reports and settings you need. |
| Agent access heatmap | Find where agents access your content, broken down by agent platform, business group, sensitivity, and action. |
| Settings | Set content guardrails once, on an agent blueprint, so every agent created from that blueprint follows them, including agents created in the future. |

A common pattern is to observe activity with the heatmap, act on a specific site when a finding calls for it, and then set content guardrails so the same intent applies to every agent in scope. Learn more in [View agent activity in the agent governance overview](agent-governance-overview).

## Key concepts

These are the main ideas behind the heatmap. Learn more about report contents and how to work with reports in Generate a report and explore the agent access heatmap.

| **Concept** | **What it means** |
| --- | --- |
| Report | A snapshot of agent activity across your Microsoft 365 content for a period you choose. Everything you see in the heatmap comes from a report. Each report reflects your organization's settings at the time it was generated, so you generate a new report to see how activity changes. |
| Dashboard | Where you explore a report. It summarizes agent activity across your content and contains the heatmap. |
| Heatmap | A grid with agent platforms as rows and business groups or sensitivity labels as columns. Each cell shows how many sites, OneDrive accounts, and Teams-connected sites agents from that platform accessed. Darker cells mean more. |
| Agent platform | The kind of agent, such as Copilot Studio agents, agents in SharePoint, or third-party agents. |
| Views | The business group view shows whose content agents use, based on departments in catalog management. The sensitivity view shows how sensitive that content is, based on the sensitivity labels applied to sites. |
| Actions | What agents did with the content, such as reading, modifying, or uploading files. |
| Site view | A single site, with its owner, the agents that use it, and what they did there. |
| Governance actions | Actions you can take on a site directly from the heatmap, such as restricting content discovery or restricting site access. |
| Detailed report | A download of the full data behind a report, for analysis outside the SharePoint admin center. |

## Basic scenarios

The following scenarios are a good place to start. Each one takes a few selections from the dashboard.

| **Scenario** | **Where to look** | **Typical next step** |
| --- | --- | --- |
| Find the content agents use most | The dashboard summary, and the heatmap cells with the most resources. | Drill into a site to see which agents use it and what they do there. |
| Find out whose content agents use | Business group view. | Bring that group's site owners into the review. |
| Check whether agents use your most sensitive content | Sensitivity view, filtered to your highest labels. | Review the sites and agents with the site owners. Restrict content discovery or site access where agent use isn't expected. |
| See whether agents only read content or also update it | Actions for each site, in the details pane and the site view. | Confirm with the site owner whether that activity is expected. |
| Confirm that activity matches what you expect | Rows for agents you expect to be active, such as broadly deployed Copilot agents. | If it matches, no action is needed. Generate reports regularly to see how activity changes. |

Learn more about generating and exploring reports in Generate a report and explore the agent access heatmap.

## Prerequisites

Before you start using the heatmap report, make sure you have:

- Microsoft Agent 365 or Microsoft 365 E7 license. For licensing questions, see [Microsoft Product Terms](https://go.microsoft.com/fwlink/?linkid=2309718) or contact your Microsoft account representative.
- The [SharePoint Administrator role](sharepoint-admin-role) or the AI Administrator role.

## Get started

You can generate your first heatmap report within a few hours. The steps are:

1. For the full heatmap experience, apply sensitivity labels to your sites and set up business groups in catalog management.
2. In the SharePoint admin center, expand **Agent governance**, select **Agent access heatmap**, and turn on data collection if it isn't already on.
3. After data is available, generate a report for the reporting period you want, and then open it to explore the heatmap.

Learn more about each step in Generate a report and explore the agent access heatmap.

## What the heatmap covers

The heatmap shows agent activity on SharePoint sites, OneDrive accounts, and Teams-connected sites. It includes declarative agents, Agent 365 agents, and Microsoft and third-party agents registered in Microsoft Entra ID.

Keep these points in mind as you use it:

- The heatmap reports on a period you choose. It isn't real-time monitoring.
- The heatmap is a governance visibility tool. It doesn't replace audit log analysis, per-file diagnostics, or security investigations, and it doesn't show end-user identities.
- If you use the agent access insights report under **Reports** &gt; **Agent insights**, that report remains available. The heatmap, the business group and sensitivity views, and actions are available in **Agent governance**.

## Related information

- [Agent governance in SharePoint and OneDrive overview](agent-governance-overview)
- [Monitor agent access to SharePoint and OneDrive](insights-on-agent-access)
- [Catalog management in SharePoint Advanced Management](catalog-management)
- [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](/en-us/purview/sensitivity-labels-teams-groups-sites)
- [Microsoft Agent 365 documentation](/en-us/microsoft-agent-365/)