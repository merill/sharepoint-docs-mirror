---
layout: Conceptual
title: File Type Version Limits - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/file-type-version-limits
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
description: Learn how SharePoint uses file-type–specific version limits to manage storage.
author: blarrywangmsft
manager: yigitd
ms.author: blarrywang
ms.service: sharepoint-online
ms.subservice: platform
ms.topic: concept-article
ms.date: 2025-12-12T00:00:00.0000000Z
locale: en-us
document_id: f1efab52-cbb4-cc6e-32c7-3e3dbcaf417b
document_version_independent_id: bfe306b1-7cec-4f02-eff4-44e6a706eeb3
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/file-type-version-limits.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: file-type-version-limits
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/file-type-version-limits.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 61743fdd-37a3-93db-2af4-1cd711695706
---

# File Type Version Limits - SharePoint in Microsoft 365 | Microsoft Learn

SharePoint supports file-type–specific version history limits. It gives organizations finer control over how versions are retained by allowing certain file types to use different version limits than the default library settings.

The extension of a file determines its file type. Today, the following file-type categories are supported:

| Name (case-insensitive) | Description | Extensions |
| --- | --- | --- |
| **audio** | Audio files | au, flac, m4a, mp3, ogg, wav, wma, aac, m4b, m4p |
| **video** | Video files | mts, m2ts, ts, 3g2, 3gp, 3gp2, 3gpp, asf, wmv, avi, m4v, mov, mp4, mp4v, webm, movie, mkv, mpg, flv, mpeg |
| **outlookpst** | Outlook Data File | pst |

When you configure a file‑type–specific version history limit on a document library, that limit replaces the library’s default version history settings for that file type. Versions of the specified file type follow only the file-type version history limit.

## Example

Suppose your document library uses an automatic version history limit that applies to all files. You notice that audio files are consuming more storage than expected. To address the storage issue, you want a stricter version limits for audio files and keep the existing automatic limit for all other files.

To implement the version limits, you configure a file-type override that sets a 30‑day manual expiration period and a maximum of 100 major versions for audio files. After this change:

- New versions of **audio** files follow the file-type–specific manual limits.
- New versions of **other** file types continue using the library’s automatic limit unchanged.

Note

Today, OutlookPST files use a manual limit that keeps 30 major versions and no expiration by default.

## Learn More

For more information, check out the following resources:

- [Modify and view organization-level version limits](set-default-org-version-limits)
- [Modify and view site-level version limits](site-version-limits)
- [Modify and view library-level version limits](library-version-limits)
- [Trimming existing versions](trim-versions)