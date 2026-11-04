---
layout: Conceptual
title: Sync in SharePoint and OneDrive - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/sharepoint-sync
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-05-29T00:00:00.0000000Z
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: sync
ms.collection:
- M365-collaboration
- Tier2
ms.custom:
- seo-marvel-apr2020
ms.localizationpriority: medium
search.appverid:
- MET150
description: In this article, you learn about syncing SharePoint and OneDrive files using the OneDrive sync app for Windows and Mac.
locale: en-us
document_id: 367f3b91-1252-7bce-fd1e-21ceb1ae12f3
document_version_independent_id: 66e3f10a-0231-e7e0-0659-0be66eaf13fa
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/sharepoint-sync.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: sharepoint-sync
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/sharepoint-sync.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 3b89c03e-13f7-007c-d2f2-7b17224f02bd
---

# Sync in SharePoint and OneDrive - SharePoint in Microsoft 365 | Microsoft Learn

When users install the OneDrive sync app for Windows or Mac, and sync the files on a team site, they can work with the files in File Explorer or Finder. They can also easily save files to the team site from the programs they use.

If the user adds, changes, or deletes files and folders on the site, the changes also apply to the files and folders of the user's computer and vice versa.

To upload files to the team site, users can copy or move them to the site in File Explorer or Finder. They can also use File Explorer or Finder to easily organize the document library by creating new folders, and moving and renaming files and folders. All these changes sync automatically.

Windows 10 devices come with the OneDrive sync app installed. Office 2016 and later installations also have the sync app installed.

## SharePoint file sync and OneDrive shortcuts

Users have two options when syncing files in SharePoint libraries and Teams. They can

- [Add shortcuts to libraries and folders to their OneDrive](https://support.microsoft.com/office/d66b1347-99b7-4470-9360-ffc048d35a33).
- [Use the Sync button in the document library](https://support.microsoft.com/office/6de9ede8-5b6e-4503-80b2-6190f3354a88).

## Deciding between OneDrive sync options

Both OneDrive shortcuts and OneDrive Sync options allow essentially the same thing-users can access files on their local computer in Explorer or Finder.

However, adding OneDrive shortcuts allows content to be accessed on all devices, whereas sync is related to a specific device. Additionally, OneDrive shortcuts offer improved performance versus using the sync button.

We recommend using OneDrive shortcuts as the more versatile option.

### Turn off OneDrive sync for SharePoint libraries

You can turn off OneDrive sync from all the SharePoint libraries in your organization with SharePoint Online Management Shell.

To turn off OneDrive sync from all the SharePoint libraries in your organization:

1. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    Note

    If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell."
2. Connect to SharePoint as a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online). by using this [Set-SPOTenant](/en-us/powershell/module/microsoft.online.sharepoint.powershell/set-spotenant) PowerShell cmdlet to remove the OneDrive sync button:
3. Run the following cmdlets:

    ```PowerShell
    Set-SPOTenant -HideSyncButtonOnTeamSite $true
    ```

Removing the sync button blocks new syncs from being started but doesn't affect existing syncs.