---
layout: Conceptual
title: Standard storage for unlicensed OneDrive accounts - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/standard-storage-unlicensed-onedrive-accounts
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-08-26T00:00:00.0000000Z
ms.author: trgreen
author: trent-green
manager: leeclontz
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: onedrive
ms.localizationpriority: medium
ms.collection:
- Strat_OD_admin
- M365-collaboration
- Essentials-manage
description: Learn how to manage Standard storage for unlicensed OneDrive accounts, including the tenant-wide active-storage period and per-account reactivation dates.
locale: en-us
document_id: f2c6a37d-d832-fc3b-e3cc-28f86412687a
document_version_independent_id: 6523ee1c-5128-0cd6-a348-9856255738f3
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/standard-storage-unlicensed-onedrive-accounts.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: standard-storage-unlicensed-onedrive-accounts
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/standard-storage-unlicensed-onedrive-accounts.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 1288effe-09e4-cae0-9418-d10cc8c979e6
---

# Standard storage for unlicensed OneDrive accounts - SharePoint in Microsoft 365 | Microsoft Learn

## Overview

Standard storage gives SharePoint administrators more control over how long unlicensed OneDrive accounts remain active before they are archived. It also lets an administrator reactivate a specific archived account for longer than the ordinary 30-day reactivation period. It builds on the default unlicensed account lifecycle described in [Manage unlicensed OneDrive user accounts](unlicensed-onedrive-accounts).

The billing experience has two distinct steps:

- **Connect pay-as-you-go billing.** Before admins can reactivate archived unlicensed OneDrive accounts, set up pay-as-you-go billing in the Microsoft 365 admin center. Follow [Set up pay-as-you-go billing](/en-us/microsoft-365/commerce/services/pay-as-you-go-setup-billing-node) to link an Azure subscription, then enable that billing subscription for unlicensed OneDrive account billing. For more information about the unlicensed account lifecycle and billing states, see [Manage unlicensed OneDrive user accounts](unlicensed-onedrive-accounts).
- **Enable Standard storage.** Standard storage is a separate opt-in that unlocks the tenant-wide duration control and lets selected reactivated accounts remain active beyond 30 days. When Standard storage is available, enable it from the dedicated unlicensed OneDrive accounts experience in the Microsoft 365 admin center. There is no SharePoint Online PowerShell parameter for enabling the billing policy or Standard storage.

Enabling Standard storage does not reactivate every archived account. Increasing the tenant-wide active-storage period also applies to existing unlicensed accounts: archived accounts that have been unlicensed for less than the newly configured period are reactivated. Accounts already beyond that period remain archived. Administrators can use account-specific reactivation controls for selected accounts. Content is billed according to its current tier: archived content uses the Archive meter, and active content retained through Standard storage uses the Standard meter.

Increasing the tenant-wide period can incur reactivation fees for eligible archived accounts that are reactivated. During calendar year 2026, these reactivation fees are waived when Standard storage is enabled. See Pricing.

Note

Standard storage will be generally available for unlicensed OneDrive accounts starting in October 2026. Until then, the Standard storage billing option might not appear in the Microsoft 365 admin center, even after you connect pay-as-you-go billing.

## Capabilities

### Standard storage billing

Set up pay-as-you-go billing and enable Standard storage in the Microsoft 365 admin center before using the new duration controls. There is no SharePoint Online PowerShell parameter for enabling the billing policy or Standard storage.

### Duration and account controls

| Scenario | Scope | Intended behavior |
| --- | --- | --- |
| Set the active-storage period | Tenant (all applicable unlicensed OneDrive accounts) | Changes when accounts become read-only and are archived. Supported values are 93 through 3,650 days. |
| Check the current period | Tenant | Reads the current active-storage period through Get-SPOTenant. |
| Reactivate until a specific date | One archived unlicensed OneDrive account | Reactivates the account and keeps it active until the date supplied with -KeepActiveUntil. |
| Extend an active period | One active or reactivating account | Updates the Standard storage end date by running the same command with a later valid date. |
| Archive early | One active account | Returns the account to Archive storage before its scheduled date. |

The tenant period can't exceed 3,650 days, and an account-specific extension requires a date. Both the tenant period and the per-account `-KeepActiveUntil` flag require a duration or date. There's no way to keep an account active indefinitely. Extend the period or date later if continued access is required.

