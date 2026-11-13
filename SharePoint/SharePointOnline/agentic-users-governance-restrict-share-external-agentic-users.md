---
layout: Conceptual
title: Restrict external sharing by agentic users in SharePoint and OneDrive - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/agentic-users-governance-restrict-share-external-agentic-users
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
description: Restrict external sharing for agentic users in SharePoint and OneDrive. Learn how to configure the tenant-level policy with PowerShell to keep content internal.
ms.date: 2026-11-12T00:00:00.0000000Z
ms.topic: how-to
ms.collection: bap-ai-copilot
author: steph-kent-ms
ms.author: stephkent
ms.reviewer: stephkent
manager: leeclontz
audience: Admin
f1.keywords: NOCSH
ms.service: sharepoint-online
ms.subservice: admin
locale: en-us
document_id: d981ef0c-704c-62ce-1cee-e36be1efdaf8
document_version_independent_id: 8cf48d0c-3e4d-2683-e802-86840b96d964
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/agentic-users-governance-restrict-share-external-agentic-users.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: agentic-users-governance-restrict-share-external-agentic-users
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/agentic-users-governance-restrict-share-external-agentic-users.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
platformId: 6a7e3b4b-1958-6200-ec06-73ae87aca64f
---

# Restrict external sharing by agentic users in SharePoint and OneDrive - SharePoint in Microsoft 365 | Microsoft Learn

Agentic users, also known as agents with identities, increasingly work alongside the people in your organization. Each agentic user acts as an agent that emulates human capabilities and handles complex tasks, operating much like a virtual employee. As part of Microsoft Agent 365, every agentic user gets its own identity in Microsoft 365, including a mailbox, a OneDrive account, and Teams chat.

Because agentic users can store and share content just like other members of your organization, you need a way to keep that content from leaving the organization. The external sharing restriction for agentic users lets SharePoint Administrators prevent agentic users from sharing SharePoint and OneDrive content with external users. You can apply the restriction to every agentic user in your tenant, or only to the agentic users associated with specific agentic application blueprints.

Note

- This policy applies only to sharing performed by agentic users. It doesn't change how people in your organization share content. The policy is turned off by default.

## When to use this policy

Use the external sharing restriction for agentic users when content handled by AI teammates must stay inside your organization. Common scenarios include:

- Rolling out new agentic applications while you evaluate how their agentic users handle organizational content.
- Meeting compliance requirements in regulated industries, where content accessed or produced by agents must not be shared outside the organization.
- Restricting agentic users from a specific first-party or third-party agentic application, while leaving other agentic applications unaffected.

For example, in the Contoso tenant, a SharePoint Administrator enables the Sales Agent agentic application and applies the policy to restrict external sharing for its agentic users. As a result, every agentic user associated with the Sales Agent application blueprint is prevented from sharing SharePoint and OneDrive content with any external user.

## How the policy works

The restriction is a tenant-level setting that you configure by using SharePoint Online PowerShell. It gives you the flexibility to restrict either all agentic users or only the agentic users tied to the agentic application blueprints you select.

| Scope | What happens |
| --- | --- |
| All agentic users | Every agentic user in the tenant, regardless of its associated agentic application, is blocked from sharing SharePoint and OneDrive content with external users. |
| Agentic users of specific blueprints | Only agentic users associated with the agentic application blueprints you add to the control list are blocked. Blueprints can be first-party (Microsoft) or third-party agentic applications. |

The blueprint control list works as a block list. You add the blueprint ID of each agentic application whose agentic users shouldn't share content externally, and you can do so when the agentic application is provisioned.

Note

The policy is applied at the tenant level. Site-level controls aren't currently available.

## Prerequisites

Before you configure the policy, make sure that:

