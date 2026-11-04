---
layout: Conceptual
title: Restrict SharePoint site access for applications and agents with Application Restrictions - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/restrict-application-agent-access
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: neilh
ms.author: neilh
author: nellymo
manager: jmcdowe
audience: Admin
ms.topic: how-to
ms.service: sharepoint-online
search.appverid:
- SPO160
- MET150
description: Learn how to restrict which applications and agents can access SharePoint sites and their content by using tenant and site policies in SharePoint Online Management Shell.
ms.date: 2026-10-13T00:00:00.0000000Z
locale: en-us
document_id: 4ffade43-6fcf-3cd9-cf5c-43e2df93cbf3
document_version_independent_id: e1621050-7188-06f6-218a-8db96568c56d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/restrict-application-agent-access.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: restrict-application-agent-access
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/restrict-application-agent-access.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
platformId: 5ac17f64-bf6a-b217-984f-4ab6535ea679
---

# Restrict SharePoint site access for applications and agents with Application Restrictions - SharePoint in Microsoft 365 | Microsoft Learn

Application Restrictions helps prevent oversharing to *applications* by designating which apps and agents can access a SharePoint site and its content. Applications not permitted by the policy can't access the site or its content, even when they hold Microsoft Entra consent and SharePoint permissions.

Application Restrictions adds an authorization boundary for applications that already have Entra consent and SharePoint permissions. It never grants permissions and it doesn't replace Entra consent. A request must pass **both** the existing permission model and Application Restrictions.

The policy is enforced when an application accesses SharePoint sites and content, either by itself (app-only) or on behalf of a signed-in user (app-plus-user, also called delegated).

Note

Application Restrictions governs **applications and agents**. To restrict which *users* can access a site, see [Restrict SharePoint site access with Microsoft 365 groups and Microsoft Entra security groups](/en-us/sharepoint/restricted-access-control). The two policies are independent and can be configured on the same site.

## How the policy is evaluated

Application Restrictions has two scopes that work together, and they're evaluated in a fixed order.

| Order | Scope | Effect |
| --- | --- | --- |
| 1 | **Not an app request, or not a third-party app** | Allowed. Application Restrictions doesn't apply. |
| 2 | **Tenant switch is off** | Allowed. All Application Restrictions enforcement is disabled, including any configured site policies. |
| 3 | **Tenant deny list** | Denied if the application matches. A site policy can't override this. |
| 4 | **Site policy absent or disabled** | Allowed. |
| 5 | **Site policy in `Allow` mode** | Allowed only if the application matches the allow list. All other governed apps are denied. |
| 6 | **Site policy in `Deny` mode** | Denied if the application matches the deny list. All other governed apps are allowed. |

Two consequences matter for planning:

- **The tenant switch is the master switch.** While it's off, nothing is enforced, including the tenant deny list and any configured site policies. Turning it on begins enforcement tenant-wide, including every site policy already staged.
- **The tenant deny list is your emergency brake.** It always outranks site configuration, so a site allow list can never re-admit an application denied at tenant scope.

### Microsoft applications are excluded

Microsoft first-party and core applications are excluded from both configuration and enforcement. You can't add a first-party application ID to a tenant or site list. The cmdlet rejects the change. At runtime, only applications positively classified as third-party are governed; an unclassified or first-party caller is never blocked by this policy.

### Applications and agent blueprints

A list entry is either a concrete application ID or a **parent agent blueprint ID**. A blueprint entry applies to the blueprint application itself and to every current or future agent app created from that blueprint. This lets you govern a whole family of agents with one entry.

You don't need to know which kind of ID you're supplying. Provide the application IDs and the service classifies and stores each one for you. Likewise, the allow and deny lists are returned to you as a single, duplicate-free list of GUIDs.

## Prerequisites