Manage these duration controls through SharePoint Online PowerShell. Controls for the same scenarios are planned for the SharePoint admin center later.

## Pricing

Archive storage, Standard storage, and reactivation are billed through pay-as-you-go. For current prices, see [Storage services](/en-us/microsoft-365/documentprocessing/syntex-pay-as-you-go-services#storage-services).

An ordinary reactivation includes the standard 30-day access period. Standard storage charges apply when an account remains active beyond that window. During calendar year 2026, the reactivation fee is waived when Standard storage is enabled.

Reactivation fees also apply when an archived account is reactivated by increasing `UnlicensedOneDriveAccountsActiveStoragePeriod`, not only when an administrator runs a per-account reactivation command. The published reactivation rate is $0.60 per GB reactivated; see [Storage services](/en-us/microsoft-365/documentprocessing/syntex-pay-as-you-go-services#storage-services) for current pricing. During calendar year 2026, the fee is waived when Standard storage is enabled. Reactivation fees are separate from ongoing storage charges. Accounts that remain archived continue to use the Archive meter, while active content retained through Standard storage uses the Standard meter.

## Lifecycle example

The default tenant-wide archive point is 93 days after an account becomes unlicensed. The account becomes read-only 33 days before it is archived. For the complete default timeline, including read-only, eDiscovery, and deletion milestones, see [Manage unlicensed OneDrive user accounts](unlicensed-onedrive-accounts).

If an administrator changes the tenant period to 365 days:

- The account remains active through day 331.
- The account becomes read-only on day 332.
- The account is archived on day 365.

After an account is archived, ordinary reactivation provides 30 days of access. Use `-KeepActiveUntil` when the account must remain active beyond that standard window.

## Before you begin

Confirm the following prerequisites:

- Pay-as-you-go billing is connected for unlicensed OneDrive accounts. For details about identifying and managing these accounts, see [Manage unlicensed OneDrive user accounts](unlicensed-onedrive-accounts).
- Standard storage is enabled in the Microsoft 365 admin center.
- You're using a SharePoint Online Management Shell version that exposes the new parameters.
- You're connected to SharePoint Online as a SharePoint administrator.
- You have the OneDrive personal-site URL for each account you want to manage.

Connect to the SharePoint Online admin endpoint:

```powershell
Connect-SPOService -Url "https://contoso-admin.sharepoint.com"
```

Replace contoso and all sample OneDrive URLs in this article with values for your tenant.

## Admin workflow

### 1. Set the tenant-wide Standard storage period

Use `Set-SPOTenant` to specify how many days an unlicensed OneDrive account remains active before it is archived:

```powershell
Set-SPOTenant `
    -UnlicensedOneDriveAccountsActiveStoragePeriod 365
```

The supported range is 93 through 3,650 days. The command displays a confirmation prompt. The read-only stage begins 33 days before the configured archive date.

Standard storage normally must be enabled to change this setting. If a tenant previously configured a custom value and later disables Standard storage billing, the service defaults to 93 days functionally.

The setting applies retroactively, not only to accounts that become unlicensed after the change. Increasing the period can therefore reactivate existing archived accounts without a separate per-account reactivation command.

For example, increasing the tenant period from 93 to 180 days has these results:

| Account | Days unlicensed | State before change | Result | Reactivation fee from this change |
| --- | --- | --- | --- | --- |
| A | 38 | Active | Remains active | None; no reactivation occurs |
| B | 105 | Archived | Reactivated because it is within the new period | Applies, unless the change is made during calendar year 2026 with Standard storage enabled |
| C | 227 | Archived | Remains archived because it is beyond the new period | None; no reactivation occurs |

Reactivation caused by this tenant-setting change incurs the reactivation fee, except during calendar year 2026 when the fee is waived with Standard storage enabled. The read-only stage still begins 33 days before the configured archive date.

**Best practice:** Keep the default at 93 days unless your organization has a defined business, legal, or compliance need for a longer lifecycle. Use the shortest period that meets the requirements.

### 2. Check the current tenant setting

```powershell
Get-SPOTenant | Select-Object UnlicensedOneDriveAccountsActiveStoragePeriod
```

If the property returns 0, the connected SharePoint Online endpoint might not yet expose the property. Update the SharePoint Online Management Shell and verify that the feature is available for the tenant.

### 3. Reactivate an account for the ordinary 30-day period

Use ordinary reactivation when 30 days of access is sufficient:

```powershell
Set-SPOSiteArchiveState `
    -Identity "https://contoso-my.sharepoint.com/personal/user_contoso_com" `
    -ArchiveState Active
```

The target must be an archived unlicensed OneDrive personal site. Connecting the billing policy permits this ordinary reactivation even when the account-specific Standard storage extension is not used.

### 4. Reactivate an account until a specific date

Use `-KeepActiveUntil` when access is required beyond the ordinary 30-day period:

```powershell
Set-SPOSiteArchiveState `
    -Identity "https://contoso-my.sharepoint.com/personal/user_contoso_com" `
    -ArchiveState Active `
    -KeepActiveUntil "2027-08-13"
```

The supplied date is interpreted in the administrator's local time and converted to UTC. For a newly reactivated account, the date must extend beyond the ordinary 30-day reactivation window. The server validates billing eligibility, rollout availability, site type, site state, and the date.

### 5. Extend an account that is active or reactivating

Run the same command with a later valid date:

```powershell
Set-SPOSiteArchiveState `
    -Identity "https://contoso-my.sharepoint.com/personal/user_contoso_com" `
    -ArchiveState Active `
    -KeepActiveUntil "2027-10-31"
```

This command updates the stored Standard storage date. It doesn't change the tenant-wide active-storage period.

### 6. Return an account to Archive storage early

When active access is no longer needed, archive the account before its scheduled date:

```powershell
Set-SPOSiteArchiveState `
    -Identity "https://contoso-my.sharepoint.com/personal/user_contoso_com" `
    -ArchiveState Archived
```

This command returns the account to Archive storage and stops continued Standard storage use for that account.

## Choose the right control

| Scenario | Recommended action |
| --- | --- |
| The default 93-day lifecycle is appropriate for most accounts | Leave the tenant period at 93 days. |
| All applicable unlicensed accounts need a longer lifecycle | Set UnlicensedOneDriveAccountsActiveStoragePeriod to a justified value from 94 through 3,650. |
| A single archived account needs access for 30 days or less | Reactivate it with -ArchiveState Active and omit -KeepActiveUntil. |
| A single archived account needs access beyond 30 days | Reactivate it with -ArchiveState Active and a valid -KeepActiveUntil date. |
| An active or reactivating account needs more time | Run the command again with a later -KeepActiveUntil date. |
| Access is no longer needed | Set -ArchiveState Archived to return the account to Archive storage early. |

## Best practices

- Use a longer tenant-wide period only when the requirement applies broadly. Use account-specific dates for exceptions.
- Return accounts to Archive storage when active access is no longer required.
- Monitor both Archive and Standard storage consumption and charges.

## Troubleshooting

### The tenant parameter isn't recognized

Update the SharePoint Online Management Shell. Confirm that the installed build includes UnlicensedOneDriveAccountsActiveStoragePeriod.

### Get-SPOTenant returns 0 for the property

The connected endpoint might not yet have the server build that exposes the read-back property. Verify rollout eligibility and try again after updating the management shell.

These standard-storage properties require PowerShell version 16.0.27600.12000 or higher.

### The tenant setting update is rejected

Verify that:

- The value is from 93 through 3,650.
- Standard storage billing is enabled.

If billing was disabled after a custom value was configured, only a reset to 93 is allowed.

### Reactivation or extension is rejected

Verify that:

- The URL identifies a OneDrive personal site, not a SharePoint team or communication site.
- The account is unlicensed and in a supported archive, active, or reactivating state.
- You use `-KeepActiveUntil` only with `-ArchiveState Active`.
- Standard storage is enabled when you request a date beyond the ordinary 30-day period.
- The date is valid and extends beyond the standard reactivation window.

### The account should no longer use Standard storage

Run `Set-SPOSiteArchiveState` with `-ArchiveState Archived` to return it to Archive storage.

## Related guidance

- [Manage unlicensed OneDrive user accounts](unlicensed-onedrive-accounts)
- [Connect to SharePoint Online PowerShell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)