- Microsoft Agent 365 or Microsoft 365 E7 license. For licensing questions, see [Microsoft Product Terms](https://go.microsoft.com/fwlink/?linkid=2309718) or contact your Microsoft account representative.
- You have the [SharePoint Administrator role](sharepoint-admin-role).
- You have the latest version of the SharePoint Online Management Shell installed.
- You have the blueprint ID (GUID) of each agentic application you want to restrict, if you plan to scope the policy to specific blueprints.

## Configure the policy by using PowerShell

Open SharePoint Online PowerShell as an administrator, connect to your tenant, and run the command that matches what you want to do. The following table summarizes the available commands.

| Goal | Command |
| --- | --- |
| Restrict all agentic users | `Set-SPOTenant -RestrictExternalSharingForAgents $true` |
| Remove the restriction for all agentic users | `Set-SPOTenant -RestrictExternalSharingForAgents $false` |
| Restrict agentic users of a specific blueprint | `Set-SPOTenant -RestrictExternalSharing -AddAppIDToList <BlueprintGUID>` |
| Remove the restriction for a specific blueprint | `Set-SPOTenant -RestrictExternalSharing -RemoveAppIdFromList <BlueprintGUID>` |

### Restrict external sharing for all agentic users

To prevent every agentic user in your tenant from sharing content with external users, run:

`Set-SPOTenant -RestrictExternalSharingForAgents $true`

### Remove the restriction for all agentic users

To allow agentic users to share content externally again, subject to your other sharing settings, run:

`Set-SPOTenant -RestrictExternalSharingForAgents $false`

### Restrict external sharing for a specific agentic application

To block external sharing only for the agentic users associated with a particular agentic application blueprint, add the blueprint to the control list. Replace `<BlueprintGUID>` with the ID of the blueprint.

`Set-SPOTenant -RestrictExternalSharing -AddAppIdtoList <BlueprintGUID>`

Adds the parent application blueprint GUID to the block list. All agentic users associated with that blueprint are restricted—not just one individual agentic user. Existing entries are preserved.

### Remove the restriction for a specific agentic application

To remove a blueprint from the control list so its agentic users are no longer restricted, run:

`Set-SPOTenant -RestrictExternalSharing <BlueprintGUID> -RemoveAppIdFromList`

### Check the current setting

To confirm whether the restriction is turned on for your tenant, run:

`Get-SPOTenant | Select-Object RestrictExternalSharingForAgents, RestrictExternalSharing`

## Allow specific agentic users to share content externally

To allow agentic users to share externally, set `RestrictExternalSharingForAgents` to `$false` and ensure their parent application blueprint is not in the `RestrictExternalSharing` block list.

Removing a blueprint restriction affects all agentic users associated with that blueprint, not an individual agent user.

Other SharePoint and OneDrive sharing policies still apply. If external sharing is limited to members of specified security groups, the agentic users must also belong to an allowed group. Security-group membership does not override the global agent restriction or a blueprint-specific block.

## FAQ

### Is the policy turned on by default?

No. The default value of RestrictExternalSharingForAgents is $false. Agentic users follow your existing sharing settings until you turn on the restriction.

### Does the policy affect people in my organization?

No. The restriction applies only to agentic users. People in your organization continue to share content according to your tenant and site sharing settings.

### Can I apply the policy to individual sites?

Not currently. The policy is configured at the tenant level, either for all agentic users or for the agentic users of selected blueprints.

### Can agentic users receive content shared by external users?

Agentic users can't be created as guests in Microsoft Entra ID. As a result, they can't redeem sharing links sent to them by external users or external agents.

### Which agentic applications can I restrict?

You can restrict agentic users associated with both first-party (Microsoft) and third-party agentic application blueprints.

## Related information

[Manage sharing settings for SharePoint and OneDrive in Microsoft 365](turn-external-sharing-on-or-off)

[Restrict discovery of SharePoint sites and content](restricted-access-control)

[Set-SPOTenant (SharePoint Online PowerShell reference)](/en-us/powershell/module/microsoft.online.sharepoint.powershell/set-spotenant)