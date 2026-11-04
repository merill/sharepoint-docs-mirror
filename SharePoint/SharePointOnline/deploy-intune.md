---
layout: Conceptual
title: Deploy OneDrive apps using Intune - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/deploy-intune
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2024-06-04T00:00:00.0000000Z
ms.reviewer: scbree
ms.author: v-mactran
author: MachelleTranMSFT
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: install-set-up-deploy
ms.service: onedrive
ms.localizationpriority: medium
ms.collection:
- Strat_OD_admin
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- onedrive-toc
search.appverid:
- MET150
- ODB160
- MOE150
- MED150
- MBS150
- ODB150
ms.assetid: 3f3a511c-30c6-404a-98bf-76f95c519668
description: In this article, you'll learn how you can use Intune to deploy the OneDrive mobile app to iOS and Android devices and the OneDrive sync app to Windows.
locale: en-us
document_id: f093c7dc-9950-ffc5-def6-990133ca13d2
document_version_independent_id: ee99c1ed-ed88-f3b8-f5ea-bd09bf64c8f2
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/deploy-intune.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: deploy-intune
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/deploy-intune.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: c3e138fc-f322-9bb8-b3fa-be4446e28bff
---

# Deploy OneDrive apps using Intune - SharePoint in Microsoft 365 | Microsoft Learn

As an [Intune Administrator](/en-us/mem/intune/fundamentals/role-based-access-control), you can use Intune to deploy OneDrive apps. Before you begin deploying, make sure you review the planning information and deployment options in the [Plan file sync for SharePoint and OneDrive in Microsoft 365](plan-file-sync).

To deploy apps in Intune, you use the [Microsoft Intune admin center](https://intune.microsoft.com/?ref=AdminCenter#blade/Microsoft_Intune_DeviceSettings/AppsMenu/allApps).

## Deploy the OneDrive sync app to Windows devices

OneDrive is preinstalled on Windows 10 and later. You can choose to switch to [per-machine installation](per-machine-installation).

For info about configuring sync app settings using Intune, see [Configure settings with Intune](configure-sync-intune).

## Deploy the OneDrive app to iOS devices

There are two options for deploying the OneDrive app on iOS:

- **Apple VPP.** Using this option and deploying with device licensing, the app is installed without user interaction. For more information, see [How to manage iOS and macOS apps purchased through Apple Business Manager with Microsoft Intune](/en-us/mem/intune/apps/vpp-apps-ios).
- **iOS Store app.** Using this option doesn't require any connection to Apple Business Manager, however users will be prompted to enter their Apple ID password to install the app. For more information, see [Add iOS store apps to Microsoft Intune](/en-us/mem/intune/apps/store-apps-ios).

## Deploy the OneDrive app to Android devices

There are two options for deploying the OneDrive app on Android:

- [Add Managed Google Play apps to Android Enterprise devices with Intune](/en-us/mem/intune/apps/apps-add-android-for-work)
- [Add Android store apps to Microsoft Intune](/en-us/mem/intune/apps/store-apps-android).
    - Use **https://play.google.com/store/apps/details?id=com.microsoft.skydrive** as the Appstore URL.

## Deploy the OneDrive app to macOS devices

There are two options for deploying the OneDrive app using Intune:

- **Microsoft 365 Apps.** You can deploy Microsoft 365 apps including OneDrive with Intune. For more information, see [Assign Microsoft 365 to macOS devices with Microsoft Intune](/en-us/mem/intune/apps/apps-add-office365-macos).
- **Deploy a standalone PKG**
    1. Download the [app package (.pkg)](deploy-and-configure-on-macos)
    2. Deploy using [Add an unmanaged macOS PKG app to Microsoft Intune](/en-us/mem/intune/apps/macos-unmanaged-pkg)

For more information about OneDrive on macOS, see [Deploy and Configure OneDrive on macOS](deploy-and-configure-on-macos).