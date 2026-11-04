---
layout: Conceptual
title: Manage access to agents in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/manage-access-agents-in-sharepoint
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-10-15T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.reviewer: 
ms.author: deniseb
author: cjtancortex
manager: corywink
audience: Admin
customer-intent: As a SharePoint administrator, I want to manage access to agents in SharePoint with built-in SharePoint permission models, SharePoint Advanced Management features such as restricted access control, restricted content discovery, and Microsoft Purview Data Loss Prevention (DLP).
f1.keywords:
- NOCSH
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
description: Learn how to manage access to agents in SharePoint with built-in SharePoint permission models, SharePoint Advanced Management features such as restricted access control, restricted content discovery, and Microsoft Purview Data Loss Prevention (DLP).
locale: en-us
document_id: 7ae7f971-1041-ea1b-47fb-59768eb9093c
document_version_independent_id: f4b5d698-d50d-290f-f15c-de04c16338ea
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/manage-access-agents-in-sharepoint.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-access-agents-in-sharepoint
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/manage-access-agents-in-sharepoint.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
platformId: a4928f38-8a17-ecc3-7361-eadcf5854200
---

# Manage access to agents in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn

Important

Microsoft is upgrading the agent experience (.agent files) in SharePoint to better align with the Microsoft Copilot extensibility ecosystem. By using the new agent experience, agents in SharePoint can be part of the Copilot app home experience and the [Microsoft plugin registry](https://techcommunity.microsoft.com/blog/microsoft-copilot-blog/introducing-the-plugin-registry---one-place-to-discover-and-govern-plugins-for-m/4559682).

To learn more, see [Upgrade agents in SharePoint and OneDrive](upgrade-sharepoint-agents).

Agents in SharePoint, powered by AI, help users quickly find information and insights on SharePoint sites, pages, and document libraries. Agents in SharePoint access your organization's data the same way Copilot in other Microsoft 365 apps does, responding to users based on their access permissions to the data. As a SharePoint admin, you can manage users' access to an agent in multiple ways by managing:

- Who can access the agents
- What information the user can access through the agent
- Where agents are available

## Manage who can access the agents

Agents in SharePoint don't require activation. You can manage who can access agents through Copilot license assignment. Or, if your organization has the pay-as-you-go billing set up, you can control who can access agents through the security groups assigned to the billing policy. Learn more about [setting up pay-as-you-go billing for agents in SharePoint](/en-us/sharepoint/sharepoint-agents-azure-billing).

### Control user access through licensing

Currently, users with a [Microsoft Copilot license](/en-us/microsoft-365/copilot/microsoft-365-copilot-licensing) can use the agents. You can use the [Microsoft Copilot setup guide](https://admin.microsoft.com/Adminportal/Home?Q=learndocs#/modernonboarding/microsoft365copilotsetupguide) in the Microsoft 365 admin center to assign the required licenses to users. For more information, see [Assign licenses to users in the Microsoft 365 admin center](/en-us/microsoft-365/admin/manage/assign-licenses-to-users) and [Microsoft Copilot requirements](/en-us/microsoft-365/copilot/microsoft-365-copilot-requirements).

Admins can choose to edit the service plans under the Copilot license to specifically allow or block users from using Copilot experiences on SharePoint. Under the [license details page for Microsoft Copilot](https://admin.microsoft.com/Adminportal/Home?#/licensedetailpage/639dec6b-bb19-468b-871c-c5c441c4b0cb) on the Microsoft 365 admin center, admins can turn *'Microsoft Copilot for SharePoint'* on or off on a per-user basis. For example, a user could be allowed to use Microsoft Copilot on Teams but not use any agents on SharePoint alone. However, this change also disables Copilot in OneDrive and on the SharePoint page authoring Copilot for that user.

### Control user access through pay-as-you-go billing

For users who aren't assigned with a Microsoft Copilot license, you can control user access to agents through pay-as-you-go billing. To do so, you need to first set up SharePoint agents as a resource in Azure. Then, you set up a pay-as-you-go policy that is assigned to a security group. You can link that policy to the agent resource in SharePoint. Only users in the security group assigned to the billing policy have access to agents. For more information, see [Use agents with pay-as-you-go billing](/en-us/sharepoint/sharepoint-agents-azure-billing).

### Use file permissions on a specific agent file

Agents in SharePoint are represented as [.agent files](https://support.microsoft.com/office/create-and-edit-an-agent-d16c6ca1-a8e3-4096-af49-67e1cfdddd42#where-agent-file). The permissions on the `.agent` file determine who can access or edit the agent. Only users who can create or access files on a SharePoint site can create or access agents.

Note

For users who access and use an agent in SharePoint, the agent's responses depend on each user's permissions to the agent's data sources. For instance, if a user has access to the agent but not to the site or document library it references, the agent's responses for this user don't include content from those restricted sources.

## Manage what information a user can access through the agents

### Use built-in SharePoint features

Agents in SharePoint use SharePoint sites, pages, and document libraries as knowledge sources to respond to the user. You can control a user's access to the information when they use an agent by controlling their access to the site. SharePoint provides many tools to control access to a site:

- Control access to a site that is associated with a [Microsoft 365 Group](/en-us/microsoft-365/solutions/collaboration-governance-overview) by [setting the site as private](https://support.microsoft.com/office/change-a-site-s-title-description-logo-and-site-information-settings-8376034d-d0c7-446e-9178-6ab51c58df42) (team sites only) and controlling group membership.
- Control access to a site that isn't associated with a group by using [site permissions](/en-us/sharepoint/site-permissions).
- Control access by using access governance policies available in the SharePoint admin center and PowerShell.

### Use SharePoint Advanced Management

Currently, to restrict access to a site by Microsoft Copilot, the SharePoint admin can set up a [restricted access control policy](/en-us/sharepoint/restricted-access-control). As a result, all access to the site is restricted to only the group of users specified in the policy. Accordingly, the content from the site is visible in Microsoft Copilot only for this restricted group of users. You can restrict access to individual sites or OneDrive. To learn more about features to prevent oversharing, control access, and enhance your content governance, see [What is SharePoint Advanced Management?](/en-us/sharepoint/advanced-management).

### With Microsoft Purview Data Loss Prevention (DLP)

To prevent selected files from being used by agents, use sensitivity labels along with [Microsoft Purview Data Loss Prevention (DLP)](/en-us/purview/dlp-learn-about-dlp). By creating a DLP custom policy with the **Content contains** &gt; **Sensitivity labels** condition, you can [prevent sharing of sensitive content with external users](/en-us/purview/dlp-create-deploy-policy#scenario-2-block-sharing-of-sensitive-items-via-sharepoint-and-onedrive-in-microsoft-365-with-external-users) and exclude items from being processed. The citations in the response include identified items, but the content of the item isn't used in the response. You can't yet add a sensitivity label directly to the [.agent file](https://support.microsoft.com/office/create-and-edit-an-agent-d16c6ca1-a8e3-4096-af49-67e1cfdddd42#where-agent-file). If you want to govern your `.agent` file by using DLP, use conditions based on the `.agent` extension instead of using sensitivity labels as the condition.

## Manage where agents are available

### Site owner controls in SharePoint

Agents that you create in SharePoint don't automatically appear in any list or published location. Users can manually go to *.agent* files to use them, just like how they discover or use Word or Excel files. Site owners can choose one main agent for their site. This agent opens when users select the Agent icon in the global header. For more information, see [Manage agents in SharePoint](https://support.microsoft.com/en-us/office/manage-agents-in-sharepoint-bcab837a-835c-4a1a-8ad4-d53a353c369f).

### Turn off agents on sites with restricted content discovery

As a SharePoint admin, you can turn off all agent-related features on individual sites by using the [restricted content discovery](/en-us/sharepoint/restricted-content-discovery) feature. Once you flag a site with restricted content discovery, users can't see the Agent icon on the global header of the site. Therefore, they don't have access to use the ready-made agent, create new agents, or add content from that site to any other agents. The restricted content discovery policy leaves site access unchanged but prevents the site's content from being surfaced in Microsoft Copilot or organization-wide search for all users.

### Block agents from being used in Copilot Chat

Tenant admins and AI admins can manage actively used agents in SharePoint in the Microsoft 365 admin center, under the **Agents** section of the Copilot Control System (formerly known as integrated apps). This experience gives administrators a clear overview of all agents ever used in Copilot Chat, with the ability to view details and block or unblock any agent for use in Microsoft Copilot, all from one place. For more information, see [Manage Copilot agents in the Microsoft 365 admin center](/en-us/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps).

![Agent Inventory](sharepointonline/media/agents-sharepoint/agent-inventory.png)

Note

Currently, blocking an agent only affects its availability in Copilot Chat. It doesn't yet apply to OneDrive, SharePoint, or Teams.