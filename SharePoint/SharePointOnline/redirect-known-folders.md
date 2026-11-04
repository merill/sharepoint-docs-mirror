---
layout: Conceptual
title: Redirect and move Windows known folders to OneDrive - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/redirect-known-folders
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-03-27T00:00:00.0000000Z
ms.reviewer: gacarini
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
ms.custom:
- seo-marvel-apr2020
- onedrive-toc
search.appverid:
- ODB160
- ODB150
- GOB150
- GOB160
- MET150
ms.assetid: e1b3963c-7c6c-4694-9f2f-fb8005d9ef12
description: In this article, you learn how to redirect users' Documents folders or other known folders to OneDrive.
locale: en-us
document_id: fd9bb99f-256c-f719-8d64-5c95b1a97d15
document_version_independent_id: 18673c5f-127d-1f38-3d6f-575434ab516a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/redirect-known-folders.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: redirect-known-folders
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/redirect-known-folders.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: cc9db121-2eca-3dd8-59ab-277d86691a22
---

# Redirect and move Windows known folders to OneDrive - SharePoint in Microsoft 365 | Microsoft Learn

This article is for IT admins managing the OneDrive sync app.

There are two primary advantages of moving or redirecting Windows known folders (Desktop, Documents, Pictures, Screenshots, and Camera Roll) to Microsoft OneDrive for the users in your domain:

- Your users can continue using the folders they're familiar with. They don't have to change their daily work habits to save files to OneDrive.
- Saving files to OneDrive backs up your users' data in the cloud and gives them access to their files from any device.

For these reasons, we recommend moving (redirecting) known folders to OneDrive if you're an enterprise or large organization. [See all our recommendations for configuring the sync app](ideal-state-configuration). Small or medium businesses might also find this process useful, but keep in mind you need some experience configuring policies. For info about the end-user experience, see [Protect your files by saving them to OneDrive](https://support.office.com/article/d61a7930-a6fb-4b95-b28a-6552e77c3057).

## Prepare to move known folders on existing devices

We recommend that you upgrade to the latest available build before you deploy.

For information on issues that can prevent folders from being moved, see [Fix problems with folder protection](https://support.office.com/article/d61a7930-a6fb-4b95-b28a-6552e77c3057#BKMK_FixProblems). Known Folder Move doesn't work for users syncing OneDrive files in SharePoint Server.

Important

If your organization is large and your users have many files in their known folders, make sure you roll out the configuration slowly to minimize the network impact of uploading files. For users who have many files in their known folders, consider using the policy [Limit the sync app upload rate to a percentage of throughput](use-group-policy#limit-the-sync-app-upload-rate-to-a-percentage-of-throughput) temporarily to minimize the network impact and then disable the policy once uploads are complete.

### Folders redirected to other organizations

If a user's Documents, Pictures, or Desktop folders are currently redirected to OneDrive in a different organization, redirecting to your organization’s OneDrive creates new Documents, Pictures, or Desktop folders and the user then sees an empty desktop. The user has to manually migrate files from the other organization’s OneDrive to OneDrive in your organization. We recommend that you disable the redirect to the other organization before redirecting to your organization if possible.

## About the Known Folder Move policies

OneDrive policies can be set using Group Policy, [Intune Windows 10 Administrative Templates](configure-sync-intune), or by configuring registry settings. For a full reference of available policies and their registry settings, see [Use OneDrive policies to control sync settings](use-group-policy).

The following policies control the Known Folder Move feature:

- [Prompt users to move Windows known folders to OneDrive](use-group-policy#prompt-users-to-move-windows-known-folders-to-onedrive)

    Use this setting to give the users a call to action to move their Windows known folders.

    ![Screenshot of the dialog that prompts users to back up their important folders.](sharepointonline/media/kfm-prompt-windows-1.png)

    If users dismiss the prompt, a reminder notification appears in the activity center until they move all known folders or an error occurs with the move, in which case the reminder notification can be dismissed.

    ![Screenshot of the notification that reminds users to protect their important folders.](sharepointonline/media/redirect-windows-kfm.png)

    Important

    We recommend deploying the prompt policy for existing devices only, and limiting the deployment to 5,000 devices a day and not exceeding 20,000 devices a week between macOS and Windows.
- [Silently move Windows known folders to OneDrive](use-group-policy#silently-move-windows-known-folders-to-onedrive)

    Use this setting to redirect and move known folders to OneDrive without any user interaction. Move all the folders or select the desired individual folders. After a folder is moved, the policy won't affect the folder again, even if the selection for the folder changes.

    You can choose to display a notification to users after their folders have been redirected.

    We also recommend using this setting together with [Prompt users to move Windows known folders to OneDrive.](use-group-policy#prompt-users-to-move-windows-known-folders-to-onedrive). If moving the known folders silently doesn't succeed, users are prompted to correct the error and continue.

    Important

    We recommend deploying the silent policy for existing devices and new devices while limiting the deployment of existing devices to 1,000 devices a day and not exceeding 4,000 devices a week between macOS and Windows.
- [Prevent users from turning off Known Folder Move](use-group-policy#prevent-users-from-redirecting-their-windows-known-folders-to-their-pc)

    Use this setting to require users to keep their known folders directed to OneDrive.

    Note

    Users can direct their known folders by opening OneDrive sync app settings, clicking the **Backup** tab, and then clicking **Manage backup**.
- [Prevent users from moving their Windows known folders to OneDrive](use-group-policy#prevent-users-from-moving-their-windows-known-folders-to-onedrive)

    Use this setting to prevent users from moving their known folders to any OneDrive account.

For info about using the OneDrive policies, see [Use Group Policy to control OneDrive sync app settings](use-group-policy).

## Transition from the Windows Folder Redirection Group Policy objects

The OneDrive Known Folder Move Group Policy objects doesn't work if you previously used [Windows Folder Redirection Group Policy objects](/en-us/windows-server/storage/folder-redirection/deploy-folder-redirection) to redirect the Documents, Pictures, or Desktop folders to a location other than OneDrive. The OneDrive Group Policy objects don't affect the Music and Videos folders, so you can keep them redirected with the Windows Group Policy objects. Follow these steps to switch to using the Known Folder Move Group Policy objects.

Note

Extending the scope of folders synced by OneDrive using Windows Folder Redirection Group Policy isn't supported.

- If folders have been redirected to OneDrive using Windows Folder Redirection Group Policy:

    1. Disable the Window Folder Redirection Group Policy and make sure to leave the folder and contents on OneDrive.
    2. Enable Known Folder Move Group Policy. Known folders remain in OneDrive.
- If folders have been redirected to a location on a local PC:

    1. Disable the Window Folder Redirection Group Policy and make sure to leave the folder and contents at the redirected location.
    2. Enable Known Folder Move Group Policy. Known folders move to OneDrive.
- If folders have been redirected to a network file share:

    1. [Use Migration Manager](/en-us/sharepointmigration/mm-get-started) to copy contents in the network file share location to a user's OneDrive, making sure that all contents go into the existing Documents, Pictures, or Desktop folders.

        Note

        If Migration Manager creates the Documents, Pictures, or Desktop folders, ensure that **Preserve file share permissions** isn't selected when performing the migration.
    2. Disable the Window Folder Redirection Group Policy and make sure to leave the folder and contents on the network file share.
    3. Enable Known Folder Move Group Policy. Known folders move to OneDrive and will merge with the existing Desktop, Documents, and Pictures folders, which contain all the file share content that you moved in the first step.