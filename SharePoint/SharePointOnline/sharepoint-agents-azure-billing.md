---
layout: Conceptual
title: Set up SharePoint agents for pay-as-you-go billing - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/sharepoint-agents-azure-billing
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
ROBOTS: NOINDEX, NOFOLLOW
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: ai-copilot
ms.collection:
- M365-collaboration
- m365copilot
- magic-ai-copilot
- Tier2
description: In this article, you learn how to set up SharePoint agents for pay-as-you-go billing.
locale: en-us
document_id: 3c44b12b-1235-8202-861d-99a061d49a6b
document_version_independent_id: 590b9236-30e8-f012-1935-1d9da2195bdf
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/sharepoint-agents-azure-billing.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: sharepoint-agents-azure-billing
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/sharepoint-agents-azure-billing.md
platformId: e7bb8455-630c-7ebd-cc46-4e913f4f88d0
---

# Set up SharePoint agents for pay-as-you-go billing - SharePoint in Microsoft 365 | Microsoft Learn

Important

Microsoft is upgrading the agent experience (.agent files) in SharePoint to better align with the Microsoft Copilot extensibility ecosystem. By using the new agent experience, agents in SharePoint can be part of the Copilot app home experience and the [Microsoft plugin registry](https://techcommunity.microsoft.com/blog/microsoft-copilot-blog/introducing-the-plugin-registry---one-place-to-discover-and-govern-plugins-for-m/4559682).

To learn more, see [Upgrade agents in SharePoint and OneDrive](upgrade-sharepoint-agents).

## Set up SharePoint agents as an Azure resource

To use pay-as-you-go billing, you need to first set up SharePoint agents as a resource in Azure. That resource is used whenever a user without a Microsoft Copilot license uses a SharePoint agent.

### Prerequisites to set up SharePoint agents as a resource in Azure

To set up SharePoint agents as a resource in Azure, you need to have at least the following permissions as:

- A SharePoint administrator
- [Owner or Contributor Azure roles](/en-us/azure/role-based-access-control/built-in-roles#privileged) to an Azure subscription
- [Owner or Contributor Azure roles](/en-us/azure/role-based-access-control/built-in-roles#privileged) to an Azure resource group linked to the same Azure subscription

Note

- You only need the Owner or Contributor Azure roles during the billing setup process.
- To assign an Owner or Contributor Azure role, see [Assign Azure roles using the portal](/en-us/azure/role-based-access-control/role-assignments-portal).

To set up SharePoint agents as an Azure resource, you need to do the following if you haven't already:

1. [Create an Azure subscription](https://azure.microsoft.com/pricing/offers/ms-azr-0003p/).
2. [Create an Azure resource group](/en-us/azure/azure-resource-manager/management/manage-resource-groups-portal#create-resource-groups) for SharePoint agents.

## Set up pay-as-you-go billing for SharePoint agents

After setting up an Azure resource group for SharePoint agents, you can set up pay-as-you-go billing for SharePoint agents in the Microsoft 365 admin center. Here are the steps:

*Step 1: Set up a pay-as-you-go billing policy* To set up a pay-as-you-go billing policy for SharePoint agents, go to the [Microsoft 365 admin center](https://admin.microsoft.com/Adminportal/Home) and follow the steps outlined in [Set up or disconnect pay-as-you-go billing in the Copilot node of the Microsoft 365 admin center](/en-us/microsoft-365/services/pay-as-you-go-setup-copilot).

*Step 2: Connect the billing policy to the SharePoint agent service*

- After creating the billing policy, select **Connect a service** for the policy, on the **Billing & usage** page. The **Pay-as-you-go services** tab opens.
- Choose **SharePoint agents** from the list of apps and services. The **Manage billing policy connections** pane appears.
- Select the billing policy to connect it to the SharePoint agent service.
- Select **Save**, then **Done**. Your billing policy is now connected to the SharePoint agent service.

### Migrate from previous pay-as-you-go policies

If you currently have a pay-as-you-go policy for SharePoint agents set up under **Org settings** and would like to take advantage of the new billing policy updates, you will need to first disconnect your existing policy before linking SharePoint agent to a new policy. By doing so, you benefit from the updated pay-as-you-go billing policies:

- You can assign one policy per security group and monitor cost for each group separately.
- Only users in the security group assigned to the billing policy have access to SharePoint agents.

Note

- Each billing policy can currently have one security group. Support for multiple security groups will be available soon.
- You can create up to 10 policies, with each policy assigned a security group.

To disconnect your existing SharePoint agents pay-as-you-go billing policy:

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/Adminportal/Home), select **Org settings** &gt; **Pay-as-you-go services**.
2. Select SharePoint agents. The **Manage billing for SharePoint agents** page appears with a notification message at the top: "We've updated how pay-as-you-go billing works with SharePoint agents. With the new billing policies, you can divide charges across multiple Azure subscriptions. Learn about using SharePoint agents with pay-as-you-go billing. To manage pay-as-you-go billing for SharePoint agents, go to *Copilot Billing & usage.*"
3. Select **Copilot Billing & usage** to open the **Billing & usage** page.
4. Select **SharePoint agents** under **Pay-as-you-go services**.
5. Select **Disconnect previous billing**.

Your previous billing is now disconnected. You can now set up a new billing policy and connect it to SharePoint agents.

### Billing rates

The following table illustrates the differences in the subscription models for the cost of SharePoint agent usage.

| SharePoint agent feature | Billing rate | Use in Microsoft Copilot scenarios^1^ | Autonomous use |
| --- | --- | --- | --- |
| Generative answer | 2 messages | No charge | 2 messages |
| Tenant graph grounding for messages | 10 messages | No charge | 10 messages |

^1^ Interactive use of generative answers, tenant graph grounding and agent actions by authenticated Microsoft Copilot users, in Microsoft 365 apps and services, are included at no extra cost.

- Generative answers: These events are dynamically generated using AI models, such as Generative Pretrained Transformers (GPTs). They can adapt and change based on the context and the knowledge sources they're connected to. They're useful for handling a wide range of topics and providing more flexible and natural interactions.
- Tenant graph grounding for messages: These events provide higher quality grounding for your agents using retrieval-augmented generation (RAG) over your tenant-wide Microsoft Graph, including external data synced into Microsoft Graph through connectors. This results in more relevant and improved responses and ensures that the grounding information is up-to-date. This capability is optional, and you can turn it on or off for each agent.

Note

- SharePoint agents are grounded in the tenant graph, so each interaction with a SharePoint agent uses 12 messages (10 messages for tenant graph grounding, and 2 messages for generative answers) to respond to a single complex prompt from the user.
- Charges of SharePoint agent usage appear under the Copilot Studio meter in your invoice. However, in Microsoft cost management, you can see a detailed breakdown by feature, including SharePoint agents.

### Monitor consumption in Microsoft Cost Management

You can monitor your organization's consumption of SharePoint agents with the pay-as-you-go with [Microsoft Cost Management](https://portal.azure.com/#view/Microsoft_Azure_CostManagement/Menu/%7E/overview/openedBy/AzurePortal). If needed, change the scope to select the subscription that is being used for agents in SharePoint.

Select **Reporting + analytics**, then select **Cost analysis** to review and analyze your consumption. Choose to use [**Smart views**](/en-us/azure/cost-management-billing/costs/quick-acm-cost-analysis#analyze-costs-with-smart-views) to quickly view your consumption by Services, Resources, and Resources groups. You can also create [custom views](/en-us/azure/cost-management-billing/costs/quick-acm-cost-analysis#analyze-costs-with-customizable-views) to analyze your consumption by different dimensions.

You can quickly create a budget under **Monitoring** &gt; **Budgets** for your selected scope.

![Screenshot of creating a budget in Microsoft Cost Management.](sharepointonline/media/agents-sharepoint/create-budget.png)

Select Alert conditions to set up the budget alert conditions. You can set up alerts for when your actual spending or the forecast reaches a certain percentage of your budget. Select **Manage action group** to set up the action group for the alert. You can choose to send an email, SMS, or push notification to the action group when the alert is triggered.

![Screenshot of creating action group in Microsoft Cost Management.](sharepointonline/media/agents-sharepoint/create-action-group.png)

You can also create a budget in Microsoft Cost Management with [Bicep](/en-us/azure/cost-management-billing/costs/quick-create-budget-bicep) and [ARM template](/en-us/azure/cost-management-billing/costs/quick-create-budget-template).

Budget helps you inform others about their spending to proactively manage costs and monitor how spending progresses over time. When you can also set up various types of cost alerts to monitor the consumption.

You can view your invoices under **Billing** &gt; **Invoices**. Use text search to filter for the invoices you want. You can also filter by **Status** and **Timespan**. You can also download the invoice in CSV format.

![Screenshot of monitoring consumption in Microsoft Cost Management.](sharepointonline/media/agents-sharepoint/cost-management.png)

#### Adjusting consumption

Using pay-as-you-go billing means that each user is responsible for their own consumption. Work with people in your organization to ensure the efficient use of agents in SharePoint. For example, restrict access to SharePoint sites with agents to only those who need to use them.

### Paying your invoice

Your organization receives an invoice for all Azure services used at the end of each month. You can pay these invoices under the Invoices section in the subscription that you use for agents in SharePoint.

## Disconnect agents from pay-as-you-go billing

To disconnect agents from pay-as-you-go billing, follow these steps:

1. In the Microsoft 365 admin center, select **Copilot** &gt; **Billing and usage**.
2. On the **Pay-as-you-go services** page, select the SharePoint agent policy.
3. The **Manage billing policy connections** panel opens up. All policies including the ones that are connected to agents are displayed.
4. Select the checkbox next to the SharePoint agent policy you would like to disconnect.
5. View confirmation that your Azure Subscription has been disconnected.
6. Pay-as-you-go services will discontinue for this Azure Subscription.
7. If multiple services are connected to a single policy, each service can be disconnected by going through the above steps.