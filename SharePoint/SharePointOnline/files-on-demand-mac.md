---
layout: Conceptual
title: Set Files On-Demand states on Mac - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/files-on-demand-mac
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2024-09-18T00:00:00.0000000Z
ms.reviewer: cagreen
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
description: Learn how to query and set file and folder states when you use OneDrive Files On-Demand on Mac.
locale: en-us
document_id: 9537147b-4205-3355-c7ff-a3a8c115d0ae
document_version_independent_id: cc079c73-e4fc-d5be-69e6-742e335d375e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/files-on-demand-mac.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: files-on-demand-mac
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/files-on-demand-mac.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 1ae44381-23e3-c44d-09e0-db110a6525b5
---

# Set Files On-Demand states on Mac - SharePoint in Microsoft 365 | Microsoft Learn

With OneDrive Files On-Demand, files can be in one of three states. Each of these states corresponds to a file attribute state.

To query the current state of a file or folder, use the following command:

- /Applications/OneDrive.App/Contents/MacOS/OneDrive /getpin &lt;Path to file or folder&gt;

## Scriptable commands

Use the following commands to set file and folder states. Quit the OneDrive sync app before running these commands.

| **Files On-Demand state** | **File attribute state** | **Command** |
| --- | --- | --- |
| Always available | Pinned | /Applications/OneDrive.App/Contents/MacOS/OneDrive /pin &lt;path&gt; |
| Locally available | Clearpin | /Applications/OneDrive.App/Contents/MacOS/OneDrive /clearpin &lt;path&gt; |
| Online-only | Unpinned | /Applications/OneDrive.App/Contents/MacOS/OneDrive /unpin &lt;path&gt; |

Note

To set the file attribute state for all items within a folder, add the /r parameter.Pinning an online-only file makes the sync app download the file contents, and unpinning a downloaded file frees up space on the device by not storing the file contents locally.To set an online-only file or folder to "locally available," you must first set it to "always available."