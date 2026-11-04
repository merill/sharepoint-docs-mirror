---
layout: Conceptual
title: Monitor agent usage in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/monitor-agent-usage
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
description: Learn how to monitor agent usage in SharePoint as a site member, or as SharePoint admin. Monitor individual agent files with file statistics, Search function, and site usage. Monitor agent usage at the organization level with SharePoint Online Management Shell, SharePoint Advanced Management, Purview agent audit log, and Microsoft Cost Management.
locale: en-us
document_id: 86301439-9286-5502-d5b9-f422a604c360
document_version_independent_id: c25fb97d-6c72-7b86-dfc2-f3eca2e1a6cf
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/monitor-agent-usage.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: monitor-agent-usage
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/monitor-agent-usage.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
platformId: 8d5cc247-93e9-d261-2142-0f742f3593ab
---

# Monitor agent usage in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn

Important

Microsoft is upgrading the agent experience (.agent files) in SharePoint to better align with the Microsoft Copilot extensibility ecosystem. By using the new agent experience, agents in SharePoint can be part of the Copilot app home experience and the [Microsoft plugin registry](https://techcommunity.microsoft.com/blog/microsoft-copilot-blog/introducing-the-plugin-registry---one-place-to-discover-and-govern-plugins-for-m/4559682).

To learn more, see [Upgrade agents in SharePoint and OneDrive](upgrade-sharepoint-agents).

You can monitor agent usage in SharePoint through various tools and methods. Each tool and method suits the needs of specific user roles within the organization. This article outlines the options available for users with at least site visitor permissions and SharePoint admins. These two role groups have different ways to monitor and analyze the performance and usage of agents in their respective areas.

Note

To ensure that security and privacy settings are always honored, some of these tools are restricted to specific user roles.

The following tools and techniques are available for monitoring agent usage in SharePoint, categorized based on user roles and permissions:

- For **users with at least site visitor permissions** (site admins, site owners, site members, and site visitors):

    - **File statistics**: Select an individual `.agent` file and use the Details pane to view its file statistics.
    - **Search**: Use **Search** to find all agents on a site for bulk actions.
    - **Site usage**: Use **Site usage** to see the most popular files and agents on their sites.
- For **SharePoint admins**:

    - **SharePoint Online Management Shell**: SharePoint admins can use SharePoint Online Management Shell to get an inventory of the agents created across sites at the organization level in a specified time period.
    - **Microsoft Purview audit log**: SharePoint admins with Compliance admin permissions can use the [Microsoft Purview audit log](/en-us/microsoft-365/compliance/audit-log-search) to monitor agent creation and usage details across the organization.
    - **Microsoft Cost Management**: SharePoint admins can use [Microsoft Cost Management](/en-us/azure/cost-management-billing/cost-management-billing-overview) to monitor the cost of agent usage at the organization level.
    - **SharePoint Advanced Management**: Coming soon, SharePoint admins can use [SharePoint Advanced Management](/en-us/sharepoint/advanced-management) to obtain detailed insights on agent usage across sites. The report lists the number of agents that are created, along with details on policies such as Restricted Content Discovery and Restricted Access Control associated with a particular site.

These tools align with user roles and permissions, enabling monitoring and management of agent activities in SharePoint. The following section provides additional details on how each tool functions and how you can use them effectively.

## Monitor agent usage with at least site visitor permissions

### Check individual agent file usage with File Statistics

Every agent you create in SharePoint is a `.agent` file saved in the location where you create it. Users with view permission to the file can check the `.agent` file's usage by using File Statistics. File Statistics is one of the [file insights](https://support.microsoft.com/office/see-file-insights-before-you-open-a-file-87a23bbc-a516-42e2-a7b6-0ecb8259e026) available from the file card or details/info pane. To check the `.agent` file's file statistics, select the `.agent` file, and then select **Details** to see the number of views and unique viewers.

![Agent Detail Pane](sharepointonline/media/agents-sharepoint/agent-detail-pane.png)

In the Details pane, select the view count to review comprehensive information about the usage of the `.agent` file.

![Agent file insights](sharepointonline/media/agents-sharepoint/agent-file-insights.png)

You can check the agent file's usage by weekly **Viewers** or **Views**:

![Agent file statistics](sharepointonline/media/agents-sharepoint/file-statistics.png)

### Use Search to find all agents for bulk actions

SharePoint users can locate all agents in a specific container, like a document library, site, or even across the entire organization, by searching for files with the `.agent` extension. By searching for `*.agent`, you find all agent files within the selected scope. The results only include agent files that you have permission to access. For site owners and members, this method is a convenient way to find agents and take bulk actions as needed.

![Agent Search](sharepointonline/media/agents-sharepoint/agent-search.png)

### See the list of the most popular agents with Site usage

Site admins, owners, members, and visitors can view site usage data, which includes a list of popular files on the sites. Popular content in the last seven days includes `.agent` files along with other content. You can sort the list of popular files and agents by visits or unique visitors. To view usage data for your site, select the settings gear and then select **Site usage**. Based on your site navigation settings, you might also access the **Site contents** option from the left-hand menu. Then select the **Site usage** option in the top navigation bar. ![Site Usage](sharepointonline/media/agents-sharepoint/site-usage.png)

## Monitor agent usage as SharePoint admins

### Use agent reports on SharePoint Advanced Management

The [Agent Insights report](/en-us/sharepoint/insights-on-sharepoint-agents) gives SharePoint admins detailed visibility into newly created agents across all SharePoint and OneDrive sites within their organization. This report helps you identify which sites have the highest number of agents, so you can better oversee and manage the content these agents use as grounding data, ensuring content integrity and governance. You can generate these reports from the SharePoint Admin Center or use PowerShell cmdlets.

![SharePoint Agent Insight Report](sharepointonline/media/agent-insights/agent-report.png)

![SharePoint Agent Insight Cmdlet](sharepointonline/media/agents-sharepoint/sample-powershell-agent-output.png)

Unless you grant explicit roles, regular site owners can't run these reports. The output report might include agent files that the site owners and site admins don't have access to. From the list, admins can go to the site, search for the agent file, and take actions as needed. They might need to grant access to themselves.

### Use Microsoft Purview audit log to monitor agent creation and usage details

Users with at least Compliance admin permissions with access to Purview can track agent creation and usage details. In addition to all file operation audits, the logs include which users interacted with the agent, and where and when the interaction took place. Audit records also include references to files, sites, or other resources Copilot and AI applications accessed to generate responses to users' instruction.

![Audit Log](sharepointonline/media/agents-sharepoint/audit-log.png)

Microsoft is prioritizing delivering even richer analytics across Copilot Analytics dashboard, Microsoft 365 Admin Center, SharePoint Advanced Management, and SharePoint Online in the coming months.

### Use Microsoft Cost Management to monitor the cost of agent usage

SharePoint admins can use [Microsoft Cost Management](/en-us/sharepoint/sharepoint-agents-azure-billing#monitor-consumption-in-azure-cost-management) to monitor the cost of agent usage at the organization level. To monitor your organization's consumption of agents by using the pay-as-you-go model, create a budget in Microsoft Cost Management by using [Bicep](/en-us/azure/cost-management-billing/costs/quick-create-budget-bicep) and [ARM template](/en-us/azure/cost-management-billing/costs/quick-create-budget-template). A budget helps you inform others about their spending to proactively manage costs and monitor how spending progresses over time. You can also set up various types of cost alerts to monitor the consumption. Furthermore, you can view your organization's consumption by:

1. Going to [Microsoft Cost Management](https://portal.azure.com/#view/Microsoft_Azure_CostManagement/Menu/%7E/overview/openedBy/AzurePortal).
2. If needed, changing the scope to select the subscription that is being used for agents in SharePoint.