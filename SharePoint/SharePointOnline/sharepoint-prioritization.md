---
layout: Conceptual
title: Service prioritization in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/sharepoint-prioritization
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-10-14T00:00:00.0000000Z
ms.reviewer: 
ms.author: sibourda
author: SimonBourdages
manager: fraga
audience: Admin
f1.keywords: NOCSH
ms.topic: article
ms.service: sharepoint-online
ms.subservice: platform
ms.collection: M365-collaboration
ms.custom: admindeeplinkSPO
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.assetid: 
description: What is service prioritization in SharePoint and How to Leverage It
locale: en-us
document_id: 7036357d-c309-900d-20bc-cf17a1351f4b
document_version_independent_id: e6847387-b163-b7d7-8390-025ef603d06c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/sharepoint-prioritization.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: sharepoint-prioritization
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/sharepoint-prioritization.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: e28faf69-da52-dd6c-1535-0dfc0f6054a6
---

# Service prioritization in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn

Service prioritization in SharePoint is a powerful service designed to prioritize apps within your SharePoint Online tenants, particularly those considered business-critical. By using service prioritization, organizations can ensure optimal performance, scalability, and reliability for key applications without requiring code modifications. Next, we explore what service prioritization entails and how to effectively use it within your organization.

## 1. What is Service Prioritization in SharePoint?

