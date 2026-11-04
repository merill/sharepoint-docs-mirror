---
layout: Conceptual
title: Enable File Requests in SharePoint or OneDrive - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/enable-file-requests
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-05-07T00:00:00.0000000Z
ms.reviewer: srice
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: onedrive
ms.localizationpriority: medium
ms.collection:
- Strat_OD_admin
- M365-collaboration
ms.custom:
- admindeeplinkSPO
- onedrive-toc
search.appverid:
- SPO160
- MET150
ms.assetid: 
description: Learn how to enable a file request in OneDrive or Sharepoint.
locale: en-us
document_id: 1fb80c7f-b87a-6910-b145-1261ce7be4fc
document_version_independent_id: 6085e0fb-1eb5-3a33-9771-11a4b4c6bee2
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/enable-file-requests.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: enable-file-requests
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/enable-file-requests.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
platformId: cc803b72-36ec-ef33-53de-a985fd777e05
---

# Enable File Requests in SharePoint or OneDrive - SharePoint in Microsoft 365 | Microsoft Learn

By using the [file request feature](https://support.microsoft.com/office/create-a-file-request-f54aa7f8-2589-4421-b351-d415fc3b83af) in OneDrive or SharePoint, users can request files by sending a link where others can upload files. When users upload files, they can't view, edit, delete, or download files in the folder or see who else uploaded.

Admins can manage the **Request files** feature through the SharePoint Online Management Shell.

Important

File request is only available if:

- You're using OneDrive for work or school.
- The admin [enabled **Anyone** links](/en-us/sharepoint/turn-external-sharing-on-or-off).
- Folder permissions are set to **View, edit, and upload** for **Anyone** links.
- **Allow only specific security groups** isn't enabled.
- Not available for Office 365 operated by 21Vianet, OneDrive for home, or Office 365 Germany.

Note

Disabling **Anyone** links also disables **Request files** on SharePoint and OneDrive.

## Enable or disable request files for SharePoint

To manage **Request files** for SharePoint:

1. Ensure [**Anyone** links are enabled at the organization level](/en-us/sharepoint/turn-external-sharing-on-or-off#change-the-organization-level-external-sharing-setting).
2. Set folder permissions to **View, edit, and upload** or **View and upload**.
3. Verify `CoreRequestFilesLinkEnabled` is **True** through the SharePoint Online Management Shell:

    - Run `Get-SPOTenant`.
    - If not set to **True**, use `Set-SPOTenant -CoreRequestFilesLinkEnabled $True`.
4. (Optional) Set link expiration by using `Set-SPOTenant -CoreRequestFilesLinkExpirationInDays`.

## Enable or disable request files for OneDrive

To manage **Request files** for OneDrive:

1. Enable [**Anyone** links](/en-us/sharepoint/turn-external-sharing-on-or-off#change-the-organization-level-external-sharing-setting).
2. Set folder permissions to **View, edit, and upload** or **View and upload**.
3. Configure **Anyone** links for OneDrive at the tenant level.
4. Verify `OneDriveRequestFilesLinkEnabled` is **True** via the SharePoint Online Management Shell:

    - Run `Get-SPOTenant`.
    - If not set to **True**, use `Set-SPOTenant -OneDriveRequestFilesLinkEnabled $True`.
5. (Optional) Set link expiration using `Set-SPOTenant -OneDriveRequestFilesLinkExpirationInDays`.

## Enable or disable request files per site

To manage **Request files** for a specific site:

1. Ensure [**Anyone** links are enabled](/en-us/sharepoint/turn-external-sharing-on-or-off#change-the-organization-level-external-sharing-setting).
2. Set folder permissions to **View, edit, and upload** or **View and upload**.
3. Verify `RequestFilesLinkEnabled` is **True** via the SharePoint Online Management Shell:

    - Run `$r=Get-SPOSite -Identity <SiteURL> -Detailed`.
    - If not set to **True**, use `Set-SPOSite -RequestFilesLinkEnabled $True`.
4. (Optional) Set link expiration using `Set-SPOSite -RequestFilesLinkExpirationInDays`.

For more information on file requests, see [Create a file request](https://support.microsoft.com/office/create-a-file-request-f54aa7f8-2589-4421-b351-d415fc3b83af).