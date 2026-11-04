---
layout: Conceptual
title: Use the sync app on virtual desktops - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/sync-vdi-support
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-08-10T00:00:00.0000000Z
ms.reviewer: garezni
ms.author: ishanikumar
author: ishanikumar
manager: jtremper
audience: Admin
f1.keywords:
- CSH
ms.topic: how-to
ms.service: onedrive
ms.localizationpriority: medium
ms.custom:
- Adm_O365
- onedrive-toc
search.appverid:
- MET150
- BCS160
ms.collection:
- Strat_OD_admin
- M365-collaboration
description: Learn about the OneDrive sync app support for desktop virtualization.
locale: en-us
document_id: 5e538936-5a60-99cb-4ba0-0ff1f79d0d39
document_version_independent_id: 855d9555-fe75-f7d6-1c33-bb8e2f9ae7d2
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/sync-vdi-support.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: sync-vdi-support
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/sync-vdi-support.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57ef615f-6bf1-4904-b6dc-96bb1d32c7e9
- https://authoring-docs-microsoft.poolparty.biz/devrel/7814ca69-56be-4667-8a46-86327796c328
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1aea571c-6f95-42f8-b87e-c4d3aaf4bd7d
- https://authoring-docs-microsoft.poolparty.biz/devrel/f15dfcd0-2664-48ba-bb88-f1f86eadbfd1
platformId: 85eee39b-f045-a76f-ec77-9badef8917ae
---

# Use the sync app on virtual desktops - SharePoint in Microsoft 365 | Microsoft Learn