- You must be at least a SharePoint Administrator.
- Install and connect to [SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
- Collect the Entra **application (client) IDs** you intend to govern. These are application IDs, not directory object IDs.

Important

Application Restrictions doesn't apply to personal sites in this release. It also doesn't trim search results or enumeration, and it doesn't offer granular access levels. A request is either allowed to continue through existing authorization or blocked from the site.

## Step 1: Turn on Application Restrictions for your organization

Enforcement is off until you enable it at tenant scope. Nothing you configure at site scope takes effect until you do.

```powershell
Enable-SPOTenantRestrictedAppAccessControl
```

Enabling begins enforcement tenant-wide, including all configured site policies, so the cmdlet warns you before it commits. To confirm the current state at any time:

```powershell
Get-SPOTenantRestrictedAppAccessControl
```

The cmdlet returns `Enabled` and `RestrictedAppIds`—the tenant deny list. Reads are always authoritative and uncached, so the values reflect the latest committed policy.

Tip

A safer sequence for a first rollout is to stage site policies first (steps 3 and 4), verify them, and turn on the tenant switch last. Nothing is enforced until the switch is on.

## Step 2: Block an application across the entire organization

The tenant list is a deny list, and it's intended as an emergency control for an application you want kept out of every site. Use it sparingly. For scoped restrictions, prefer a site policy.

Add one or more applications:

```powershell
Set-SPOTenantRestrictedAppAccessControlList -AddRestrictedAppIds "11111111-1111-1111-1111-111111111111","22222222-2222-2222-2222-222222222222"
```

Remove an application:

```powershell
Set-SPOTenantRestrictedAppAccessControlList -RemoveRestrictedAppIds "11111111-1111-1111-1111-111111111111"
```

Notes on behavior:

- Additions and removals apply as one atomic update, and removals are applied before additions. An ID can't appear in both parameters.
- Adding is all-or-none. If any supplied ID belongs to a Microsoft first-party application or the service can't classify it, the whole change is rejected and nothing is written.
- Removing doesn't require the application to still exist, so you can always clean up stale or deleted app IDs.
- List changes never turn the tenant switch on or off. Configuration and enablement stay independent.
- The tenant deny list holds a maximum of **100** application IDs.

## Step 3: Choose the enforcement mode for a site

Each site has an active mode that decides which of its two lists is enforced.

| Mode | Behavior | Use when |
| --- | --- | --- |
| `Allow` | Only applications on the allow list can access the site. All other governed apps are denied. | You want a known, closed set of apps on a sensitive site. |
| `Deny` | Applications on the deny list are blocked. All other governed apps are allowed. | You want to exclude specific apps and leave the site otherwise open. |

```powershell
Set-SPOSiteRestrictedAppAccessControlMode -Identity "https://contoso.sharepoint.com/sites/Finance" -Mode Allow
```

You must set a mode before you enable Application Restrictions on a site. Every site cmdlet accepts `-Identity` as either a site URL or a site ID.

Both lists are stored permanently, and a mode change preserves both of them. Only the list selected by the active mode participates in enforcement; the other is kept for later and has no runtime effect. When you switch modes, the cmdlet warns you first, identifying the current mode, the target mode, the size of the newly active list, and the new default decision.

Important

An empty active **allow** list blocks every governed third-party and agentic application from the site. An empty active **deny** list blocks nothing.

## Step 4: Add applications to the site's allow or deny list

Specify which list you're changing with `-ListType`, then add or remove IDs:

```powershell
# Add two applications to the allow list
Set-SPOSiteRestrictedAppAccessControlList -Identity "https://contoso.sharepoint.com/sites/Finance" -ListType AllowList -AddRestrictedAppIds "11111111-1111-1111-1111-111111111111","22222222-2222-2222-2222-222222222222"

# Remove an application from the allow list
Set-SPOSiteRestrictedAppAccessControlList -Identity "https://contoso.sharepoint.com/sites/Finance" -ListType AllowList -RemoveRestrictedAppIds "11111111-1111-1111-1111-111111111111"
```

The same rules as the tenant list apply: updates are atomic, removals occur before additions, an ID can't appear in both parameters, and all additions fail if any ID belongs to a first-party application. If you try to remove an ID that isn't present, the cmdlet returns a validation error.

Each site list holds up to **100** entries, and the two lists together hold up to **200**.

List and mode changes update only the configuration. They never turn enforcement on. That's deliberate: it prevents a single added ID from instantly activating an allow list on an unconfigured site and locking out every other application.

## Step 5: Turn on enforcement for the site

Once the mode and lists are staged and reviewed, enable the site:

```powershell
Enable-SPOSiteRestrictedAppAccessControl -Identity "https://contoso.sharepoint.com/sites/Finance"
```

The cmdlet fails if no mode is set on the site. Set a mode first by completing step 3.

## Step 6: Verify the policy

```powershell
Get-SPOSiteRestrictedAppAccessControl -Identity "https://contoso.sharepoint.com/sites/Finance"
```

The cmdlet returns `SiteUrl`, `Enabled`, `Mode`, `AllowList`, and `DenyList`. Because the returned object carries its own `SiteUrl`, you can pipe sites into the cmdlet and still identify each result.

Confirm all three layers before you rely on the outcome:

```powershell
# Is the master switch on, and is the app denied tenant-wide?
Get-SPOTenantRestrictedAppAccessControl

# What is this site enforcing right now?
Get-SPOSiteRestrictedAppAccessControl -Identity "https://contoso.sharepoint.com/sites/Finance"
```

If the returned policy includes `IsPolicyDataMalformed`, the stored site policy couldn't be read. Application Restrictions doesn't enforce on that site until the policy is rewritten. Existing SharePoint authorization still applies, so reapply the configuration to replace it.

## Change or roll back a policy

Choose the narrowest action that achieves what you want.

| Goal | Cmdlet | What it preserves |
| --- | --- | --- |
| Stop enforcing on one site, keep the configuration | `Disable-SPOSiteRestrictedAppAccessControl` | Mode and both lists |
| Empty one list, keep everything else | `Clear-SPOSiteRestrictedAppAccessControlList -ListType <AllowList or DenyList>` | The other list, the mode, and site enablement |
| Remove a site's policy entirely | `Clear-SPOSiteRestrictedAppAccessControlPolicy` | It preserves nothing. The cmdlet disables enforcement and removes the mode and both lists. |
| Stop enforcing organization-wide, keep the deny list | `Disable-SPOTenantRestrictedAppAccessControl` | The tenant deny list and all site configuration |
| Remove the tenant policy entirely | `Clear-SPOTenantRestrictedAppAccessControlPolicy` | It preserves nothing. The cmdlet disables the switch and clears the deny list. |

Examples:

```powershell
# Pause enforcement on a site without losing the configuration
Disable-SPOSiteRestrictedAppAccessControl -Identity "https://contoso.sharepoint.com/sites/Finance"

# Empty the deny list but keep the allow list, mode, and enablement
Clear-SPOSiteRestrictedAppAccessControlList -Identity "https://contoso.sharepoint.com/sites/Finance" -ListType DenyList

# Remove the site policy entirely
Clear-SPOSiteRestrictedAppAccessControlPolicy -Identity "https://contoso.sharepoint.com/sites/Finance"
```

Warning

Clearing the list that the active mode enforces changes enforcement immediately. Clearing an active **allow** list means no third-party applications can access the site; clearing an active **deny** list means all of them can. The cmdlet warns you and states whether the change takes effect now or when enforcement is next enabled.

Disabling or clearing at **tenant** scope stops every configured site policy from enforcing, not just the tenant deny list. Both cmdlets warn you before committing.

## Confirmation prompts and automation

Every cmdlet that changes policy supports `-WhatIf` and `-Confirm`, and prompts for confirmation by default.

```powershell
# Preview the impact of a mode switch without changing anything
Set-SPOSiteRestrictedAppAccessControlMode -Identity "https://contoso.sharepoint.com/sites/Finance" -Mode Deny -WhatIf

# Suppress the prompt in an automated script
Enable-SPOSiteRestrictedAppAccessControl -Identity "https://contoso.sharepoint.com/sites/Finance" -Confirm:$false
```

`-WhatIf` shows the same impact summary as the interactive prompt. Using `-Confirm:$false` suppresses only the prompt. It doesn't bypass validation, authorization, auditing, or first-party protection.

## Auditing

Policy changes are recorded in the unified audit log with dedicated operations:

| Operation | Raised by |
| --- | --- |
| `RestrictedAppAccessControlTenantPolicyUpdated` | Tenant mutations |
| `RestrictedAppAccessControlTenantPolicyCleared` | A complete tenant clear |
| `RestrictedAppAccessControlSitePolicyUpdated` | Site mutations |
| `RestrictedAppAccessControlSitePolicyCleared` | A complete site clear |

Records contain only the policy fields you already see in PowerShell. Tenant records may include `Enabled`, `RestrictedAppIds`, and `IsPolicyDataMalformed`; site records may include `Enabled`, `Mode`, `AllowList`, `DenyList`, and `IsPolicyDataMalformed`, with `SiteUrl` and the acting administrator supplied by the audit envelope. No secrets or access tokens are recorded.

A record is written only after a change is persisted and only for properties whose values actually changed. An update that changes nothing emits no record.

## Cmdlet reference

**Tenant**

| Cmdlet | Purpose |
| --- | --- |
| [Get-SPOTenantRestrictedAppAccessControl](/en-us/powershell/module/sharepoint-online/get-spotenantrestrictedappaccesscontrol) | Return the tenant switch and deny list |
| [Set-SPOTenantRestrictedAppAccessControlList](/en-us/powershell/module/sharepoint-online/set-spotenantrestrictedappaccesscontrollist) | Add or remove applications on the tenant deny list |
| [Enable-SPOTenantRestrictedAppAccessControl](/en-us/powershell/module/sharepoint-online/enable-spotenantrestrictedappaccesscontrol) | Turn on enforcement organization-wide |
| [Disable-SPOTenantRestrictedAppAccessControl](/en-us/powershell/module/sharepoint-online/disable-spotenantrestrictedappaccesscontrol) | Turn off enforcement, preserving the deny list |
| [Clear-SPOTenantRestrictedAppAccessControlPolicy](/en-us/powershell/module/sharepoint-online/clear-spotenantrestrictedappaccesscontrolpolicy) | Turn off enforcement and clear the deny list |

**Site**

| Cmdlet | Purpose |
| --- | --- |
| [Get-SPOSiteRestrictedAppAccessControl](/en-us/powershell/module/sharepoint-online/get-spositerestrictedappaccesscontrol) | Return a site's enablement, mode, and both lists |
| [Set-SPOSiteRestrictedAppAccessControlMode](/en-us/powershell/module/sharepoint-online/set-spositerestrictedappaccesscontrolmode) | Set the active mode to `Allow` or `Deny` |
| [Set-SPOSiteRestrictedAppAccessControlList](/en-us/powershell/module/sharepoint-online/set-spositerestrictedappaccesscontrollist) | Add or remove applications on a site list |
| [Enable-SPOSiteRestrictedAppAccessControl](/en-us/powershell/module/sharepoint-online/enable-spositerestrictedappaccesscontrol) | Turn on enforcement for the site |
| [Disable-SPOSiteRestrictedAppAccessControl](/en-us/powershell/module/sharepoint-online/disable-spositerestrictedappaccesscontrol) | Turn off enforcement, preserving mode and lists |
| [Clear-SPOSiteRestrictedAppAccessControlList](/en-us/powershell/module/sharepoint-online/clear-spositerestrictedappaccesscontrollist) | Empty one list |
| [Clear-SPOSiteRestrictedAppAccessControlPolicy](/en-us/powershell/module/sharepoint-online/clear-spositerestrictedappaccesscontrolpolicy) | Remove the site policy entirely |

Application Restrictions is managed only through these dedicated cmdlets. `Get-SPOTenant` and `Get-SPOSite` don't return the policy, and `Set-SPOTenant` and `Set-SPOSite` can't change it.

## Limits

| Limit | Value |
| --- | --- |
| Applications on the tenant deny list | 100 |
| Entries per site list | 100 |
| Combined entries per site | 200 |