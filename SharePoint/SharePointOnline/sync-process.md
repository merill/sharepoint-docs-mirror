---
layout: Conceptual
title: How sync works - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/sync-process
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2024-09-14T00:00:00.0000000Z
ms.reviewer: kafeaver
ms.author: v-mactran
author: MachelleTranMSFT
manager: jtremper
audience: Admin
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
- MET150
ms.assetid: 2f748bc6-6f01-4406-a791-ec047f066d6d
description: Learn how the OneDrive sync app works. Understand how information flows between applications, how technologies work together, & how data is secured.
locale: en-us
document_id: 552cd361-7573-b537-c282-86e0fdff47f8
document_version_independent_id: 8a1d7604-d47b-51f6-b3ee-89a0140cdce9
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/sync-process.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: sync-process
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/sync-process.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 0d11e951-2aad-4ea5-41d0-8830a088af73
---

# How sync works - SharePoint in Microsoft 365 | Microsoft Learn

This article gives you an overview of how sync works in Microsoft OneDrive. It helps you understand the logic behind how information flows between applications, how the technologies work together, and how data is secured.

[Download the PDF](https://go.microsoft.com/fwlink/p/?LinkId=829044)

![Illustration of the sync process](sharepointonline/media/sync-process-infographic.png)

## How information flows

The OneDrive sync app uses [Windows Push Notification Services](/en-us/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview) (WNS) to sync files in real time. WNS informs the sync app whenever a change actually happens, eliminating redundant polling and saving on unnecessary computing power.

Here's how it works:

- A change occurs in Microsoft 365.
- WNS alerts the sync app of the change.
- OneDrive adds it to the Internal Server Changes Queue.

    - Any metadata changes happen immediately, like renaming or deleting files.
    - Downloading content also starts a specific session with the client.
- Microsoft 365 has metadata pointers directing it through Microsoft Azure.
- The changes are processed in the order they're received.

The previous OneDrive sync app (Groove.exe) used a polling service to check for changes on a predetermined schedule. Polling can lead to system lag and slowness because it requires a significant amount of computing power. Using WNS is a significant enhancement.

## Authentication protocols

The authentication protocols depend on which version of SharePoint you're using.

- SharePoint Server 2019 uses NTLM.
- SharePoint in Microsoft 365 uses FedAuth.

## Syncing different file types

OneDrive handles sync differently depending on the type of file.

For Office 2016 and Office 2019 files, OneDrive collaborates directly with the specific apps to ensure data are transferred correctly. If the Office desktop app is running, it handles the syncing. If it isn't running, OneDrive will.

For other types of files and folders, items smaller than 8 MB are sent inline in a single HTTPS request. Anything 8 MB or larger is divided into file chunks and sent separately one at a time through a [Background Intelligent Transfer Service](/en-us/windows/desktop/Bits/background-intelligent-transfer-service-portal) (BITS) session. Other changes are batched together into HTTPS requests to the server.

## The underlying technologies

The OneDrive sync app uses the following to sync files:

- To find new changes and upload information: `https://<tenant_name, i.e. contoso>-my.sharepoint.com/personal/<user_contoso_onmicrosoft_com>/_api/SPFileSync/sync/<default document library ID GUID>/`
- To download items: `https://<tenant_name, i.e. contoso>-my.sharepoint.com/personal/<user_contoso_onmicrosoft_com>/_layouts/15/download.aspx`
- To discover the sites and organizations a user can access: `https://odc.officeapps.live.com/odc/servicemanager/userconnected`

## Security and encryption

File chunks are stored in multiple containers in Azure, each of which is given a unique key. Each key is required to reassemble the complete file. There's also a separate master key encrypting each file chunk key, ensuring the data remain secure even when not moving.

## Related topic

- [SharePoint Authentication in Microsoft 365](/en-us/sharepoint/authentication)