---
layout: Conceptual
title: Prevent users from contacting Microsoft directly - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/disable-contact-support-send-feedback
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-03-26T00:00:00.0000000Z
ms.reviewer: pramod.balasu
ms.author: v-mactran
author: MachelleTranMSFT
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: onedrive
ms.custom: onedrive-toc
ms.collection: M365-collaboration
ms.localizationpriority: medium
description: This article describes how SharePoint Administrators in Microsoft 365 can disable the 'Contact support' and 'Send feedback' features in the OneDrive sync app.
locale: en-us
document_id: b85afd14-7a27-550f-c835-eec8c208b93e
document_version_independent_id: 0b743d9b-3bdc-dbea-c48e-48fa5bd12f14
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/disable-contact-support-send-feedback.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: disable-contact-support-send-feedback
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/disable-contact-support-send-feedback.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 1158989f-d268-8982-f04f-42566524d991
---

# Prevent users from contacting Microsoft directly - SharePoint in Microsoft 365 | Microsoft Learn

Note

- The ability of OneDrive users to contact Microsoft directly in the form of support requests is disabled before end of calendar year 2022.  Only an administrator is able to open a support request with Microsoft.
- Users can still send feedback as usual on the OneDrive app on Windows, Mac, iOS, and Android devices.
- For **Windows and Mac**: 'Contact support' is disabled in future updates and for existing or old versions, it doesn't let you create a service request.
- For **Android**: 'Report a Problem' creates a feedback item instead of a service request.
- For **iOS**: 'Ask for help' will be disabled in future updates and for existing or old versions, you're unable to create a service request. 'Report a Problem' creates a feedback item instead of a service request.

The OneDrive sync app (OneDrive.exe) allows users to contact Microsoft directly from within the app. Users can:

- Create a support ticket by selecting **Get help** and then selecting the **Contact support** link in the help pane.
- Send positive or negative feedback directly to Microsoft by selecting **Send feedback**.

![The Get help and Send feedback commands](sharepointonline/media/img1-4717638.png)

As a SharePoint Administrator, you can disable the support features to prevent people in your organization from contacting Microsoft directly.

If you disable these features, users can still select **Get help** and view help articles, but the **Contact support** link no longer appears.

The following screenshots show the changes after you disable the support features.

![The Get help and Feedback commands](sharepointonline/media/img2-4717638.png)

![The help pane](sharepointonline/media/img3-4717638.png)

Note

If you disable "Contact support" and "Send feedback" but allow users to sync personal accounts, they can still contact support and send feedback directly to Microsoft from the OneDrive sync app when they're signed in with their personal account.

## Disable "Contact support" and "Send feedback" in Windows

To disable these features in Windows, you can:

- Use the [Set-SPOTenantSyncClientRestriction](/en-us/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction) in Microsoft PowerShell
- Edit the registry

### Use PowerShell

1. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    Note

    If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell."
2. Connect to SharePoint as a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
3. Run the following command:

    ```PowerShell
    Set-SPOTenantSyncClientRestriction -DisableReportProblemDialog $true
    ```

### Edit the registry

Follow these steps to disable the features on a PC by editing the registry.

Important

Follow the steps in this section carefully. Serious problems might occur if you modify the registry incorrectly. Before you modify it, [back up the registry for restoration](https://support.microsoft.com/help/322756/how-to-back-up-and-restore-the-registry-in-windows) in case problems occur.

1. In Registry Editor, locate the following subkey: **HKEY\_CURRENT\_USER\Software\Microsoft\OneDrive**
2. Right-click **OneDrive**, select **New**, and then select **DWORD (32-bit) Value**.
3. Enter `DisableReportProblemDialog` for the name.
4. Right-click the new registry key, enter **1** for **Value data**, and then select **OK**.

## Disable "Contact support" and "Send feedback" on Mac

To disable the features in the OneDrive sync app for Mac, add a preference to defaults.

For the standalone Mac sync app: `defaults write com.microsoft.OneDrive DisableReportProblemDialog 1`

For the Mac sync app installed through the Mac App Store:

`defaults write com.microsoft.OneDrive-mac DisableReportProblemDialog 1`