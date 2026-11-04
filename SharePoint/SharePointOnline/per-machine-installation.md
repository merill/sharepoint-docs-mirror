---
layout: Conceptual
title: Install the sync app per-machine (Windows) - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/per-machine-installation
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2024-11-05T00:00:00.0000000Z
ms.reviewer: garezni
ms.author: v-mactran
author: MachelleTranMSFT
manager: jtremper
audience: Admin
f1.keywords:
- CSH
ms.topic: install-set-up-deploy
ms.service: onedrive
ms.localizationpriority: medium
ms.custom:
- Adm_O365
- seo-marvel-apr2020
- onedrive-toc
search.appverid:
- MET150
- BCS160
ms.collection:
- Strat_OD_admin
- M365-collaboration
ms.assetid: 6891b561-a52d-4ade-9f39-b492285e2c9b
description: In this article, you learn how to install the OneDrive sync app once for a Windows PC with multiple users.
locale: en-us
document_id: d03e432e-17b8-cdf8-5cd1-158f19d493e4
document_version_independent_id: 699feed2-7123-c54d-8e01-4be30466f3e4
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/per-machine-installation.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: per-machine-installation
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/per-machine-installation.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: cc676573-2815-3573-0afa-fb172e129da6
---

# Install the sync app per-machine (Windows) - SharePoint in Microsoft 365 | Microsoft Learn

By default, the OneDrive sync app installs per-user, meaning that you need to install the app for each user on a machine. With the per-machine installation option, you need to install the app once on a PC. This option is especially useful for computers with multiple users and for when you don't want executable files running from a user profile.

Other than where the sync app is installed, the behavior is the same.

## Updates

The OneDrive sync app with the installation option of either per-machine or per-user both use the [same release notes](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0), support the same update rings, and update in the same time-frame. [More info about the sync app update process](sync-client-update-process).

If you're moving from per-user to per-machine, update settings aren't affected.

## Requirements

The per-machine installation's system requirements are the same as the per-user installation.

The per-machine installation option supports syncing OneDrive and SharePoint files in Microsoft 365 and in SharePoint Server 2019.

The per-machine installation option provides automatic transitioning from the [previous OneDrive sync app (Groove.exe)](transition-from-previous-sync-client).

## Deployment instructions

1. Download OneDriveSetup.exe.
2. Run "OneDriveSetup.exe /allusers" from a command prompt window (which results in a User Account Control prompt) or by using Microsoft Endpoint Configuration Manager.

- The per-user option installs OneDrive for each user account on a PC under the %localappdata% folder.
- The per-machine option installs OneDrive under the "Program Files (x86)" or "Program Files" directory (depending on the OS architecture).

When setup completes, OneDrive starts. If accounts were added on the computer, they're migrated automatically.

## Verify per-machine installation

To verify that you have the per-machine installation, you can use the following registry detection rule in Configuration Manager:

| Field | Value |
| --- | --- |
| Hive | HKEY\_LOCAL\_MACHINE |
| Key | SOFTWARE\Microsoft\OneDrive |
| Name | Version |
| 32-bit on 64-bit | TRUE |
| Type | REG\_SZ |
| Value | 19.043.0304.0007 |

## Revert back to the per-user sync app

We don't support automated migration from per-machine to per-user. To revert back after installing per-machine, uninstall the sync app and [install the latest released version](https://go.microsoft.com/fwlink/?linkid=844652) without the "/allusers" parameter.