Service Prioritization in SharePoint enables businesses to assign a higher priority to their critical applications within a SharePoint environment. This prioritization ensures that these apps are the last to experience throttling in their tenant during periods of high resource usage. It allows the app to scale resource usage limits (https://aka.ms/spo429) significantly—ranging from a minimum of 2x up to 10x when there are available resources. As a result, Service Prioritization enhances application reliability and delivers more consistent performance.

Note

Sharing limits are excluded from this offering at this time.

## 2. Key Benefits of Service Prioritization in SharePoint

- **Scalable Resources**: Application resource limits can exceed [normal thresholds](https://aka.ms/spo429), offering up to 10 times more capacity when available.
- **No Code Changes Required**: Any app can be prioritized without requiring development or code modifications as long as they can be registered on Microsoft Graph metered APIs.
- **Pay-As-You-Go Model**: Organizations only pay for the resources they consume.

## 3. Metered API Classification

Service prioritization in SharePoint integrates with Azure's standard cost management experience, enabling organizations to monitor and control expenses associated with prioritized apps. For detailed reporting, refer to Microsoft’s Cost Management documentation.

To support prioritization, service prioritization in SharePoint operates on a metered API model with defined costs:

- **Standard APIs**: charged at $0.02 per 1,000 requests.
- **Heavy APIs**: charged at $0.14 per 1,000 requests.

"Heavy" APIs are those that consume a larger amount of SharePoint resources, including but not limited to resource enumeration, permissions, and downloads. If a SharePoint API is not "Heavy", it is considered "Standard".

Note

All API calls to SharePoint and OneDrive are included. Price varies based on the API used per pricing above in effect as of 11/11/2025.

## 4. Manage Service Prioritization in SharePoint Using PowerShell

Administrators can onboard and manage service prioritization policies and app registrations using the SharePoint Online PowerShell module. Below are some key cmdlets:

- **[New-SPOServicePrioritizationBillingPolicy]**: Creates a new billing policy for service prioritization. This policy defines the billing structure for prioritized apps.
- **[Add-SPOServicePrioritizationAppRegistration]**: Registers an app for service prioritization. Requires details such as App ID, Policy ID and Quota Multiplier.
- **[Get-SPOServicePrioritizationBillingPolicies]**: Retrieves all existing billing policies for service prioritization in the tenancy.
- **[Get-SPOServicePrioritizationAppRegistrations]**: Retrieves all app registrations for service prioritization in the tenancy.
- **[Set-SPOServicePrioritizationAppRegistration]**: Updates an existing app registration for service prioritization, such as modifying the Quota Multiplier or enabling/disabling the registration.
- **[Remove-SPOServicePrioritizationAppRegistration]**: Deletes an existing app registration for service prioritization.

## 5. Manage Service Prioritization in SharePoint Using the Microsoft 365 Admin Center

Administrators can onboard and manage service SharePoint prioritization policies and app registrations using the Microsoft 365 admin center. Pay-as-you-go is managed in the billing in the Billing node of the Microsoft 365 admin center. Here are the main steps:

### 5.1. Check the pre-requisites

- To manage Service Prioritization in SharePoint, you must have the SharePoint Administrator or the Global Administrator role.
- To create a new subscription in the Microsoft 365 admin center, you must be a Billing Account Owner or a Billing Account Contributor.
- The tenant must have at least one SharePoint license, or a license that includes SharePoint.
- You must have an Azure subscription in the same tenant as Microsoft 365. If you don't have an Azure subscription, you can create one during the billing policy setup process.
- You must have an Azure resource group in that subscription. If you don't have an Azure resource group, you can create one during the billing policy setup process.
- You must have Owner or Contributor rights to the Azure subscription and resource group.

### 5.2. Create a billing policy

- Sign in to the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339)
- Go to Billing &gt; Pay-as-you-go.
- On the Billing policies tab, select Add a billing policy.
- On the Billing details page, enter a name for the billing policy.
- From the Subscription drop-down list, select an existing Azure subscription, or select Create a new subscription.
- From the Resource group drop-down list, select an existing resource group, or select Create a new resource group.
- From the Region drop-down list, select a region. This selection determines where the tenant ID and usage data are stored.
- In the Choose Users screen, keep the default “all users” for the SPSP scenario.
- In the Budget screen, you can optionally create an alert when this policy reaches a limit.
- Review the pay-as-you-go billing terms of service and privacy statement, and then select the I accept the pay-as-you-go billing terms of service checkbox.

Note

You can't edit a subscription or resource group associated with a billing policy.

### 5.3. Connect the SharePoint Services Prioritization to a billing policy

- On the Review and create policy page, select a billing policy
- Select Connect your services to connect the policy
- You are redirected to the Pay-as-you-go page.
- Select the name of the service to connect (Services Prioritization in SharePoint)
- In the side panel, select the Billing policies tab.
- Find the billing policies that you want to connect to
- Select the Connection status toggle to set it to Connected.
- Select Save and then close the side panel.

### 5.4. Register an app for SharePoint Services Prioritization

- Go to the Pay-as-you-go page.
- Select the “Services Prioritization in SharePoint” service.
- Go to the Settings tab.
- Use the option to add an application.
- Enter the Application ID, Quota Multiplier and Billing Policy.
- Select Save and then close the side panel.

### 5.5. View spending for your organization

- In the Microsoft 365 admin center, go to Billing &gt; Pay-as-you-go.
- On the Billing policies tab, select a billing policy.
- In the billing policy side panel, select the Budget tab.
- The Spending option displays data for the current month and includes a chart that displays data for the last six months.
- You can also monitor your pay-as-you-go usage and costs in Microsoft Cost Management for Azure. Ensure you have at least read access to the billing resource group.

## 6. Best Practices and Considerations

- Prioritize apps that are critical to your business operations to maximize the value of service prioritization in SharePoint.
- Take time to understand the limits of the service at https://aka.ms/spo429.
- Regularly review resource usage and adjust quotas or policies as necessary to balance performance with cost efficiency.
- Applications registered for Service Prioritization will be billed for any requests (API calls) above the regular application limits defined at https://aka.ms/spo429.

## 7. Related articles

- [Understanding SharePoint throttling limits](https://aka.ms/spo429)
- [Get started with the SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
- [Microsoft 365 pay-as-you-go services - Overview and benefits](/en-us/microsoft-365/commerce/services/pay-as-you-go-overview)
- [Microsoft 365 pay-as-you-go pricing - SharePoint in Microsoft 365](microsoft-365-pay-as-you-go-pricing)
- [Set up and manage pay-as-you-go billing in the Billing node of the Microsoft 365 admin center](/en-us/microsoft-365/commerce/services/pay-as-you-go-setup-billing-node)
- [Create a budget for pay-as-you-go billing](/en-us/microsoft-365/commerce/services/pay-as-you-go-budget)
- [Microsoft 365 pay-as-you-go terms of service - SharePoint in Microsoft 365](microsoft-365-pay-as-you-go-terms-of-service)
- [Microsoft Cost Management documentation](/en-us/azure/cost-management)