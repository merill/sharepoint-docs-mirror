---
layout: Conceptual
title: Control Groove.exe installation when deploying Office using Click-to-Run - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/exclude-or-uninstall-previous-sync-client
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2024-09-18T00:00:00.0000000Z
ms.reviewer: kafeaver
ms.author: v-mactran
author: MachelleTranMSFT
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: install-set-up-deploy
ms.service: onedrive
ms.localizationpriority: medium
search.appverid:
- ODB160
- OFF160
- ODB150
- MET150
ms.collection:
- Strat_OD_admin
- M365-collaboration
ms.custom: onedrive-toc
ms.assetid: 3eff17b9-c709-462f-946c-17719af68aca
description: Learn how the previous OneDrive for Business sync app (Groove.exe) is excluded or uninstalled with Office Click-to-Run installations.
locale: en-us
document_id: e19f89b3-b4c3-ddd5-02e6-ead8ed38f959
document_version_independent_id: 96bf8858-11de-0057-b635-784986990eec
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/exclude-or-uninstall-previous-sync-client.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: exclude-or-uninstall-previous-sync-client
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/exclude-or-uninstall-previous-sync-client.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/dc29fde7-b949-4135-9273-ad8e4a53d516
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/25d6050c-71f5-4b48-8bc7-575debd6530a
platformId: 02e26875-acae-7956-a804-591512b65ab2
---

# Control Groove.exe installation when deploying Office using Click-to-Run - SharePoint in Microsoft 365 | Microsoft Learn

Important

Support for the previous OneDrive for Business sync app (Groove.exe) ended on January 11, 2021. As of February 1, 2021, users can longer sync OneDrive or SharePoint files in Microsoft 365 by using Groove.exe. Groove.exe will continue to work only for files in SharePoint Server.

Starting in October 2017, we changed how the previous OneDrive for Business sync app installs for enterprise customers who deploy Office 2013 or 2016 by using Click-to-Run.

- The previous sync app (Groove.exe) is no longer installed by default with Office 2016 Click-to-Run. If your organization provides an Office deployment configuration file to Setup.exe, you need to update your file to exclude Groove.exe from the install.
- When not in use or running, the previous sync app (Groove.exe) is uninstalled, unless: (a) Groove.exe is already configured to sync one or more SharePoint or SharePoint Server libraries or (b) a "PreventUninstall" registry key is present on the computer.

These changes don't affect your organization if you're already using the new OneDrive sync app (OneDrive.exe) to sync OneDrive and SharePoint files. These changes also don't affect your organization if you deploy Office using the traditional Windows Installer-based (MSI) method.

Note

The new OneDrive sync app (OneDrive.exe) is the recommended option for SharePoint Server 2019 customers. However, the previous sync app (Groove.exe) is still used and supported for earlier versions of SharePoint Server. [Which version of OneDrive am I using?](https://support.office.com/article/19246eae-8a51-490a-8d97-a645c151f2ba)

## Ensure Groove.exe is no longer installed

If your organization provides an Office deployment configuration file to Setup.exe, add this to your config file to exclude Groove in your deployment:

`<Product ID="O365ProPlusRetail" > <Language ID="en-us" /> <ExcludeApp ID="Groove" /> </Product>`

For more info about configuration options, see [Configuration options for the Office Deployment Tool](/en-us/deployoffice/office-deployment-tool-configuration-options).

To override the default behavior and make sure the previous OneDrive for Business sync app installs and stays installed, you must provide a config file that doesn't exclude Groove.exe. Also, you must set the "PreventUninstall" registry key on all computers where you need Groove.exe installed, so that the process doesn't uninstall Groove.exe.

## Uninstall Groove.exe when not in use

On Office upgrade, the installer runs on each computer to detect whether Groove.exe is currently in use or the "PreventUninstall" registry key is set. If either Groove.exe is in use or the registry key is set, Groove.exe is left in place. Otherwise, if Groove.exe isn't in use and the registry key isn't set, Groove.exe gets uninstalled automatically on that computer.

### Prevent uninstallation (registry key)

[HKLM\SOFTWARE\Microsoft\Office\Groove] "PreventUninstall"=dword:00000001

## Timeline

The following table shows more detail about which Office installations were affected by these changes and when.

| **Office version** | **Groove.exe is no longer installed by default** | **Groove.exe is uninstalled on next update if not in use for 30 days** |
| --- | --- | --- |
| MSI (all versions) | Not applicable | Not applicable |
| Office 2013 Click-to-Run | Not applicable | Not applicable |
| Office 2016 Click-to-Run - Office Insider | Sept. 2017 - Version 1710 (Build 8530.1000) | Sept. 2017 - Version 1710 (Build 8530.1000) |
| Office 2016 Click-to-Run - Monthly Channel | Oct. 2017 - Version 1709 (Build 8528.2139) | Oct. 2017 - Version 1709 (Build 8528.2139) |
| Office 2016 Click-to-Run - Semi-Annual Enterprise Channel (Preview) | Sept. 2018 - Version 1808 (Build 10730.20102) | Sept. 2018 - Version 1808 (Build 10730.20102) |
| Office 2016 Click-to-Run - Semi-Annual Enterprise Channel | Jan. 2019 - Version 1808 (Build 10730.20264) | Jan. 2019 - Version 1808 (Build 10730.20264) |

For more info about Office channels, see [Overview of update channels for Microsoft 365 Apps for enterprise](/en-us/deployoffice/overview-update-channels).