---
layout: Conceptual
title: Silently configure user accounts - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/use-silent-account-configuration
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-04-05T00:00:00.0000000Z
ms.reviewer: wsproule
ms.author: v-mactran
author: MachelleTranMSFT
manager: jtremper
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.service: onedrive
ms.localizationpriority: medium
ms.collection:
- Strat_OD_admin
- M365-collaboration
search.appverid:
- ODB160
- MET150
ms.assetid: 64aa1f56-d7f6-4500-a408-1fde8fe6db36
ms.custom:
- seo-marvel-apr2020
- onedrive-toc
description: Learn how IT admins can enable silent account configuration when deploying the OneDrive sync app in an enterprise.
locale: en-us
document_id: 17aec87c-a56c-91c0-b2d5-5f9f11322c1e
document_version_independent_id: 439abe40-cdab-e480-0df9-30aa183ef521
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/use-silent-account-configuration.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: use-silent-account-configuration
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/use-silent-account-configuration.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
platformId: 8aee4b54-e0b4-b13c-2dbf-3b4b4bf5933e
---

# Silently configure user accounts - SharePoint in Microsoft 365 | Microsoft Learn

This article is for IT admins who would like to silently configure user accounts when deploying the new OneDrive sync app (OneDrive.exe) to managed Windows computers in their enterprise. This feature works for computers that are joined to Microsoft Entra ID.

If you enable this feature, OneDrive.exe attempts to silently (without user interaction) sign-in to the work or school user account that was used to sign into Windows (known as the Windows Primary Account). That Windows account must be a Microsoft Entra account or be linked to a Microsoft Entra account through a hybrid authentication configuration (see Prerequisites below).

