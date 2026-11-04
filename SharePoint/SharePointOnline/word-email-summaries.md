---
layout: Conceptual
title: Summaries in sharing emails for Word docs - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/word-email-summaries
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2024-10-07T00:00:00.0000000Z
ms.reviewer: srice
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: reference
ms.service: sharepoint-online
ms.localizationpriority: medium
ms.collection: 
search.appverid:
- SPO160
- BSA160
- MET150
ms.assetid: 317eed2b-d266-4c4c-9a37-1aceed9db567
description: Learn how to disable summary info in sharing emails.
locale: en-us
document_id: d0865b58-e457-85f1-12ae-6e981412d2ed
document_version_independent_id: 59748f53-7ea4-eeb4-9338-85e67c21f55d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/word-email-summaries.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: word-email-summaries
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/word-email-summaries.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 21be67e7-b84d-a6af-1275-eb610919726b
---

# Summaries in sharing emails for Word docs - SharePoint in Microsoft 365 | Microsoft Learn

Important

As of May 2024, we are no longer send summaries in sharing emails for Word documents.

When users share a Word document in SharePoint or OneDrive, recipients get an email that shows:

- The key points in the doc (derived from content extracted from the document by artificial intelligence)
- An estimated time to read the doc (based on the word count and the average reading speed in English)

This summary info helps recipients plan for the work that the doc will require. Currently, this feature only works if the selected links are "Anyone" or "People in my organization."

![A sharing email with summary info.](sharepointonline/media/sharing-email.png)

Note

Files that have been marked as sensitive by DLP do not include the summary info. The summary info that appears in sharing emails also [appears on file cards in SharePoint and OneDrive](https://support.microsoft.com/office/87a23bbc-a516-42e2-a7b6-0ecb8259e026).

If you, as a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365, don't want recipients to receive summary info in sharing emails, you can disable it.

1. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    Note

    If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell."
2. Connect to SharePoint as a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
3. Run the following command:

    ```PowerShell
    Set-SPOTenant -IncludeAtAGlanceInShareEmails $false 
    ```