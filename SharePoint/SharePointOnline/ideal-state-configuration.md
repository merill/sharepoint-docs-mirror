---
layout: Conceptual
title: Recommended sync app configuration - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/ideal-state-configuration
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-04-05T00:00:00.0000000Z
ms.reviewer: kangan
ms.author: cagreen
author: cartergreen
manager: gacarini
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
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
ms.assetid: b664e743-ae8b-4a93-aefd-1b20c584a93a
description: View our recommendations for deploying and configuring the OneDrive sync app.
locale: en-us
document_id: 95aa4d57-f10c-6b32-bc4c-b56357a69c1f
document_version_independent_id: 10312475-8e1b-2602-ac3f-d3d470b6b1a4
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/ideal-state-configuration.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: ideal-state-configuration
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/ideal-state-configuration.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: eec68080-031a-c405-c694-e31ea92aef1a
---

# Recommended sync app configuration - SharePoint in Microsoft 365 | Microsoft Learn

For the best performance, reliability, and user experience, follow these "ideal state" recommendations when you configure the OneDrive sync app.

## Updates and rings

- **Allow access to oneclient.sfx.ms and g.live.com**. Computers must be able to reach these URLs to apply updates and bug fixes, and enable or disable features. Updates are installed automatically; so, you don't need to package and deploy them. Because OneDrive runs in the background, updates are also installed silently and don't affect users.
- **Use the Insiders and Production rings**. Select several people in your IT department as early adopters to join the Insiders ring and receive features early. Leave everyone else in the organization on the default Production ring to ensure they receive bug fixes and new features in a timely fashion. This recommendation applies even if you are on the Semi-Annual Enterprise Channel for Windows and Office. For more information about the rings, see [Sync app update process](sync-client-update-process). To set the update ring on Windows, see [Set the sync app update ring](use-group-policy#set-the-sync-app-update-ring). To set it on Mac, see [Deploy and configure the new OneDrive sync app for Mac](deploy-and-configure-on-macos#tier).

## Windows Notification Service

- **Make sure connection to the service is enabled**. Work with your network team to ensure proxies:

    - Allow network traffic to bypass \*.wns.windows.com
    - Avoid HTTPS decryption for \*.wns.windows.com

        This requirement applies to both Windows and Mac. [See the complete list of required URL and IP address ranges](/en-us/office365/enterprise/urls-and-ip-address-ranges#sharepoint-online-and-onedrive-for-business).

## Files On-Demand and Storage Sense

- **Keep Files On-Demand enabled**. OneDrive Files On-Demand helps users access all their files (individual or shared) without having to download them and use storage space. This setting is on by default for Windows 10 and Mac. To check this setting for Windows, see [Use OneDrive Files On-Demand](use-group-policy#use-onedrive-files-on-demand). To check it for Mac, see [Deploy and configure the new OneDrive sync app for Mac](deploy-and-configure-on-macos).
- **Use Storage Sense policies on PCs**. These policies let you automatically clean up "locally available" files users haven't explicitly pinned as "always available." For additional information, see [More info about Storage policies](/en-us/windows/client-management/mdm/policy-csp-storage).

## Silent account configuration

- **Silently configure user accounts on PCs**. When you enable the silent account configuration policy, users are signed in automatically; so, they don't need to open OneDrive or enter their password. For more information, see [Use silent account configuration](use-silent-account-configuration).

## Application start-up

- **Start OneDrive automatically when signing in to Windows**. When you enable the autostart configuration policy, OneDrive will automatically start every time users sign in to Windows. For more information, see [Start OneDrive automatically when signing in to Windows](use-group-policy#start-onedrive-automatically-when-signing-in-to-windows).

## Known Folder Move

Windows users are familiar and comfortable with saving files to their desktop, documents, and pictures folders from years of developing it as a habit. When you redirect and move these folders to OneDrive, users can continue saving files to these locations, and they're backed up and available from any device. For more information, see [Redirect known folders](redirect-known-folders).

- **On new PCs, enable the silent policy**. [Silently move Windows known folders to OneDrive](use-group-policy#silently-move-windows-known-folders-to-onedrive)
- **On existing PCs, gradually enable the prompt and/or silent policy**. [About the Known Folder Move Group Policy objects](redirect-known-folders#about-the-known-folder-move-policies)

## Office integration

- **Keep Office file collaboration enabled** Office uses differential sync to sync only changes instead of the entire file each time. This makes sync faster and reduces network bandwidth. For information about this setting for Mac, see [Deploy and configure the new OneDrive sync app for Mac](deploy-and-configure-on-macos).

    Note

    As of May 2025, the coauthoring and in-app sharing of Office files setting is enabled by default for all tenants. If this setting is disabled, Office file collaboration is turned off, and when file conflicts occur, both versions of the file are kept. If the setting isn't previously disabled by organizations, end users shouldn't experience any changes.

## Offline mode

- **Keep offline mode enabled** With offline mode, users can work with OneDrive in the web in low or no internet situations. This setting is on by default on Windows and Mac. For more info, see [Prevent users from getting silently signed in to offline experiences on the web](lists-sync-policies#prevent-users-from-getting-silently-signed-in-to-offline-experiences-on-the-web), [Prevent users at your organization from enabling offline mode in OneDrive on the web](use-group-policy#prevent-users-at-your-organization-from-enabling-offline-mode-in-onedrive-on-the-web), and [Prevent users at your organization from enabling offline mode in OneDrive on the web for libraries and folders that are shared from other organizations](use-group-policy#prevent-users-at-your-organization-from-enabling-offline-mode-in-onedrive-on-the-web-for-libraries-and-folders-that-are-shared-from-other-organizations). For info about this setting for Mac, see [DisableOfflineMode](deploy-and-configure-on-macos#disableofflinemode) and [DisableOfflineModeForExternalLibraries](deploy-and-configure-on-macos#disableofflinemodeforexternallibraries).

## Shortcuts to shared folders

Users have two options when syncing files in SharePoint libraries and Teams. They can

- [Add shortcuts to libraries and folders to their OneDrive](https://support.microsoft.com/office/d66b1347-99b7-4470-9360-ffc048d35a33).
- [Use the Sync button in the document library](https://support.microsoft.com/office/6de9ede8-5b6e-4503-80b2-6190f3354a88).

It's recommended to use shortcuts instead of using the Sync button. Shortcuts are more performant because rather than syncing the entire library, only the specific folder is synced. Additionally, because the shortcuts are added to a user's OneDrive rather than to the device, it's easier to access content across all devices.

If you're an admin and want to hide the Sync button in document libraries, use the following PowerShell command:

Set-SPOTenant -HideSyncButtonOnTeamSite $true

## Sync reports

The [OneDrive sync reports in the Apps Admin Center](sync-health) provides you with sync health reports for tracking relevant health issues and advisories, checking the sync status and app version of individual devices, and monitoring Known Folder Move roll out. You must enable this setting on the devices from which you want to get reports. For more info, see [Enable sync health reporting for OneDrive](use-group-policy#enable-sync-health-reporting-for-onedrive). For info about this setting for Mac, see [Deploy and configure the new OneDrive sync app for Mac](deploy-and-configure-on-macos).