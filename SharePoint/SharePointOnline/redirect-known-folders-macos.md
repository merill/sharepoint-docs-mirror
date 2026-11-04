---
layout: Conceptual
title: Redirect and move macOS known folders to OneDrive - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/redirect-known-folders-macos
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2024-09-16T00:00:00.0000000Z
ms.reviewer: cagreen
ms.author: v-mactran
author: MachelleTranMSFT
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: upgrade-and-migration-article
ms.service: onedrive
ms.localizationpriority: medium
ms.collection:
- Strat_OD_admin
- M365-collaboration
- m365initiative-healthyonedrive
- onedrive-toc
ms.custom: 
search.appverid:
- ODB160
- ODB150
- GOB150
- GOB160
- MET150
description: In this article, you'll learn how to redirect users' Desktop and Documents folders to OneDrive on macOS using Folder Backup (Known Folder Move).
locale: en-us
document_id: 19c725af-36ac-8f78-981e-3c73e615e86c
document_version_independent_id: 2cba462a-e5c4-e8ff-b8c3-cb9c0f170231
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/redirect-known-folders-macos.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: redirect-known-folders-macos
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/redirect-known-folders-macos.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/aebdc4a3-c54b-4eea-94e3-663d5e166f57
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/1baec8e6-ab38-4b56-bb59-f6282d94f311
platformId: 4f5b3ac1-35ad-e254-cc84-9b0888e8524b
---

# Redirect and move macOS known folders to OneDrive - SharePoint in Microsoft 365 | Microsoft Learn

This article is for IT admins managing the OneDrive sync app for macOS.

There are two primary advantages of moving or redirecting macOS Desktop and Documents folders to Microsoft OneDrive for the users in your organization:

- Your users can continue using the folders they're familiar with. They don't have to change their daily work habits to save files to OneDrive.
- Saving files to OneDrive backs up your users' data in the cloud and gives them access to their files from any device.

For these reasons, we recommend moving (redirecting) Desktop and Documents folders to OneDrive with Folder Backup if you're an enterprise or large organization. [See all our recommendations for configuring the sync app](ideal-state-configuration). Small or medium businesses may also find this useful, but keep in mind you'll need some experience configuring settings. For info about the end-user experience, see [Protect your files by saving them to OneDrive](https://support.office.com/article/d61a7930-a6fb-4b95-b28a-6552e77c3057).

Note

OneDrive sync for macOS runs natively on Apple silicon. This support is generally available starting with build 22.022.

## Prepare to move Desktop and Documents folders on existing devices

The [standalone OneDrive sync app](https://support.microsoft.com/office/845dcf18-f921-435e-bf28-4e24b95e5fc0#OSVersion=Mac) (not from the Mac App Store) is required for Folder Backup. This app requires Full Disk Access, which can be granted and deployed by IT admins. For more information, see [Configure device restriction settings in Microsoft Intune](/en-us/mem/intune/configuration/device-restrictions-configure).

We recommend that you upgrade to the latest available build before you deploy.

Important

If your organization is large and your users have a lot of files in their Desktop and Documents folders, make sure you roll out the configuration slowly to minimize the network impact of uploading files. For users who have a lot of files in their folders, consider using the setting [AutomaticUploadBandwidthPercentage](deploy-and-configure-on-macos#automaticuploadbandwidthpercentage) temporarily to minimize the network impact and then disable the setting once uploads are complete.

### Folders redirected to other organizations

If a user’s Desktop and Documents folders are currently redirected to OneDrive in a different organization, redirecting to your organization’s OneDrive will create new Desktop and Documents folders and the user will see an empty desktop. The user will have to manually migrate files from the other organization’s OneDrive to OneDrive in your organization. We recommend that you disable the redirect to the other organization before redirecting to your organization if possible.

## About the Folder Backup settings

You can set OneDrive settings using software distribution tools such as [Microsoft Intune](/en-us/mem/intune/apps/apps-add-office365-macOS) and [Jamf Pro](https://www.jamf.com/products/jamf-pro/), [Munki](https://www.munki.org/), [AutoPkg](https://github.com/autopkg/autopkg), [Apple Remote Desktop](https://support.apple.com/guide/remote-desktop/welcome/mac), and [AppleScript](https://developer.apple.com/library/archive/documentation/AppleScript/Conceptual/AppleScriptX/AppleScriptX.html). You can also configure settings in a .plist file. For a full reference of available preferences and their settings, see [Deploy and configure the OneDrive sync app for macOS](deploy-and-configure-on-macos).

For new machines, Folder Backup can be configured from the start, so all new files are uploaded to the cloud. This is great for organizations as it increases user engagement with OneDrive, and admins can easily protect files with enterprise-level security and compliance that comes built in.

The following settings control the Folder Backup feature:

- [Prompt users to move Desktop and Documents folders to OneDrive (KFMOptInWithWizard)](deploy-and-configure-on-macos#kfmoptinwithwizard)

    Use **KFMOptInWithWizard** to give the users a call to action to move their Desktop and Documents macOS folders.

    ![Screenshot of the dialog that prompts users to back up their important folders.](sharepointonline/media/redirect-macos-manage-folder-backup.png)

    If users dismiss the prompt, a reminder notification appears in the Sync Activity Center until they move all available folders.

    ![Screenshot of the notification that reminds users to protect their important folders.](sharepointonline/media/redirect-macos-folder-backup.png)

    Important

    We recommend deploying the prompt setting for existing devices only, and limiting the deployment to 5,000 devices a day and not exceeding 20,000 devices a week between macOS and Windows.
- [Silently move macOS Desktop and Documents folders to OneDrive (KFMSilentOptIn)](deploy-and-configure-on-macos#kfmsilentoptin)

    Use **KFMSilentOptIn** to redirect and move folders to OneDrive without any user interaction. Move all the folders or select the desired individual folders. By default, the Desktop and Documents folders are moved. After a folder is moved, the setting won't affect the folder again, even if the selection for the folder changes.

    You can choose to display a notification to users after their folders have been redirected.

    We also recommend using this setting together with **[KFMOptInWithWizard](deploy-and-configure-on-macos#kfmoptinwithwizard)**. If moving the Desktop and Documents folders silently doesn't succeed, users are prompted to correct the error and continue.

    Important

    We recommend deploying the silent setting for existing devices and new devices while limiting the deployment of existing devices to 1,000 devices a day and not exceeding 4,000 devices a week between macOS and Windows.
- [Prevent users from turning off Folder Backup (KFMBlockOptOut)](deploy-and-configure-on-macos#kfmblockoptout)

    Use **KFMBlockOptOut** to force users to keep their Desktop and Documents folders directed to OneDrive.

    Note

    Users can direct their Desktop and Documents folders by opening OneDrive sync app preferences, clicking the **Backup tab**, and then clicking **Manage Backup**.
- [Prevent users from moving their macOS Desktop and Documents folders to OneDrive (KFMBlockOptIn)](deploy-and-configure-on-macos#kfmblockoptin)

    Use **KFMBlockOptIn** to prevent users from moving their Desktop and Documents folders to any OneDrive account.

For info about using the OneDrive sync settings, see [Deploy and configure the OneDrive sync app for macOS](deploy-and-configure-on-macos).