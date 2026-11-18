---
layout: Conceptual
title: Restrict content collaboration by agentic users (preview) - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/agentic-users-governance-restrict-share-to-set-users
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
description: Restrict agentic user sharing in SharePoint and OneDrive so agents share content only with their managers. Learn how to turn on this guardrail in Agent 365.
ms.date: 2026-11-10T00:00:00.0000000Z
ms.topic: how-to
author: nibandyo
ms.author: nibandyo
ms.reviewer: stephkent
manager: leeclontz
audience: Admin
f1.keywords: NOCSH
ms.service: sharepoint-online
ms.subservice: sync
ms.collection: bap-ai-copilot
ms.localizationpriority: medium
ms.custom:
- sfi-ga-nochange
locale: en-us
document_id: 8f604bc9-279a-986d-6ca1-4b207013fc28
document_version_independent_id: 90f4d246-5414-a14e-062c-6369d97d86dc
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/agentic-users-governance-restrict-share-to-set-users.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: agentic-users-governance-restrict-share-to-set-users
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/agentic-users-governance-restrict-share-to-set-users.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/302444b9-4a43-4841-8014-3d9e4251ff15
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bebd8809-dac1-4c22-83e2-66d98af8a94d
platformId: 835b42e9-67d8-50a5-41c6-9b560e9df0f8
---

# Restrict content collaboration by agentic users (preview) - SharePoint in Microsoft 365 | Microsoft Learn

Prevent agents from sharing Microsoft 365 content outside your organization.

Agentic users, also known as agents with identities, increasingly work alongside the people in your organization. An agentic user emulates human capabilities and handles complex tasks, operating much like a virtual employee. As part of Microsoft Agent 365, every agentic user gets its own identity in Microsoft 365, including a mailbox, a OneDrive account, and Teams chat.

Like people, agentic users can be granted access to SharePoint sites and Microsoft 365 resources, and they can share that content with others in your organization. To prevent agentic users from oversharing content broadly, admins can enforce a content guardrail. With the content guardrail turned on, SharePoint Administrators can allow agentic users to share SharePoint and OneDrive content and collaborate with a limited set of users.

Note

This feature is in preview. In this release, an agentic user’s allowed list contains only its agent manager, so when the setting is on, the agentic user can share a site and its contents with only its manager. The guardrail is off by default.

You can apply this setting to all agent blueprint app IDs in your tenant or only to the blueprint app ID that you select. Because the setting lives on the blueprint app ID, every agentic user associated with the blueprint honors it, including third-party agent blueprint app IDs.

## When to use this setting

Use the setting when the agentic users of a specific agent blueprint ID should not share content with anyone other than its manager. Common scenarios include:

- Rolling out a new agent blueprint app ID while you evaluate how its agentic users handle organizational content.
- Meeting compliance requirements in regulated industries, such as financial services, where agentic users have access to restricted or proprietary content.
- Deploying an assistant for a team that handles high-value material, such as deal or legal content, so that what the agent gathers stays with the person accountable for it.

For example, a SharePoint Administrator at Contoso activates the Sales Agent blueprint and turns on the setting for it. Every agentic user associated with the Sales Agent blueprint app id, can now share sites and content only with its own agent manager. If a sales agent user tries to share a proposal with anyone else in the organization, the share is blocked.

## How the setting works

This setting works at the tenant level. Turn it on for agent blueprint app ID, either in the Microsoft Agent 365 portal when you onboard a blueprint app ID or in the SharePoint admin center under Agent governance.

| Scope | What happens |
| --- | --- |
| Agentic users of specific blueprints | Only agentic users associated with the blueprint app ID you select are restricted. Agentic users of other blueprints follow your existing sharing settings. Blueprint app ID can be first-party (Microsoft) or third-party agentic applications. |

When an agentic user tries to share a site or its content, the recipients are checked and share with anyone other than the agent’s manager is blocked.

The guardrail is designed to be safe to turn on broadly:

- It isn’t retroactive. Content an agentic user shared before you turned on the setting stays shared, and no existing permissions are removed.
- It fails closed. If the circle of work can’t be evaluated, the share is blocked and the failure is logged.
- It works alongside other existing content governance controls. Information barriers, Restricted Access Control, and sensitivity labels still apply.

Note

The guardrail is applied at the tenant level for each blueprint. Site-level controls aren’t currently available.

## Prerequisites

Before you turn on the guardrail, make sure that you have:

- The SharePoint Administrator role.
- Microsoft Agent 365 or Microsoft 365 E7 license. For licensing questions, see [Microsoft Product Terms](https://go.microsoft.com/fwlink/?linkid=2309718) or contact your Microsoft account representative.
- Identified the agent blueprints you want to restrict. If you plan to scope the guardrail to specific blueprints, have each blueprint’s name or ID (GUID) ready.

## Turn on the guardrail

### In the Microsoft Agent 365 portal

Global Administrators can turn on the guardrail as one of the default protection policies applied when an agent template is onboarded in the tenant. In the Agent 365 portal, go to **Policies**, open **Default protection for autopilots**, and select the setting to be **On**.

When you set the guardrail to **On**, every agent user associated with the agent template can share site and content only with their manager.

[![Screenshot of the Default protection for autopilots Policies tab in Microsoft admin center with Restrict collaboration by agentic users turned On.](sharepointonline/media/agentic-users-governance-restrict-share-to-set-users/restrict-agent-collaboration-pane.png)](sharepointonline/media/agentic-users-governance-restrict-share-to-set-users/restrict-agent-collaboration-pane.png#lightbox)

## Agentic user guardrail FAQ

### Is the policy turned on by default?

No. The guardrail is off by default. Agentic users follow your existing sharing settings until you turn it on.

### Does the policy affect people in my organization?

No. The restriction applies only to agentic users. People in your organization continue to share content according to your tenant and site sharing settings.

### Can I apply the policy to individual sites?

Not currently. Configure the guardrail at the tenant level, either for all agent blueprints or for the specific blueprints you select.

### Which agentic applications can I restrict?

You can restrict agentic users associated with both first-party (Microsoft) and third-party agentic application blueprints.

### Who is in an agentic user’s circle of work?

In this release, an agentic user’s circle of work contains only its agent manager.

### What happens to content an agentic user already shared?

Nothing changes for content shared before you turned on the guardrail. Existing shares and permissions stay in place; the guardrail applies to new sharing actions.

### Does the guardrail replace my other sharing controls?

No. Your tenant and site sharing settings, information barriers, Restricted Access Control, and sensitivity labels continue to apply. When more than one policy applies, the most restrictive one wins.

## Related information

- [Restrict external sharing by agentic users in SharePoint and OneDrive](agentic-users-governance-restrict-share-external-agentic-users)
- [Manage sharing settings for SharePoint and OneDrive in Microsoft 365](turn-external-sharing-on-or-off)
- [Permission insights for agentic users](agent-governance-overview)