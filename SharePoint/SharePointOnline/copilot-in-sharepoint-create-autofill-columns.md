---
layout: Conceptual
title: Create autofill columns - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/copilot-in-sharepoint-create-autofill-columns
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-06-15T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.reviewer: ssquires
ms.author: chucked
author: chuckedmonson
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ROBOTS: 
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: ai-copilot
ms.collection:
- M365-collaboration
- m365copilot
ms.localizationpriority: medium
search.appverid:
- MET150
description: Learn how to organize files, automate columns, and classify documents in a document library in SharePoint.
locale: en-us
document_id: 82861221-c9e3-5496-5b58-974029ff0d66
document_version_independent_id: a504c36c-dcc8-78cd-b497-7d66ec90fd55
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/copilot-in-sharepoint-create-autofill-columns.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: copilot-in-sharepoint-create-autofill-columns
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/copilot-in-sharepoint-create-autofill-columns.md
platformId: 1cfde4d8-cdde-ac11-7393-20c12427ad20
---

# Create autofill columns - SharePoint in Microsoft 365 | Microsoft Learn

Copilot in SharePoint helps you automatically generate metadata for your document libraries using autofill columns.

The Create autofill columns capability analyzes files in the library and suggests metadata columns and extraction prompts. These columns automatically populate metadata from file content, helping organize libraries, improve discovery, and support automation scenarios.

## Get suggested columns and metadata

To get suggested columns and metadata based on the first 20 files in your document library, follow these steps.

1. Launch the quick action.
2. Use a suggested prompt or enter a custom prompt.
3. Save your changes.

### Launch the quick action

1. Select the Copilot in SharePoint icon in the lower-right corner of your document library.
2. From the quick actions menu, select **Create autofill columns**.
3. The chat panel opens and displays a list of suggested prompts related to the creation of columns.

    Note

    If this is the first time using Copilot in SharePoint in the library, it will automatically suggest up to three columns based on the available files.
4. You can also request your own column in the chat panel.

### Use a suggested prompt

