---
layout: Conceptual
title: Get started with agents in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/get-started-sharepoint-agents
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-10-15T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.reviewer: 
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
f1.keywords:
- NOCSH
ROBOTS: NOINDEX, NOFOLLOW
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: ai-copilot
ms.collection:
- M365-collaboration
- m365copilot
- magic-ai-copilot
- Tier2
- M365-sam
ms.localizationpriority: medium
search.appverid:
- MET150
description: 'Learn how admins can get started with agents in SharePoint, including setting up pay-as-you-go billing and managing Azure resources for agents. '
locale: en-us
document_id: 90db3c80-337e-40b7-ef21-23332ec8e158
document_version_independent_id: 4e31f327-cb06-4ca7-91ef-281bdc0a75ff
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/get-started-sharepoint-agents.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: get-started-sharepoint-agents
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/get-started-sharepoint-agents.md
platformId: ffd444d1-3d7b-e541-0280-fd62736d0db7
---

# Get started with agents in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn

Important

Microsoft is upgrading the agent experience (.agent files) in SharePoint to better align with the Microsoft Copilot extensibility ecosystem. By using the new agent experience, agents in SharePoint can be part of the Copilot app home experience and the [Microsoft plugin registry](https://techcommunity.microsoft.com/blog/microsoft-copilot-blog/introducing-the-plugin-registry---one-place-to-discover-and-govern-plugins-for-m/4559682).

To learn more, see [Upgrade agents in SharePoint and OneDrive](upgrade-sharepoint-agents).

[Agents in SharePoint](https://support.microsoft.com/office/get-started-with-agents-in-sharepoint-69e2faf9-2c1e-4baa-8305-23e625021bcf), powered by AI, help users quickly find information and insights on SharePoint sites, pages, and document libraries. These agents access your organization's data the same way Copilot in other Microsoft 365 apps does, responding to users based on their access permissions to the data. This article discusses how admins can get started with agents in SharePoint, including setting up pay-as-you-go billing and managing Azure resources for agents.

## Understand who can set up and use agents

Agents in SharePoint don't require activation. Once a user is assigned a Copilot license, or if your organization uses pay-as-you-go billing, these agents automatically become available to the user on eligible sites where they have permissions.

| **Action** | **Requirements for the user** |
| --- | --- |
| **Create an agent** | - Assigned with a Copilot license. - Ability to add new files to a SharePoint site. |
| **Configure and interact with an agent** | - Assigned with a Copilot license or your organization has the pay-as-you-go billing set up for you. |

Important

If your organization hasn't adopted Microsoft Copilot, review the requirements and learn how to adopt it for your organization. [Learn more](/en-us/microsoft-365/copilot/microsoft-365-copilot-overview).

## Use agents with Copilot licenses

Users can use agents in SharePoint after being [assigned a Copilot license](/en-us/microsoft-365/copilot/microsoft-365-copilot-enable-users#assign-licenses). Use the [Microsoft Copilot setup guide](https://admin.microsoft.com/Adminportal/Home?Q=learndocs#/modernonboarding/microsoft365copilotsetupguide) in the Microsoft 365 admin center to assign the required licenses to users. For more information, see [Assign licenses to users in the Microsoft 365 admin center](/en-us/microsoft-365/admin/manage/assign-licenses-to-users) and [Microsoft Copilot requirements](/en-us/microsoft-365/copilot/microsoft-365-copilot-requirements). To learn more, see [controlling user access through licensing](/en-us/sharepoint/manage-access-agents-in-sharepoint#control-user-access-through-licensing).

## Use agents with pay-as-you-go billing

To use agents with pay-as-you-go billing, first set up SharePoint agents as a resource in Azure. Whenever a user without a Microsoft Copilot license uses an agent in SharePoint, their usage uses that resource. For more information, see [Use agents with pay-as-you-go billing](/en-us/sharepoint/sharepoint-agents-azure-billing).

## Comparison of Copilot licenses and pay-as-you-go billing

What does the user get with pay-as-you-go billing and a Copilot license? Here's a comparison:

| [Licensed for Microsoft Copilot](/en-us/microsoft-365/copilot/microsoft-365-copilot-licensing) | [Pay-as-you-go](/en-us/sharepoint/sharepoint-agents-azure-billing)Enabled | What does the user get? |
| --- | --- | --- |
| No | No | Cannot create or use agents. |
| No | Yes | All unlicensed users can use agents and are billed per pay-as-you-go billing. |
| Yes | No | - Licensed users can create and use agents. - Unlicensed users can't create or use agents. |

## Monitor agent usage

Users with at least site visitor permissions can check the agent's file statistics, use search to find all agents for bulk actions, and see site usage. SharePoint admins can use the SharePoint Online Management Shell, Microsoft Purview audit log, Microsoft Cost Management, and SharePoint Advanced Management to monitor agent usage at the organization level. For more information, see [Monitor agent usage in SharePoint](/en-us/sharepoint/monitor-agent-usage).