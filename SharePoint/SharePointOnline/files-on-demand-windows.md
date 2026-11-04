---
layout: Conceptual
title: Set Files On-Demand states in Windows - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/files-on-demand-windows
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2024-09-01T00:00:00.0000000Z
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
- OFF160
- ODB150
- MET150
ms.assetid: 3eff17b9-c709-462f-946c-17719af68aca
description: Learn how to query and set file and folder states when you use OneDrive Files On-Demand on Windows.
locale: en-us
document_id: e0b69094-5db5-0e81-dd43-0e49c159582d
document_version_independent_id: 8fec6902-f639-44d7-a3a5-3f4089e03df9
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/files-on-demand-windows.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: files-on-demand-windows
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/files-on-demand-windows.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
platformId: a58f7f16-ca59-4e0b-cef6-54c6eb8c9731
---

# Set Files On-Demand states in Windows - SharePoint in Microsoft 365 | Microsoft Learn

With OneDrive Files On-Demand, files can be in one of three states. Each of these states corresponds to a file attribute state. To query the current state of a file or folder, use the following command:

- attrib &lt;Path to file or folder&gt;

## Scriptable commands

Use the following commands to set file and folder states.

| **Files On-Demand state** | **File attribute state** | **Command** |
| --- | --- | --- |
| Always available | Pinned | attrib +p &lt;path&gt; |
| Locally available | Clearpin | attrib -p &lt;path&gt; |
| Online-only | Unpinned | attrib +u &lt;path&gt; |

Note

Pinning an online-only file makes the sync app download the file contents, and unpinning a downloaded file frees up space on the device by not storing the file contents locally. To set an online-only file or folder to "locally available," you must first set it to "always available."If you meet the [Sync app requirements](https://support.office.com/article/cc0cb2b8-f446-445c-9b52-d3c2627d681e) and still can't see the Files On-Demand option under "Settings", make sure the service "Windows Cloud Files Filter Driver" start type is set to 2 (AUTO\_START). Enabling this feature sets the following registry key value to 2.`[HKLM\SYSTEM\CurrentControlSet\Services\CldFlt]"Start"="dword:00000002"`