1. From the chat panel, select an action. For this example, we use create autofill columns or add autofill columns.
2. In the chat box, review the instruction provided. If needed, you can modify the text to better suit your intent. Once you're ready, select **Send** to submit your action.
3. AI analyzes up to 20 recent files in the document library to generate column suggestions. These files are selected across supported file types (such as Office documents and PDF files) to provide representative analysis.

    If you select specific files before running Autofill, AI analyzes only the selected files.

    The suggested columns appear highlighted and marked as AI-generated. This might take a few moments.

    [![Create autofill columns - suggestions.](sharepointonline/media/knowledge-agent-organize-files/create-autofill-columns-suggestions.jpg)](sharepointonline/media/knowledge-agent-organize-files/create-autofill-columns-suggestions.jpg#lightbox)

    Tip

    The suggested column information is summarized in the chat panel. [![Create autofill columns - suggestions chat panel](sharepointonline/media/knowledge-agent-organize-files/create-autofill-columns-suggestions-chat-panel.jpg)](sharepointonline/media/knowledge-agent-organize-files/create-autofill-columns-suggestions-chat-panel.jpg#lightbox)
4. Review the suggested columns and the associated metadata to make sure they're appropriate for your content.
5. To remove a suggested column:

    - From the document library page, select the column name, and then select **Remove column**.
    - From the chat panel, on the column card, select **Remove**.
6. To rename the column or to refine the metadata in a suggested column:

    - From the document library page, select the column name, and then select **Edit column**.
    - From the chat panel, on the column card, select **Edit**.
7. On the **Edit column** panel, you can change the column name or modify the instruction that generates the metadata. After you edit the instruction, test it on up to 10 files to make sure it gives you the information you want. When you're done making changes for that column, select **Save**.

### Enter a custom prompt

1. In the chat panel's text box, enter your own instruction.

    Tip

    When requesting a column, be sure to specify a clear name and what type of information you would like to capture (for example, reason for document creation or project rationale), as well as any specifics around format and length. This helps ensure the column meets your needs. [![Create autofill columns - complex prompt](sharepointonline/media/knowledge-agent-organize-files/create-autofill-columns-complex-prompt.jpg)](sharepointonline/media/knowledge-agent-organize-files/create-autofill-columns-complex-prompt.jpg#lightbox)
2. Select **Send** to submit your action.

### Save your changes

1. When you're ready to save all of the column changes, select **Save changes**.
2. On the **Save and apply your changes?** confirmation screen, verify that you want to update the current library view or save as a new view, and then select **Apply changes**.

    Tip

    If you create a new view, it will be the name of the library appended with a numerical value. The naming experience will be improved in future updates, but for now you can rename the view from the library command bar.
3. You're returned to the updated library, and processing begins for up to the first 20 files in the library. You can verify and monitor the progress in the [activity panel](copilot-in-sharepoint-file-processing-status#view-the-activity-panel).
4. After these prompts are saved on a column, any new files uploaded to the library are automatically processed, and the extracted information is saved to the corresponding columns.

### Newly uploaded files

After you save the changes and create autofill metadata columns for a library, all newly uploaded files are automatically processed with metadata. This applies regardless of whether the uploader has a Copilot license. Any new file added to the library will have metadata applied automatically.

All newly added files are also included as part of your Copilot benefits. Even if the library is connected to a pay-as-you-go meter, new files in this library are not charged at a pay-as-you-go rate and are instead covered by the Copilot license.

### Apply changes to existing files

You can apply the same metadata logic to existing files in the library by selecting the files you want to process. Once selected, select the **Autofill** button to get documents processed and updated with metadata.

[![Autofill menu](sharepointonline/media/knowledge-agent-organize-files/autofill-menu.png)](sharepointonline/media/knowledge-agent-organize-files/autofill-menu.png#lightbox)

## Advanced Autofill

Advanced Autofill uses Copilot Credits to process documents faster when you need additional processing capacity. It’s available only to organizations that have turned on usage-based billing for Copilot in SharePoint.

Site admins can turn on Advanced Autofill for all site members by sharing their Copilot Credits with the site. Once turned on, Autofill uses advanced processing whenever it runs on the site.

If Copilot Credits are unavailable, Autofill uses the processing capacity included with each user’s Microsoft 365 Copilot license until credits are available again.

## Set up Advanced Autofill

Only site admins can change the Advanced Autofill setting.

To turn on Advanced Autofill on a SharePoint site:

1. On the SharePoint site, select **Settings**.
2. Open the **Site AI** panel.
3. Under **Advanced Autofill columns**, turn on **Share credits for advanced autofill columns**.

Note

Site admins can only share Copilot Credits from their own account.

## Requirements and limitations

- **Supported file types:** .csv, .docx, .pdf, .xlsx, and other Microsoft 365-compatible formats.
- **Supported languages:** All languages supported through [Microsoft Copilot](https://support.microsoft.com/topic/26de43a1-c176-4908-bef7-29c8c37ac7ce) for text-based prompts and responses, but can only process files in English.
- **Supported column types:** Text, Multiple lines of text, Number, Yes/No, Date and time, Choice, Hyperlink, Currency, and Managed metadata.
- **Limitations:**
    - Person or Group, Location, Image, and Lookup column types are currently unsupported.
    - For optimal performance, we recommend adding no more than 10 columns per library and processing files no larger than 65 pages.
    - Copilot in SharePoint can process files only, not folders. If files within a folder are used to configure the library, the configuration applies to the entire library.
    - Copilot in SharePoint processes up to 20 files during initial column configuration. To extract information from additional files, select the files and choose **Autofill columns** &gt; **Autofill** from the command bar. You can monitor progress by selecting **Autofill columns** &gt; **View autofill activity**.
- If a managed metadata column type is used, it can only use the first 100 terms of a mapped term set. If a preferred term or synonym matches, the preferred term is saved to the column.
- Encrypted files cannot be analyzed, and their metadata is not included in the results. If encrypted files are present, they may appear as not processed.
- Copilot in SharePoint can configure document libraries only. The following library types aren't supported: FormServerTemplates, SitePages, Style Library, and SiteAssets.
- This service is available only for SharePoint sites — including hub sites, sites associated to a hub site, and the primary site of a site collection. Subsites aren't supported.