---
layout: Conceptual
title: Get started with Copilot in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/copilot-in-sharepoint-get-started
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-09-25T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.reviewer: jseto
ms.author: jseto
author: chuckedmonson
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ROBOTS: 
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: ai-copilot
ms.collection:
- M365-collaboration
- m365copilot
ms.localizationpriority: medium
search.appverid:
- MET150
description: Learn how to set up Copilot in SharePoint.
locale: en-us
document_id: 7a0950e2-9c76-e8d3-7bba-b9c558b3b2bd
document_version_independent_id: d982698b-df99-927f-304f-177b637ed59f
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/copilot-in-sharepoint-get-started.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: copilot-in-sharepoint-get-started
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/copilot-in-sharepoint-get-started.md
platformId: b7d88f6c-a179-3832-fde0-f9d5117c14f9
---

# Get started with Copilot in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn

Copilot in SharePoint brings agentic capabilities into SharePoint so teams can ask questions, run workflows, and create sites, pages, interactive reports, and Office files from their SharePoint content using natural language. Videos, prompt guides and other getting started materials are available [here](https://adoption.microsoft.com/copilot-in-sharepoint/).

Copilot in SharePoint is currently in public preview. General availability begins rolling out on September 30, 2026. Capabilities may appear in your tenant after that date as rollout progresses.

Important

Two things change at general availability:

- **Availability controls.** The PowerShell cmdlets used to opt tenants and sites in or out during preview are being retired. Existing settings are honored until November 1, 2026. Learn how to manage availability [here](/en-us/SharePoint/copilot-in-sharepoint-get-started#manage-availability-of-copilot-in-sharepoint).
- **Advanced work with Copilot Credits** New agentic capabilities and the ability to work at greater scale than was possible in preview are being added to Copilot in SharePoint. These are called advanced work and use Copilot Credits through usage-based billing.

The everyday Copilot in SharePoint capabilities that have been in public preview stay included with the Microsoft 365 Copilot license.

## Prerequisites

To use Copilot in SharePoint:

- **Microsoft 365 Copilot license.** Users must have an active Microsoft 365 Copilot license. Everyday Copilot in SharePoint capabilities are included with this license at no extra cost, and no opt-in step is required.

To use advanced work in Copilot in SharePoint:

- **Enable usage-based billing.** To use advanced capabilities or to work at greater scale, users need usage-based billing enabled through a spending policy in the Microsoft 365 admin center and available Copilot Credits.
- **Set up site-level enablement for site-wide real-time Autofill.** For site-wide, real-time metadata autofill, usage-based billing must also be enabled for the SharePoint site.

## Licensing and Copilot Credits

Copilot in SharePoint uses a hybrid business model. Everyday individual productivity is included with the Microsoft 365 Copilot license. Advanced work requires usage-based billing and consumes Copilot Credits.

For most users, the experience is unchanged from preview. Users with Copilot credits are asked to confirm before moving into advanced work that spends Copilot credits.

| - | Included with the Microsoft 365 Copilot license | Requires Copilot Credits |
| --- | --- | --- |
| **Value** | Understand, create, and organize content | Automate and operate content at scale |
| **When to use it** | Understand and create content across files, pages, lists, and libraries. Copilot in SharePoint works with your content—answering questions, drafting what's next, and organizing as you go. | Automation across large sets of content and content estates. Hand the job to Copilot when it spans more content than you can work through yourself, needs to run on its own, or has to keep pace as content arrives. |
| **Capabilities** | • Ask questions, find content, and catch up• Create HTML, Word, Excel, or PowerPoint files• Create and edit pages, libraries, or lists• Create simple rules, approvals, and deterministic workflows• Rename and share individual files• Create and manage skills• Use Autofill metadata | • Work across large or unbounded content sets, including large-scale synthesis and document review• Create entire sites and solutions• Create and edit files, pages, libraries, and lists at scale• Build multistep, complex AI workflows, such as skills in scheduled AI automations• Use real-time Autofill metadata• Generate new images in document libraries and pages, and edit existing ones• Get analytics on how sites, pages, news, and documents are performing |

Copilot Credit consumption varies based on the type and complexity of the task and nature and volume of the content involved. For examples of credit scenarios, see the [Copilot Credits Guide](https://aka.ms/CopilotCredits/LicensingGuide).

## Set up usage-based billing

Copilot in SharePoint uses the same Copilot Credits cost-management experience as other advanced AI workloads. It doesn't introduce a separate administration model. Details on usage-based billing and cost management are [here](/en-us/microsoft-365/copilot/usage-based-billing-overview-copilot-credits).

For most organizations, an admin action is required before anyone can use advanced capabilities.

1. In the Microsoft 365 admin center, go to **Copilot** &gt; **Cost management**.
2. Select **Add spending policy** and give the policy a name.
3. Under **Access scope**, choose whether the policy applies to all users or to specific security groups.
4. Under **Agents and services**, select **Advanced work in SharePoint**.
5. Set **Limits and alerts** for the policy, choose a **Billing method**, then review and add the policy.

Notes:

- Admins who are new to Copilot Credits need to create a [cost management policy](https://go.microsoft.com/fwlink/p/?linkid=2201187).
- Existing cost management policies might automatically include newly available services if the **Allow new agents and services as they become available** option is turned on for the policy. Review your existing policies to check this setting.

### Decide who needs Copilot Credits

You don't need to enable usage-based capabilities for every SharePoint user. Prioritize people who manage sites and content at scale:

- **Content managers**—prioritize for credits. Examples include knowledge managers, records managers, paralegals, compliance analysts, and library services coordinators who curate, classify, and process content across large collections or on an ongoing basis.
- **Site managers**—prioritize for credits. Examples include SharePoint administrators, digital workplace managers, intranet managers, and collaboration platform leads who create or update sites at scale and enable site-wide processing.
- **Content creators**—assign based on need. Everyday content creation is included, but high-volume or repeatable creation might require advanced capabilities.
- **All other SharePoint users**—likely do not need credits. Everyday individual productivity scenarios remain included with the Microsoft 365 Copilot license.

## What users see

- **For most users, the experience is unchanged from preview.** Copilot Credits aren't required for everyday productivity tasks.
- **Users with credits are asked to confirm.** When a prompt requires an advanced capability, or crosses the threshold of working at scale, Copilot asks the user to approve credit use before continuing. The UI then indicates that credits are being spent for that session.
- **Users can check credit usage.** Prompting `/cost` shows how many credits a task used and how much of the monthly limit remains, including when the limit resets.
- **Users are warned before running out.** When 20% of the monthly credit limit remains, Copilot notifies the user that usage-based features pause until the next month when the limit is reached. Users can request more credits from that prompt.
- **Users without credits see a graceful stop.** If a prompt requires an advanced capability and the user doesn't have Copilot Credits, Copilot explains what it can't complete. If a task crosses the working-at-scale threshold, Copilot completes what it can, then asks the user to start a new chat session.

## Language support

Copilot in SharePoint supports only languages that appear in **both** the SharePoint Online supported language list and the Microsoft Copilot supported language list.

- [Languages supported by SharePoint](https://support.microsoft.com/office/languages-supported-by-sharepoint-dfbf3652-2902-4809-be21-9080b6512fff)
- [Languages supported by Microsoft Copilot](https://support.microsoft.com/office/supported-languages-for-microsoft-365-copilot-94518d61-644b-4118-9492-617eea4801d8)

Note

For best results, use a supported language for your prompts. Copilot in SharePoint isn't tested or validated for languages outside the supported list, and results might vary.

## Models

Copilot in SharePoint currently runs on a Microsoft-managed reasoning model from OpenAI. Microsoft selects and manages the model, and the specific model might change over time as the service adopts newer models. You don't need to configure a model to use Copilot in SharePoint.

## Usage limits

The weekly limits that applied during public preview are removed at general availability.

In rare cases, daily service protection limits may still apply for Copilot licensed users to help ensure fair access for everyone. If a user reaches a service protection limit, Copilot features in SharePoint are temporarily unavailable until the limit resets.

## Manage Availability of Copilot in SharePoint

### Site AI settings

The **Site AI settings** panel lets site owners manage how users interact with AI on their site, including Copilot in SharePoint. Owners can:

- Choose which agent opens from the agent icon on the global header—either Copilot in SharePoint or a custom agent.
- Hide the Copilot button on site pages for site visitors only.
- Enable advanced document processing for the site.

To open the panel, go to **Settings** &gt; **Site AI**.

### Restricted Content Discovery

Restricted Content Discovery is an existing setting that's respected. If it's enabled on a site, Copilot in SharePoint and AI actions don't appear on that site. This rule applies regardless of your other availability settings.

### Retirement of the preview PowerShell controls

PowerShell controls were previously used to manage availability of Copilot in SharePoint. With the transition from public preview to general availability, Copilot in SharePoint is retiring the PowerShell commands used to opt tenants and sites in or out during preview—`KnowledgeAgentScope`, `KnowledgeAgentSelectedSitesList`, and `KnowledgeAgentSelectedSitesListOperation`.

- Existing PowerShell settings continue to be honored until **November 1, 2026**.
- After November 1, 2026, manage availability using Site AI settings and Restricted Content Discovery.

### Powershell controls details

Use the existing `KnowledgeAgent` parameters in `Set-SPOTenant` to manage availability across all sites, selectively include sites, or selectively exclude sites.

For multigeo tenants, run the PowerShell script in each geo. Note that the underlying PowerShell parameter names, such as `KnowledgeAgentScope`, retain the preview naming for compatibility. Although the feature is now described as Copilot in SharePoint, the parameter names remain unchanged.

Use the [SharePoint Online Management Shell version 16.0.26615.12013 or later](https://www.microsoft.com/download/details.aspx?id=35588) to manage access to Copilot in SharePoint for users with Copilot licenses. For setup instructions, see [Get started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

If you already have the SharePoint Online Management Shell installed, make sure you're running the latest version by running the following command in administrative mode: `Update-Module -Name Microsoft.Online.SharePoint.PowerShell`.

### To resolve versioning errors

If you get the following error, it might indicate that you have multiple or conflicting versions of the SharePoint Online Management Shell installed:

`Set-SPOTenant : A parameter cannot be found that matches parameter name 'KnowledgeAgentScope'`

To resolve the issue, follow these steps:

1. Remove the conflicting SharePoint modules. Open **Add or remove programs**, and search for *SharePoint*. Uninstall any SharePoint admin modules you find.
2. Check the installed modules by running the following command:

    `Get-Module -Name *SharePoint* -ListAvailable`

    If multiple versions are listed, remove them by running:

    `Uninstall-Module -Name <ModuleName>`
3. Manually delete the remaining modules. If you encounter exceptions during uninstall, use this command to locate the module path:

    `(Get-Module -Name *SharePoint* -ListAvailable).Path`

    Go to the parent folder and manually delete it.
4. Restart PowerShell. Close the terminal and reopen it to clear any modules loaded in memory.
5. Repeat cleanup. Repeat steps 2 and 3 until no SharePoint Online PowerShell modules remain.
6. To install the latest SharePoint Online PowerShell module, run:

    `Install-Module -Name Microsoft.Online.SharePoint.PowerShell`

    Note

    To verify the installed version, use the following command:

    `(Get-Module -Name Microsoft.Online.SharePoint.PowerShell -ListAvailable).Version`

    If multiple versions appear, repeat the previous cleanup steps.

### Manage availability for specific sites

#### KnowledgeAgentScope

- **Description**: Administrators use KnowledgeAgentScope to control which SharePoint sites have access to Copilot in SharePoint.
- **Valid values**:

    - `AllSites`: Copilot in SharePoint is available on all sites.
    - `IncludeSelectedSites`: Copilot in SharePoint is available only on sites specified in KnowledgeAgentSelectedSitesList.
    - `ExcludeSelectedSites`: Copilot in SharePoint is available on all sites except those specified in KnowledgeAgentSelectedSitesList.
    - `NoSites`: Copilot in SharePoint isn't available on any sites. (This is the default value.)
- **Note**: Requires Microsoft Copilot license.

#### KnowledgeAgentSelectedSitesList

- **Description**: Administrators use KnowledgeAgentSelectedSitesList to pass a list of SharePoint site URLs to include or exclude from Copilot in SharePoint.
- When `KnowledgeAgentScope` = **ExcludeSelectedSites**: the list is treated as sites to **EXCLUDE** (site opt-out list).

    - When `KnowledgeAgentScope` = **IncludeSelectedSites**: the list is treated as sites to **INCLUDE** (site opt-in list).
- By default, this list overwrites any existing list.
- You can only call this parameter when `KnowledgeAgentScope` is set to `IncludeSelectedSites` or `ExcludeSelectedSites`.
- The list of site URLs can't exceed 100 items.
- **Note**: Requires Microsoft Copilot license.

#### KnowledgeAgentSelectedSitesListOperation

- **Description**: KnowledgeAgentSelectedSitesListOperation specifies the operation to perform on the current sites list.
- **Valid values**:

    - `Overwrite`: Overwrite the existing sites list (default).
    - `Append`: Append the input list of sites to the existing sites list.
    - `Remove`: Remove the input list of sites from the existing sites list.
- **Note**: Calling this parameter without `KnowledgeAgentSelectedSitesList` has no effect.

### Examples

#### Make Copilot in SharePoint available on all sites

```PowerShell
# Connect to SharePoint Online admin center
Connect-SPOService https://yourtenant-admin.sharepoint.com

# Make Copilot in SharePoint available for all sites in the tenant
Set-SPOTenant -KnowledgeAgentScope AllSites

# Verify the configuration
Get-SPOTenant | Select-Object KnowledgeAgentScope
```

#### Make Copilot in SharePoint available on specified sites only

```PowerShell
# Connect to SharePoint Online admin center
Connect-SPOService https://yourtenant-admin.sharepoint.com

# Make available only on the included sites
Set-SPOTenant -KnowledgeAgentScope IncludeSelectedSites

# Specify sites to include (initial inclusion list)
Set-SPOTenant -KnowledgeAgentSelectedSitesList @("https://yourtenant.sharepoint.com/sites/site5", "https://yourtenant.sharepoint.com/sites/site7")

# Add additional sites to the existing inclusion list (if needed)
Set-SPOTenant -KnowledgeAgentSelectedSitesList @("https://yourtenant.sharepoint.com/sites/site3") -KnowledgeAgentSelectedSitesListOperation Append

# Verify the inclusion configuration
Get-SPOTenant | Select-Object KnowledgeAgentScope, KnowledgeAgentSelectedSitesList
```

#### Opt out specific sites (available on all sites except those listed)

```PowerShell
# Connect to SharePoint Online admin center
Connect-SPOService https://yourtenant-admin.sharepoint.com

# Make available on all sites except selected sites
Set-SPOTenant -KnowledgeAgentScope ExcludeSelectedSites

# Specify sites to exclude (initial exclusion list)
Set-SPOTenant -KnowledgeAgentSelectedSitesList @("https://yourtenant.sharepoint.com/sites/site1", "https://yourtenant.sharepoint.com/sites/site2")

# Add additional sites to the existing exclusion list (if needed)
Set-SPOTenant -KnowledgeAgentSelectedSitesList @("https://yourtenant.sharepoint.com/sites/site3") -KnowledgeAgentSelectedSitesListOperation Append

# Verify the exclusion configuration
Get-SPOTenant | Select-Object KnowledgeAgentScope, KnowledgeAgentSelectedSitesList
```

#### Turn off Copilot in SharePoint for the tenant

```PowerShell
# Connect to SharePoint Online admin center
Connect-SPOService https://yourtenant-admin.sharepoint.com

# Turn off Copilot in SharePoint for all sites
Set-SPOTenant -KnowledgeAgentScope NoSites

# Verify it is turned off
Get-SPOTenant | Select-Object KnowledgeAgentScope
```

Note

Microsoft 365 Government—GCC, GCC High, DoD, Office 365 air-gapped cloud environments, and Microsoft 365 operated by 21Vianet don't currently support Copilot in SharePoint.