For all [supported operating systems](https://support.office.com/article/cc0cb2b8-f446-445c-9b52-d3c2627d681e), the OneDrive sync app supports:

- Virtual desktops that persist between sessions.
- Non-persistent virtual desktops that use [Azure Virtual Desktop](/en-us/azure/virtual-desktop).
- Non-persistent virtual desktops that have [FSLogix Apps](/en-us/fslogix/configure-profile-container-tutorial) or [FSLogix Office Container](/en-us/fslogix/configure-office-container-tutorial), and a Microsoft 365 subscription for all of the following operating systems:
    - Windows 11, 32-bit or 64-bit (supports VMDK/Virtual Machine Disk files)
    - Windows Server 2025 or newer (supports VHDX/Virtual Hard Disk)

Note

Check the latest versions at these links: [OneDrive](https://support.microsoft.com/en-us/office/onedrive-release-notes-845dcf18-f921-435e-bf28-4e24b95e5fc0), [FSLogix App](/en-us/fslogix/overview-release-notes) Using the OneDrive sync app with non-persistent environments requires that you [install the sync app per machine](per-machine-installation). For Windows Server, the [SMB network file sharing protocol](/en-us/windows-server/storage/file-server/file-server-smb-overview) is also required. The OneDrive sync app is supported in a remote app scenario hosted as a Citrix Virtual App. The OneDrive sync app with FSLogix doesn't support running multiple instances of the same container simultaneously.

## Set up OneDrive in Citrix Virtual Apps

This section describes how to enable and use OneDrive in Citrix Virtual Apps.

### Prerequisites

To enable OneDrive in Citrix Virtual Apps, you must have the following versions of Windows and Citrix Virtual Apps and Desktops (CVAD):

**Windows**:

- Windows 11
- Windows Server 2025

**Citrix**:

- CVAD 7 2203 LTSR/Long Term Service Release CU1 or later.
- VDA/Virtual Delivery Agent 2212 enables Shellbridge by default. All earlier versions require Shellbridge to be enabled manually.
- To enable this feature, On 2203 LTSR TS VDA (2019 Server, 2022 Server, Windows 10 RDSH/Remote Desktop Session Host, or Windows 11 RDSH/Remote Desktop Service Host) add the following registry details:

    - `HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\Citrix Virtual Desktop Agent`
    - `Name: Shellbridge`
    - `Type: REG_DWORD`
    - `Value: 1`

To ensure that the feature is correctly enabled, open a command window (cmd.exe) and run `start ms-settings:printers`. If the feature is enabled, the printer setting window is displayed.

**We recommend adding OneDrive.exe to `LogoffCheckSysModules`**.

- `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Citrix\wfshell\TWI`
- `Value Name:LogoffCheckSysModules`
- `Type:REG_SZ`
- `String:OneDrive.exe, Microsoft.Sharepoint.exe`

Important

[FSLogix](/en-us/fslogix/how-to-install-fslogix) must be used in conjunction with Citrix Virtual Apps for OneDrive to be supported.

### How to set up OneDrive

1. Install OneDrive Sync app per machine. See [Install the sync app per-machine](per-machine-installation).
2. Install the latest version of FSLogix. See [Install FSLogix Applications](/en-us/fslogix/how-to-install-fslogix).

    Note

    All non-persistent VDI environments require the latest version of FSLogix. Ensure you install the latest version. See [OneDrive sync error FSLogix_unsupported_environment on VMs](/en-us/sharepoint/troubleshoot/sync/fslogix-unsupported-environment-sync-error-vm).
3. Add OneDrive to `HKLM\Software\Microsoft\Windows\CurrentVersion\` by using the following command:

    `REG ADD HKLM\Software\Microsoft\Windows\CurrentVersion\Run /v OneDrive /t REG_SZ /d "\"C:\Program Files\Microsoft OneDrive\OneDrive.exe\" /background"`
4. Silently configure user accounts. See [Silently configure user accounts](use-silent-account-configuration).

    Note

    Silent sign-in should work if your machine is connected to Microsoft Entra ID. Make sure to turn off this setting if your computer isn't Microsoft Entra joined.

## Set up OneDrive in Omnissa Horizon Virtual Apps

This section describes how to enable and use OneDrive in Omnissa Horizon Virtual Apps.

### Prerequisites

- Omnissa Horizon
- Windows

    - Windows 10 and Windows 11 Guest Operating Systems for Horizon Agent and Remote Experience, for Omnissa Horizon 8.x (2006 and later) (78714). For more information, see [this article](https://kb.omnissa.com/s/article/78714).
    - Non-Windows 10 and 11 Guest Operating Systems for Horizon 8 Agent (78715). For more information, see [this article](https://kb.omnissa.com/s/article/78715).
- FSLogix
- Omnissa Dynamic Environment Manager (DEM) or a product which enables user environment personalization. The system on which you plan to install DEM must meet certain software requirements. For more information, see [this article](https://docs.omnissa.com/bundle/DEMInstallConfigGuideV2406/page/SoftwareRequirements.html).

### Registry Keys

The following registry keys help to roam the user environment on multiple nodes in the virtual application farm. Omnissa Dynamic Environment Manager or a similar user environment management tool can be used to deploy the registry keys to all farm servers.

- [IncludeRegistryTrees]

    - `HKCU\Software\Microsoft\Office`
    - `HKCU\Software\Microsoft\Internet Explorer`
    - `HKCU\Software\Microsoft\Windows\CurrentVersion\Internet Settings`
    - `HKCU\Software\Microsoft\Windows\CurrentVersion\Shell Extensions\Cached`
    - `HKCU\Software\Microsoft\OneDrive`
- [IncludeFolderTrees]

    - `<Appdata>\Microsoft\Windows\Recent`
    - `<Appdata>\Microsoft\crypto`
    - `<Appdata>\SystemCertificates`
    - `<LocalAppdata>\Microsoft\IdentityCache`
    - `<LocalAppdata>\Microsoft\Internet Explorer`
    - `<LocalAppdata>\Microsoft\Windows\INetCache`

### Configure Omnissa Dynamic Environment Manager with Horizon Apps

1. Launch the Omnissa Dynamic Environment Manager management console, select **Create Config File**, and select **Use an Application Template**.
2. Select the application template (Microsoft Office 2016 and 2019, or Microsoft 365), select **OneDrive for Business**, and click **Next**.
3. Provide the file name and description and select **Finish**.
4. Add the previously listed **required registry keys** to **Import / Export** settings.

### Configure FSLogix with Omnissa Dynamic Environment Manager

Configuring FSLogix in combination with Dynamic Environment Manager will help with store OneDrive cache and the save location for Microsoft and non-Microsoft applications.

For more info on how to configure FSLogix Office Container (ODFC) on all Horizon Virtual App farm servers, refer to [this article](/en-us/fslogix/tutorial-configure-odfc-containers).

- Install the per-machine version of the OneDrive sync app on all the Horizon Virtual App farm hosts.
- Create the following entries in each Horizon farm servers. You can use DEM or similar user environment management tool to deploy the registry to all virtual app farm servers.

    - Key: `HKLM\Software\Microsoft\Windows\CurrentVersion\Run`
    - Type: `REG_SZ`
    - Name: `OneDrive`
    - Data: `"C:\Program Files\Microsoft OneDrive\OneDrive.exe"/background`
    - Key: `HKLM\Software\Policies\Microsoft\OneDrive`
    - Type: `REG_DWORD`
    - Name: `SilentAccountconfig`
    - Data: `1`

Note

Sometimes the silent login will take several seconds. If the first attempt fails, a second attempt might be required.