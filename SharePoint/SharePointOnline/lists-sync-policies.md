---
layout: Conceptual
title: Lists sync policies - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/lists-sync-policies
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2021-07-02T00:00:00.0000000Z
ms.reviewer: andreye
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: article
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: high
search.appverid:
- SPO160
- MET150
ms.collection:
- M365-collaboration
description: Learn how to control Lists sync by using Group Policy objects (GPOs).
locale: en-us
document_id: ea355f21-5b38-e118-56eb-9d5e5fc6f38e
document_version_independent_id: 767521a0-4274-f730-3bb3-cf2dd7787047
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/lists-sync-policies.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: lists-sync-policies
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/lists-sync-policies.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 68f9d778-a0fb-19a8-f4be-04c90f2c8d37
---

# Lists sync policies - SharePoint in Microsoft 365 | Microsoft Learn

This article describes the Group Policy objects (GPOs) for Microsoft Lists (and SharePoint lists) that administrators can configure by using Group Policy. Use the registry key information to confirm that a setting is enabled. Lists sync policies are listed under OneDrive because Lists sync gets packaged, installed, and updated through the OneDrive sync app's existing update mechanism. For information about controlling OneDrive sync settings by Group Policy, see [OneDrive policies](/en-us/onedrive/use-group-policy).

Note

To preserve Lists performance acceleration when the Chromium-based browser restrictions on local network access take effect, deploy the browser policy `LocalNetworkAccessAllowedForUrls` now. Add your tenant’s SharePoint Online and OneDrive endpoints (for example:

- `https://YOURTENANT-my.sharepoint.com`
- `https://YOURTENANT.sharepoint.com` Policy reference (Edge): [https://learn.microsoft.com/deployedge/microsoft-edge-browser-policies/localnetworkaccessallowedforurls](/en-us/deployedge/microsoft-edge-browser-policies/localnetworkaccessallowedforurls) Policy reference (Chrome): https://chromeenterprise.google/policies/#LocalNetworkAccessAllowedForUrls

## List of policies by string ID

- (DisableListSync) [Prevent Lists sync from running on this device](lists-sync-policies#prevent-lists-sync-from-running-on-this-device)
- (BlockExternalListSync) [Prevent users from syncing lists shared from other organizations](lists-sync-policies#prevent-users-from-syncing-lists-shared-from-other-organizations)
- (DisableNucleusSilentConfig) Prevent users from getting silently signed in to offline experiences on the web

### Prevent Lists sync from running on this device

By default, Lists sync is turned on for users of Microsoft Lists, which allows users to access and edit their lists even when offline. If you enable this policy, Lists sync will be blocked from running on the device.

Prevent Lists sync from running on the device:

`[HKLM\SOFTWARE\Policies\Microsoft\OneDrive] "DisableNucleusSync" = "dword:1"`

Re-enable Lists sync on the device:

`[HKLM\SOFTWARE\Policies\Microsoft\OneDrive] "DisableNucleusSync" = "dword:0"`

Note

This policy's registry value name `DisableNucleusSync` differs from the policy name `DisableListSync`. When verifying this policy is applied, look for `DisableNucleusSync` in the registry.

### Prevent users from syncing lists shared from other organizations

Enabling this setting prevents users at your organization from syncing lists that are shared from other organizations. After the setting is enabled (by entering value **1**) on a computer, lists shared from other organizations won't sync. Disable the setting (by entering value **0**) to allow your users to sync external lists.

Prevent external List sync with:

`[HKLM\SOFTWARE\Policies\Microsoft\OneDrive] "BlockExternalListSync" = "dword:1"`

Restore external List sync with:

`[HKLM\SOFTWARE\Policies\Microsoft\OneDrive] "BlockExternalListSync" = "dword:0"`

### Prevent users from getting silently signed in to offline experiences on the web

Offline experiences in Microsoft Lists and OneDrive on the web are set up to automatically sign in users with their Microsoft Entra account credentials. If you enable this setting, people who used offline experiences in Microsoft Lists and OneDrive on the web previously and who are signed in on a Microsoft Entra-joined PC will no longer be able to set up offline experiences without entering their account credentials.

Important

If the M365 browser extension isn't installed on users' Chromium-based browsers (Microsoft Edge, Google Chrome, and so on), we recommend leaving silent account configuration enabled to ensure the seamless operation of List sync.

Enabling this policy sets the following registry key value to 1:

`[HKLM\SOFTWARE\Policies\Microsoft\OneDrive] "DisableNucleusSilentConfig" = "dword:00000001"`

For more information about this feature, including troubleshooting steps, see [Silently configure user accounts](/en-us/onedrive/use-silent-account-configuration).

## Control Lists sync on unmanaged devices and based on location

You can use the following settings to control access to Lists sync from unmanaged devices and configure network location-based access to List sync.

[Control access from unmanaged devices](control-access-from-unmanaged-devices)

[Control access to SharePoint and OneDrive based on network location](control-access-based-on-network-location)