Before OneDrive.exe begins syncing, it checks the available disk space. If syncing the user's entire OneDrive would cause the available space to drop below 1 GB or if the size exceeds the threshold you set (on devices that don't have Files On-Demand enabled), OneDrive prompts the user to choose folders to sync. For info about setting this threshold using Group Policy, see [Set the maximum size of a user's OneDrive that can download automatically](use-group-policy#set-the-maximum-size-of-a-users-onedrive-that-can-download-automatically).

When the user is configured in the sync app, if the same user account is syncing files with the previous OneDrive sync app (Groove.exe), the new sync app (OneDrive.exe) will attempt to take over syncing those files.

Important

We recommend enabling silent account configuration when you configure the sync app. [See all our recommendations for configuring the sync app](ideal-state-configuration)

## Prerequisites

Before you can enable silent account configuration, you need to join your devices to Microsoft Entra ID. You can join devices running Windows 10 or newer, and Windows Server 2016 or newer, directly to Microsoft Entra ID. To learn how, see [Join your work device to your organization's network](/en-us/azure/active-directory/user-help/user-help-join-device-on-network).

If you have an on-premises environment that uses Active Directory, you can enable [Microsoft Entra hybrid joined devices](/en-us/azure/active-directory/devices/hybrid-azuread-join-plan) to join devices on your domain to Microsoft Entra ID. Devices must be running one of the following operating systems:

- Windows 11
- Windows 10
- Windows Server 2019
- Windows Server 2016
- Windows Server 2012 R2

If you federate your on-premises Active Directory with Microsoft Entra ID, you must use AD FS to enable this feature. For info about using Microsoft Entra Connect, see [Getting started with Microsoft Entra Connect using express settings](/en-us/azure/active-directory/hybrid/how-to-connect-install-custom).

Note

For more info, see [How to configure Microsoft Entra hybrid joined devices](/en-us/azure/active-directory/devices/hybrid-azuread-join-plan). To check the join status and fix problems, see [Troubleshoot Microsoft Entra hybrid joined devices](/en-us/azure/active-directory/devices/troubleshoot-hybrid-join-windows-current).

## Enable silent configuration

If the computers on your network are joined to Active Directory on-premises, you can use domain group policy to configure silent account configuration.

Using Group Policy:

1. Enable silent account configuration. For info, see [Silently sign in users to the OneDrive sync app with their Windows credentials](use-group-policy#silently-sign-in-users-to-the-onedrive-sync-app-with-their-windows-credentials).
2. Optionally, specify the maximum OneDrive size that downloads automatically in silent configuration. For info, see [Set the maximum size of a user's OneDrive that can download automatically](use-group-policy#set-the-maximum-size-of-a-users-onedrive-that-can-download-automatically). If you enable Files On-Demand, OneDrive ignores the maximum size value.
3. Optionally, set the default location for the OneDrive folder. For info, see [Set the default location for the OneDrive folder](use-group-policy#set-the-default-location-for-the-onedrive-folder).

Tip

See the [Verify SilentAccountConfig](use-silent-account-configuration#VerifySilentAccountConfig) section below to verify and troubleshoot your configuration.

Note

Silent account configuration won't work on devices for users who require multifactor authentication. Select third-party identity providers (IdPs) are supported, but there are caveats. For more information, make sure to check out the [Microsoft Entra federation compatibility list](/en-us/azure/active-directory/hybrid/how-to-connect-fed-compatibility).

Configuration with Alternate IDs is only supported within Microsoft 365 Government environments.

If the computers on your network aren't connected to Active Directory on-premises, but only to Microsoft Entra ID, we recommend using Intune and a Microsoft PowerShell script to set the registry keys required to enable silent account configuration. Be sure you have [automatic enrollment set up for Windows 10 or newer devices](/en-us/mem/intune/enrollment/windows-enroll?formCode=MG0AV3).

Using a script:

```PowerShell
$HKLMregistryPath = 'HKLM:\SOFTWARE\Policies\Microsoft\OneDrive'##Path to HKLM keys
$DiskSizeregistryPath = 'HKLM:\SOFTWARE\Policies\Microsoft\OneDrive\DiskSpaceCheckThresholdMB'##Path to max disk size key
$TenantGUID = 'xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx'

if(!(Test-Path $HKLMregistryPath)){New-Item -Path $HKLMregistryPath -Force}
if(!(Test-Path $DiskSizeregistryPath)){New-Item -Path $DiskSizeregistryPath -Force}

New-ItemProperty -Path $HKLMregistryPath -Name 'SilentAccountConfig' -Value '1' -PropertyType DWORD -Force | Out-Null ##Enable silent account configuration
New-ItemProperty -Path $DiskSizeregistryPath -Name $TenantGUID -Value '102400' -PropertyType DWORD -Force | Out-Null ##Set max OneDrive threshold before prompting
```

## Windows Image Prep requirements

SilentAccountConfig creates a SilentBusinessConfigCompleted registry entry once SilentAccountConfig has successfully provisioned the user in OneDrive.exe. This prevents SilentAccountConfig from reprovisioning the user in OneDrive.exe if the user manually stops syncing.

If SilentAccountConfig has successfully completed on a computer you're going to use to build a Windows deployment image (for example, SysPrep), you need to ensure this registry key and also ClientEverSignedIn and PersonalUnlinkedTimeStamp registry keys are removed before you prepare your image. You can do so by running the following commands:

```console
reg delete HKCU\Software\Microsoft\OneDrive /v SilentBusinessConfigCompleted /f
reg delete HKCU\Software\Microsoft\OneDrive /v ClientEverSignedIn /f
reg delete HKCU\Software\Microsoft\OneDrive /v PersonalUnlinkedTimeStamp /f
reg delete HKCU\Software\Microsoft\OneDrive /v OneAuthUnrecoverableTimestamp /f
```

## Verify SilentAccountConfig

### Instructions for SharePoint in Microsoft 365

1. Unlink all preexisting Business instances in OneDrive.
2. Clear the registry of any previous successful Silent Business Config runs:

```console
reg delete HKCU\Software\Microsoft\OneDrive /v SilentBusinessConfigCompleted /f
reg delete HKCU\Software\Microsoft\OneDrive /v ClientEverSignedIn /f
reg delete HKCU\Software\Microsoft\OneDrive /v PersonalUnlinkedTimeStamp /f
reg delete HKCU\Software\Microsoft\OneDrive /v OneAuthUnrecoverableTimestamp /f
```

1. Set the Silent Config policy registry entry (must be run from an administrator CMD window):

    ```console
    reg add HKLM\SOFTWARE\Policies\Microsoft\OneDrive /v SilentAccountConfig /t REG_DWORD /d 0x1 /f
    ```
2. Sign out of Windows (Ctrl+Alt+Delete Sign out).
3. Sign in to Windows.
4. Shortly you should see a blue cloud icon in the notification area of the taskbar. Selecting the icon should show the activity center pop-up showing ongoing/recent activity from the first sync. If so, SilentAccountConfig has worked correctly.
5. If instead you see the "Set up OneDrive" screen, SilentAccountConfig couldn't silently sign in or failed for another reason. Verify you completed these steps correctly by repeating them again. Follow the [Verify Single Sign On (SSO)](use-silent-account-configuration#VerifySSO) steps later in this article to confirm that SSO isn't a problem. Gather sync app logs to send to the engineering team for further help.

### Instructions for SharePoint Server 2019 or newer

1. Ensure you can manually get the OneDrive sync app to sync content with your on-premises SharePoint Server, 2019 or newer, before proceeding. See [Configure sync app for syncing with SharePoint Server](/en-us/sharepoint/install/configure-syncing-with-the-onedrive-sync-app) for details.
2. Set the SharePointOnPremPrioritization reg key value to 1 (this ensures that your on premises SharePoint Server takes precedence over Microsoft 365 SharePoint cloud, delete the registry key to revert to SharePoint in Microsoft 365):

    ```console
    reg add HKLM\SOFTWARE\Policies\Microsoft\OneDrive /v SharePointOnPremPrioritization /t REG_DWORD /d 0x1 /f
    ```
3. Follow steps 1 through 6 in the previous procedure for SharePoint in Microsoft 365.
4. If instead, you see the "Set up OneDrive" screen, SilentAccountConfig was unable to silently sign in or failed for another reason. Verify you've completed these steps correctly by repeating them again. Gather sync app logs to send to the engineering team for further help.

### To prevent Silent Business Config

```console
reg delete HKLM\SOFTWARE\Policies\Microsoft\OneDrive /v SilentAccountConfig /f
```

## Verify that Single Sign On (SSO) is working

The most common reason for SilentAccountConfig to fail is the credentials aren't available to OneDrive.exe without user interaction. Follow these steps to determine if this is a problem in your case.

If you have a computer you think should work with SilentAccountConfig, you can manually verify that SSO is working correctly to ensure that the environment is configured correctly.

1. Ensure OneAuth is enabled

    ```console
    reg delete HKCU\Software\Microsoft\OneDrive /v OneAuthUnrecoverableTimestamp /f
    ```
2. Shut down any running OneDrive.exe processes (verify in the Task Manager Details tab - Ctrl+Shift+Esc).
3. Start menu - OneDrive, you should see the **Set up OneDrive** screen (if not unlink/stop syncing any business accounts and start over).
4. Enter the same email address that the user used to sign into Windows (try alias@domain and domain\alias forms).
5. Select the **Sign in** button.
6. The dialog should switch to a "signing in" page with a spinning icon for a few seconds. It should then continue to the next part of the wizard without asking for a password.
7. If a password prompt doesn't appear, your auth environment is properly configured and SilentAccountConfig should work for your users.
8. If you do see a password prompt, the environment isn't configured properly for silent sign-on. This could be due to a problem with how the computer is domain joined (for example, a trust relationship problem), a problem with ADFS configuration, a Microsoft Entra Conditional Access policy requiring user interaction, you didn't provide the same user email address as the one used to sign into Windows, or some other reason. You need to resolve whatever is blocking silent sign-on before SilentAccountConfig works for you.
9. Remove any OneAuth failure timestamp

```console
reg query HKCU\Software\Microsoft\OneDrive /v OneAuthUnrecoverableTimestamp
reg delete HKCU\Software\Microsoft\OneDrive /v OneAuthUnrecoverableTimestamp /f
```