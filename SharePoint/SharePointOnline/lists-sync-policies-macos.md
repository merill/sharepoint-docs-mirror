---
layout: Conceptual
title: Configure lists sync on Mac - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/lists-sync-policies-macos
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2023-03-03T00:00:00.0000000Z
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords: 
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: high
search.appverid: 
ms.collection:
- M365-collaboration
description: Learn how to configure lists sync on Mac by using Group Policy objects (GPOs).
locale: en-us
document_id: 3f18bc56-2cbd-8d4b-38bf-8ad1ee382ca0
document_version_independent_id: 9f72a4cc-2cc1-5c23-ce17-bc6d957cff9e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/lists-sync-policies-macos.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: lists-sync-policies-macos
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/lists-sync-policies-macos.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: cf5e2475-a547-8dfb-ef53-096bf9c9c045
---

# Configure lists sync on Mac - SharePoint in Microsoft 365 | Microsoft Learn

This article describes macOS preferences for Microsoft Lists (and SharePoint lists). For info about controlling OneDrive sync settings on macOS, see [Deploy and configure OneDrive on macOS](/en-us/sharepoint/deploy-and-configure-on-macos).

## Manage Lists sync settings on macOS using property list files

Lists sync gets packaged, installed, and updated through the OneDrive sync standalone (non-App Store) app's existing update mechanism. As a result, some Lists sync preferences are listed under the OneDrive group domain. After the OneDrive sync app for Mac is installed, users can configure settings for Lists sync. As an administrator, you might want to provide users in your organization with a standard set of preferences. Preferences for the Lists sync app for Mac are stored in property list `.plist` files.

| - | Lists sync preferences | OneDrive group preferences |
| --- | --- | --- |
| **.plist location** | ~/Library/Preferences/com.microsoft.SharePoint-mac.plist | ~/Library/Group Containers/UBF8T346G9.OneDriveStandaloneSuite/Library/Preferences/UBF8T346G9.OneDriveStandaloneSuite.plist |

## List of policies by string ID

- `DisableNucleusSync` - [Prevent Lists sync from running on the device](lists-sync-policies-macos#prevent-lists-sync-from-running-on-the-device)
- `BlockExternalListSync` - [Prevent users from syncing lists shared from other organizations](lists-sync-policies-macos#prevent-users-from-syncing-lists-shared-from-other-organizations)
- `DisableNucleusSilentConfig` - [Prevent users from getting silently signed in to Lists sync with existing Microsoft account credentials being used across Microsoft apps on macOS](lists-sync-policies-macos#prevent-users-from-getting-silently-signed-in-to-lists-sync-with-existing-microsoft-account-credentials-being-used-across-microsoft-apps-on-macos)

### Prevent Lists sync from running on the device

By default, Lists sync is turned on for users of Microsoft Lists. If you set this preference, Lists sync will be blocked from running on the device.

**Location**: [Lists Sync preferences](lists-sync-policies-macos#manage-lists-sync-settings-on-macos-using-property-list-files)

Prevent Lists sync from running on the device:

```xml
<key>DisableNucleusSync</key>
<integer>1</integer>
```

Re-enable Lists sync on the device:

```xml
<key>DisableNucleusSync</key>
<integer>0</integer>
```

### Prevent users from syncing lists shared from other organizations

Enabling this setting prevents users at your organization from syncing lists that are shared from other organizations. After the setting is enabled (value 1) on a computer, lists shared from other organizations won't sync. Disable the setting (value 0) to allow your users to sync external lists.

**Location**: [Lists Sync preferences](lists-sync-policies-macos#manage-lists-sync-settings-on-macos-using-property-list-files)

Prevent external List sync with:

```xml
<key>BlockExternalListSync</key>
<integer>1</integer>
```

Restore external List sync with:

```xml
<key>BlockExternalListSync</key>
<integer>0</integer>
```

### Prevent users from getting silently signed in to Lists sync with existing Microsoft account credentials being used across Microsoft apps on macOS

Lists sync is set up to automatically sign users in with credentials being used across other Microsoft apps on macOS like OneDrive. If you enable this setting, automatic sign-in and Lists sync setup wouldn't occur.

**Location**: [OneDrive group preferences](lists-sync-policies-macos#manage-lists-sync-settings-on-macos-using-property-list-files)

Prevent Lists sync silent configuration:

```xml
<key>DisableNucleusSilentConfig</key>
<integer>1</integer>
```

Restore Lists sync silent configuration with:

```xml
<key>DisableNucleusSilentConfig</key>
<integer>0</integer>
```