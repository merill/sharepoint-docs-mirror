---
layout: Conceptual
title: Upgrade agents in SharePoint and OneDrive - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/upgrade-sharepoint-agents
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-10-15T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.reviewer: corywink
ms.author: cjtan
author: cjtancortex
manager: corywink
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
search.appverid:
- MET150
ms.localizationpriority: medium
description: 'Learn how to upgrade agents in SharePoint and OneDrive to Microsoft Copilot Agent Builder and Copilot in SharePoint. '
locale: en-us
document_id: 84b4817d-7394-86ac-e738-2729f8684e8d
document_version_independent_id: 064ea4b5-73ae-ad56-471b-76c493b863bc
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/upgrade-sharepoint-agents.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: upgrade-sharepoint-agents
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/upgrade-sharepoint-agents.md
platformId: cf814acd-eb7a-c0a4-0278-997ce93e6c5a
---

# Upgrade agents in SharePoint and OneDrive - SharePoint in Microsoft 365 | Microsoft Learn

Learn how to upgrade your agent experiences in SharePoint and OneDrive. Upgrading allows your agents to leverage Copilot in SharePoint and all the functionality of the [Microsoft Copilot extensibility ecosystem](/en-us/microsoft-365/copilot/extensibility).

## What is changing?

Microsoft is upgrading the agent experience in SharePoint and OneDrive. Upgrading better aligns your agents with the [Microsoft Copilot extensibility ecosystem](/en-us/microsoft-365/copilot/extensibility), ensuring your agents are part of the [Microsoft Copilot app Home experience](https://blogs.microsoft.com/blog/2026/09/25/introducing-the-new-copilot-with-home-code-and-autopilot/) and the [Microsoft plugin registry](https://techcommunity.microsoft.com/blog/microsoft-copilot-blog/introducing-the-plugin-registry---one-place-to-discover-and-govern-plugins-for-m/4559682), the shared catalog for discovering, publishing, and governing organization-approved and custom-built plugins across Microsoft Copilot experiences, Microsoft 365 apps, OneDrive and SharePoint.

Existing agents in the .agent file format will continue to work across SharePoint, Microsoft Teams, and the Copilot app until the end of March 2027. You can start upgrading or moving each experience to a supported path that best fits its purpose now. After March 2027, .agent files will stop responding and you will have to upgrade to continue using them.

The right upgrade path depends on what each agent helps users accomplish today:

| **Agent role** | **Recommended path** |
| --- | --- |
| Primarily answers questions about content on the current SharePoint site | Use Copilot in SharePoint directly |
| Performs a repeatable action, workflow, or task within the SharePoint site | Convert the agent to a skill |
| Provides a customized Q&A, retrieval, or analysis experience | Upgrade the agent with Microsoft Copilot Agent Builder |
| Is a custom engine agent built in Copilot Studio and published to SharePoint | Publish the existing Copilot Studio agent to Microsoft Copilot app |

Starting in mid-November 2026, you'll use [Microsoft Copilot Agent Builder](/en-us/microsoft-365/copilot/extensibility/agent-builder-build-agents) to create agents for [SharePoint](https://support.microsoft.com/sharepoint/copilot-in-sharepoint/create-an-agent-in-sharepoint) and [OneDrive](https://support.microsoft.com/onedrive/copilot/create-and-use-an-agent-in-onedrive). You can still select SharePoint and OneDrive content as knowledge sources and use a provided prompt to start building a conversational agent. However, creating an agent no longer saves a .agent file in SharePoint or OneDrive. You can edit, share, and monitor your agents through the Copilot app and manage them through [Agent 365](/en-us/microsoft-365/admin/manage/agent-registry?view=o365-worldwide).

### Are agents in SharePoint and OneDrive being retired?

No, only the .agent file format is being retired. You can continue to deliver named conversational experiences and focused site tasks grounded in SharePoint content through [Copilot in SharePoint](copilot-in-sharepoint-get-started) and [Microsoft Copilot Agent Builder](/en-us/microsoft-365/copilot/extensibility/agent-builder-build-agents).

How these agents are incorporated back into SharePoint will change with the [Agent Chat web part](https://www.microsoft.com/microsoft-365/roadmap?id=575298) (coming soon) as the primary experience. Agents saved as .agent files will stop working after March 2027.

### Why is Microsoft making this change?

Copilot in SharePoint and the Copilot extensibility ecosystem provide a consistent foundation for creating, discovering, sharing, governing, monitoring, and managing agents and plugins. Upgraded agents can continue to use SharePoint and OneDrive content, with more customization options, broader distribution, and centralized administration through Agent 365. Skills add focused, reusable capabilities directly to Copilot in SharePoint.

### Which agents are affected?

This change applies to agents stored as .agent files in SharePoint or OneDrive. You might currently use these agents in the SharePoint chat pane, through the Agent Link web part, in the agent immersive viewer, in a Microsoft Teams chat or channel, or in the Copilot app.

You don't need to recreate Copilot Studio agents published to SharePoint because of this change. Review their publishing configuration and publish them to Microsoft Copilot app to make them available to the [Agent Chat web part](https://www.microsoft.com/microsoft-365/roadmap?id=575298) for display.

### Do I need to take action immediately?

No. Existing .agent files will continue to work until the end of March 2027. However, you should start planning your upgrade to take full advantage of Copilot in SharePoint, Copilot extensibility updates, and the governance and analytics of [Agent 365](/en-us/microsoft-agent-365).

### What happens after March 2027?

Agents in .agent file format stop responding to prompts:

1. .agent files that you added to a Teams chat or channel stop responding.
2. .agent files that you used in Microsoft Copilot app stop responding.
3. In SharePoint and OneDrive:

    - Accessing a .agent file (directly or through a share link) displays a message that indicates an upgrade is required.
    - The agent no longer opens in the immersive viewer, Copilot app, or SharePoint side chat pane.
    - The agents icon on the SharePoint navigation no longer appears.
    - The only main agent available on a SharePoint site is Copilot, so this setting is no longer needed and will be removed.

## Upgrade paths

You can choose from different Copilot capabilities to upgrade to based on what your existing agent does and where people need to use it.

As you upgrade an existing SharePoint or OneDrive agent, consider the outcome it provides today and choose the upgrade path that best preserves that outcome. Also consider reviewing agents with no recent use or no clear owner for archival or deletion, instead of upgrading them.

### Agents

If your existing .agent file provides a named Q&A, retrieval, or analysis experience that users need to access beyond the current SharePoint site, consider creating an agent with [Microsoft Copilot Agent Builder](/en-us/microsoft-365/copilot/extensibility/agent-builder).

Agents created through Microsoft Copilot Agent Builder can be used across supported Microsoft 365 experiences, including Copilot app, Teams, and SharePoint. Users can [monitor agents](/en-us/microsoft-365/copilot/extensibility/agent-builder-monitor-agents) in this builder, and administrators can govern, analyze, and manage agents through [Microsoft Agent 365](/en-us/microsoft-agent-365/overview).

In SharePoint, site owners can bring agents directly to their audience by adding them to the pages where people need them using the [Agent Chat web part](https://www.microsoft.com/microsoft-365/roadmap?id=575298). Site owners control where these agents appear as part of the overall site experience. Usage by unlicensed users is consolidated under Copilot app pay-as-you-go (PAYG).

#### Upgrade the agent with Microsoft Copilot Agent Builder

The agent is a customized Q&A, retrieval, or analysis experience with an identity, description, starter prompts, and instructions.

Some examples:

- A named subject matter expert that users recognize and revisit to get information
- Used across SharePoint, Microsoft Copilot, and Teams
- Agents grounded in SharePoint and OneDrive content for question‑and‑answer using Retrieval‑Augmented Generation (Q&A/RAG) scenarios

Before you start, confirm you have the following access:

- Edit permissions to the .agent file
- Ability to [share that agent](/en-us/microsoft-365/admin/manage/agent-settings#sharing)
- Permission to edit pages so an [Agent chat web part](https://www.microsoft.com/microsoft-365/roadmap?id=575298) can be added to the page

To upgrade:

Note

The upgrade experience described here will be available starting mid-November 2026.

1. Take note of who has access to the agent and where the agent is used.
2. Edit the .agent file.

    ![Screenshot of SharePoint Builder showing the Upgrade banner and 'Upgrade to Microsoft 365 Agent' buttons.](sharepointonline/media/upgrade-sharepoint-agents/sp-agent-builder-upgrade-banner.png)
3. Select **Upgrade to Microsoft 365 agent**. A confirmation dialog appears.

![Screenshot of SharePoint Builder showing the Upgrade confirmation dialog with the Move file to Recycle bin option selected.](sharepointonline/media/upgrade-sharepoint-agents/upgrade-confirmation-dialog.png)

1. Select **Upgrade to Microsoft 365 agent** to confirm. Teams and Copilot app will automatically use the upgraded agent.

    - If you plan to add the agent to a page [Agent Chat web part](https://www.microsoft.com/microsoft-365/roadmap?id=575298), select **Move file to Recycle bin**.
    - If you want to continue using the .agent file configuration as the main agent for the site until March 2027, through an Agent Link web part open in the SharePoint chat pane, don't select **Move file to Recycle bin**.
2. On a successful upgrade, the agent uses Microsoft Copilot Agent Builder for all future updates. You can no longer edit the original .agent file and it won't be changed by Microsoft Copilot Agent Builder.
3. If the original agent was shared with everyone in the organization, this access continues in the upgraded agent. Otherwise, the agent is private to you and you can share it to the necessary Microsoft 365 groups. Verify that users who need the agent can access both the agent and the selected knowledge sources.

![Screenshot of the upgraded agent confirmation for a private agent, with Share and Start chat options shown.](sharepointonline/media/upgrade-sharepoint-agents/copilot-agent-builder-upgrade-confirmation-private.png)

1. The agent is now available through the plugin store in the Copilot app according to sharing and administrative policies. Not every upgraded agent is automatically published broadly.

You control the agent your audience uses during the transition period:

1. If you don't delete the original .agent file, you can open it in the SharePoint chat pane. If you link to it from the [Agent Link web part](https://support.microsoft.com/sharepoint/pages-in-sharepoint/use-the-agent-link-web-part), set it as the main agent, or open the file directly in the side pane, the original configuration loads and users can interact with it.

    To direct users to the upgraded agent instead:

- If the original agent is on a SharePoint page through a link or the Agent Link web part, update the page to use [Agent Chat web part](https://www.microsoft.com/microsoft-365/roadmap?id=575298), instead.
- Upgraded agents can't be used in the site's chat pane, so you won't be able to set one as the main agent for the site. Instead, add the [Agent Chat web part](https://www.microsoft.com/microsoft-365/roadmap?id=575298) to a page, so it's prominent on the site and set the main agent as **Copilot**.

1. In the Copilot app, the upgraded agent automatically loads when requested.
2. In a Teams chat or channel, the agent is upgraded but needs to be re-added to the chat or channel. Remove the agent that's in the chat or channel now, then add the agent again by [copying the sharing link](https://support.microsoft.com/microsoft-365-copilot/share-an-agent-in-the-microsoft-365-copilot-app) and posting it to the chat or channel.

Here are some important differences between the .agent file and the Microsoft 365 agent:

- You don't manage Microsoft 365 agent permissions through SharePoint site permissions. Set share access through Microsoft Copilot Agent Builder. If you shared the .agent file with everyone in the organization, you can carry that organization-wide access over during the upgrade. Otherwise, the upgraded agent is private and the creator needs to share it with the people, groups, and email addresses that need to access it from the SharePoint site.
- Usage data starts collecting for the upgraded agent.

#### Custom engine agents

If you have a .agent file that resulted from publishing a [custom engine agent created in Copilot Studio](/en-us/microsoft-365/copilot/extensibility/custom-engine-agent-architecture) to the SharePoint channel, you don't need to rebuild it as a Microsoft Copilot Agent Builder agent.

To add these agents to the [Agent Chat web part](https://www.microsoft.com/microsoft-365/roadmap?id=575298), you need to make them available to the Microsoft Copilot app and Teams channel. For more information about publishing, see [Key concepts - Publish and deploy your agent - Microsoft Copilot Studio](/en-us/microsoft-copilot-studio/publication-fundamentals-publish-channels).

You can delete the .agent file after you add it to a SharePoint page by using the [Agent Chat web part](https://www.microsoft.com/microsoft-365/roadmap?id=575298).

### Copilot in SharePoint

[Copilot in SharePoint](copilot-in-sharepoint-get-started) helps people work directly with content on a SharePoint site.

If your .agent file primarily helps people ask questions about or understand content from the current site, you might not need to maintain a separate named agent. You can use Copilot in SharePoint directly.

Copilot in SharePoint answers questions about content on the current SharePoint site. It doesn't include special instructions beyond answering authoritatively.

Some examples:

- Catch me up on the most recent changes
- Tell me more about this [topic] on this site

Users need a Microsoft Copilot license to use Copilot in SharePoint. Verify that Copilot [is available](copilot-in-sharepoint-get-started#manage-availability-of-copilot-in-sharepoint) on the site.

To ensure that users discover Copilot in SharePoint, set Copilot as the [Main agent](copilot-in-sharepoint-get-started#site-ai-settings) for the site through the site’s AI Settings. When you complete this step, you can delete the .agent file.

### Skills for Copilot in SharePoint

Note

The `convert-agent-file-to-skill` skill will be available mid-November 2026.

[Skills](copilot-in-sharepoint-skills) customize what Copilot in SharePoint can do for specific business outcomes.

A .agent file might be a good candidate for a skill if it performs a repeatable action, workflow, or task within the context of a SharePoint site instead of primarily providing a Q&A experience. The skill should run only in this site context and should be discoverable and executable through interactions with Copilot in SharePoint.

A simple way to distinguish between the two is:

- **Use a skill** when Copilot should perform a focused, repeatable task or multistep workflow within the SharePoint site.
- **Use an agent** when users need a customized Copilot experience for Q&A, retrieval, analysis, or other scenarios.

Some examples:

- Drafting a document from SharePoint content on this site.
- Reviewing a document to recommend updates.
- Organizing files for a business outcome.
- Applying focused instructions or guardrails to a narrow task.

#### Convert the agent to a skill

Before you start, confirm you have the following:

- Confirm the intended users have a Microsoft Copilot license. Only Microsoft Copilot licensed users can access Copilot in SharePoint and its services.
- Confirm Copilot in SharePoint [is available](copilot-in-sharepoint-get-started#manage-availability-of-copilot-in-sharepoint) on the site.
- Confirm the actions of this agent don't need to be accessible in the Copilot app or Teams.

To convert the agent to a skill:

1. Prompt to use the skill, `convert-agent-file-to-skill`, with the .agent or .copilot agent file. You will have the option to create a site or personal skill.
2. To help users discover a site skill, add a [Button web part](https://support.microsoft.com/sharepoint/sites-pages/use-the-button-web-part) to the page to open Copilot in SharePoint to run a prompt with the skill. This step is optional.
3. You can delete the .agent file after the conversion.

## Upgrade guidance

### Who can upgrade an agent?

The agent owner, creator, or site owner is best suited to decide the upgrade path for the agent. They can make the decision based on how users discover and engage with the agent.

To upgrade the agent, you need:

- Edit permissions to the .agent file
- Ability to [share that agent](/en-us/microsoft-365/admin/manage/agent-settings#sharing)
- Permission to edit pages so the [Agent chat web part](https://www.microsoft.com/microsoft-365/roadmap?id=575298) can be added to the page

To convert to a skill, you need [Copilot in SharePoint](copilot-in-sharepoint-get-started) available on the site.

### How do I find agents that need to be upgraded?

Individuals with OneDrive agents can prioritize those that they use most frequently. On SharePoint sites, prioritize agents with high usage, broad audiences, business-critical scenarios, custom instructions, pay-as-you-go dependencies, Teams distribution, or prominent SharePoint placement.

In OneDrive, you can find your agents through the filters on [Home, Shared, or Favorites folders](https://support.microsoft.com/onedrive/copilot/find-your-agent-files-in-onedrive) and the save location **My Files** &gt; **Documents** &gt; **Agents**.

In SharePoint, you have a few options for finding your agents:

- As the agent owner, visit the **Owned by you Agents** section of [Build](https://support.microsoft.com/sharepoint/get-started-with-sharepoint/getting-started-with-build-in-sharepoint) in SharePoint to see agents you own and are candidates for upgrade.

    ![Screenshot of the agents you own shown in Build in SharePoint.](sharepointonline/media/upgrade-sharepoint-agents/sp-build-see-agents.png)
- Use the [agent reports on SharePoint Advanced Management](monitor-agent-usage#use-agent-reports-on-sharepoint-advanced-management) to inventory agents.
- Use the [agent registry](/en-us/microsoft-365/admin/manage/agent-registry?view=o365-worldwide) to see "SharePoint" agents.
- Use [search](monitor-agent-usage#use-search-to-find-all-agents-for-bulk-actions) to find your agents on the site.

### What should I do if I use an agent that someone else created?

Contact the agent owner or the SharePoint site owner and ask whether a replacement is planned. Permission to use an agent doesn't necessarily provide the edit and creation permissions needed to upgrade it. Confirm that you can access and use the replacement before the .agent experience stops working.

## Permissions, sharing, and data

### Do existing permissions and sharing automatically transfer?

No. Sharing a Microsoft Copilot Agent Builder agent is separate from sharing files on a SharePoint site.

A .agent file uses SharePoint file permissions and might inherit access from its site or library. After the upgrade, the Microsoft Copilot Agent Builder agent uses agent-level sharing to share with people, groups, and email addresses, but not to SharePoint groups. If you shared the .agent file with everyone in the organization, that organization-wide access can carry over during the upgrade. Otherwise, the upgraded agent is private until the owner shares it.

Creators and owners should review and share the upgraded or new agent with the people and groups that will see the agent on the SharePoint site.

Access to an agent doesn't grant access to its underlying SharePoint or OneDrive content. Users must have permission to both the agent and the knowledge sources it uses.

### What happens to existing usage history and analytics?

Existing .agent usage history doesn't transfer to the replacement. Analytics for the upgraded skill or agent begin as a new experience. Capture any legacy reporting needed for records or adoption analysis before completing the transition.

### What happens to existing links and placements?

In SharePoint, update the page to use [Agent Chat web part](https://www.microsoft.com/microsoft-365/roadmap?id=575298). Note that the upgraded agent can't be used in the site's chat pane, so you won't be able to set it as the Main agent for the site. Set the Main agent to be **Copilot** after adding the upgraded agent to a page.

In Copilot app, the upgraded agent automatically loads when requested. OneDrive users should use Copilot app to use their agents.

In a Teams chat or channel, the agent is upgraded but needs to be re-added to the chat or channel. Remove the agent that's in the chat or channel now, then add the upgraded agent by [grabbing a link to it](https://support.microsoft.com/microsoft-365-copilot/share-an-agent-in-the-microsoft-365-copilot-app) and adding it to a message to the chat or channel.

### How do I know an agent is upgraded?

Deleting the .agent file after you choose an upgrade path is the easiest way to track which agents remain to upgrade.

If the agent was converted to a skill for the SharePoint site, there's no indication on the .agent file that a conversion happened, but the file moves to the skill location as a backup.

If the .agent file was upgraded to a Microsoft Copilot Agent Builder declarative agent, the SharePoint agent builder shows a banner indicating that the agent is upgraded and no longer editable.

![Screenshot of a banner showing this agent has been upgraded to a declarative agent and can be used in Copilot Chat.](sharepointonline/media/upgrade-sharepoint-agents/edit-upgraded-sp-agent.png)

## Timing and preparation

### Is my existing agent already gone?

No. You can use existing .agent files during the transition. The announcement provides time to inventory, evaluate, upgrade, and test experiences before .agent files stop responding to prompts after March 2027.

### When will the experience change?

Expect the following changes starting mid-November 2026:

1. When you create an agent from SharePoint or OneDrive, you use Microsoft Copilot Agent Builder, and no longer create .agent files.
2. The **Upgrade to Microsoft 365 Agent** button appears in the builder.
3. The **convert-agent-file-to-skill** skill becomes available in Copilot in SharePoint.

### When will existing .agent files stop working?

Existing .agent files will stop responding to prompts after March 2027. After that time, they will no longer respond in the SharePoint chat side pane, Teams, or the Copilot app. The Agent Link web part and the current immersive viewer will also no longer provide access to these agents.

### Do I need to take action now?

You don't need to take any action now, but you should begin preparing. Start with the agents that are business-critical, actively used, broadly shared, embedded on SharePoint pages, added to Teams, or dependent on pay-as-you-go consumption.

1. Inventory .agent files in SharePoint and OneDrive.
2. Identify each agent's owner, audience, purpose, knowledge sources, and current access points.
3. Choose the best-fit upgrade path.
4. Upgrade or re-create the experience, then configure sharing and placement.
5. Test with representative users and familiar prompts before switching.
6. Archive or delete the original .agent file after validating the replacement.

### Will Microsoft automatically upgrade my agents?

No. There's no automatic upgrade. An agent owner or site owner should review .agent files and choose the appropriate upgrade paths. This approach ensures that a named chat experience isn't converted into a skill, or a focused site task into a broader agent without considering the original business outcome. In some cases, the best thing to do is delete the .agent file because it's no longer used. Deleted files appear in the recycle bin.

### Are these changes available in Microsoft Government Cloud?

All these upcoming changes apply to Microsoft Government Cloud.

Copilot extensibility is available in Microsoft Government Cloud, so upgrading to Microsoft Copilot Agent Builder declarative agents preserves your agents' capabilities.

Converting to a skill in Copilot in SharePoint will be available when Copilot in SharePoint is available in Microsoft Government Cloud (coming soon).

## Administrator guidance

### How should administrators prepare?

Learn about [Microsoft Agent 365](/en-us/microsoft-agent-365).

1. Ensure your agent creators can [share that agent](/en-us/microsoft-365/admin/manage/agent-settings#sharing).
2. Identify active and business-critical .agent files.
3. Engage site owners and agent creators to assign ownership and choose an upgrade path.
4. Confirm licensing and consumption configuration for each destination.
5. Update internal guidance, support processes, training, and communications before the creation experience changes.
6. Allow time to test sharing, content access, Teams placement, SharePoint placement, and representative prompts.

### Where will users find upgraded agents?

Users can discover declarative agents and Copilot Studio agents through supported Microsoft 365 experiences, including the plugin store, Microsoft Copilot app, and Teams.

SharePoint site owners can place relevant agents directly on pages through the [Agent Chat web part](https://www.microsoft.com/microsoft-365/roadmap?id=575298) (coming soon).

Users discover and use skills through [Copilot in SharePoint](copilot-in-sharepoint-get-started) and can highlight them with [Quick Steps](https://support.microsoft.com/sharepoint/data-and-lists/create-a-quick-step-for-your-list-or-library), [Button web part](https://support.microsoft.com/sharepoint/sites-pages/use-the-button-web-part), or other site entry points.

### What is happening with SharePoint Agents pay-as-you-go?

SharePoint Agents pay-as-you-go only applies to .agent files. The upgraded agents follow the [capabilities and licensing model](/en-us/microsoft-365/copilot/extensibility/prerequisites#agent-capabilities-and-licensing-models) for agents in Microsoft Copilot app.

SharePoint Agents pay-as-you-go doesn't apply to Copilot in SharePoint.