---
layout: Conceptual
title: Create views in a SharePoint document library - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/copilot-in-sharepoint-create-views
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: 
ms.date: 2026-09-24T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.reviewer: jseto
ms.author: jseto
author: cjtancortex
manager: corywink
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
description: Learn how to use rules to create custom views in a SharePoint document library.
locale: en-us
document_id: 9114b80a-3a93-23ce-37e7-b486fcee5116
document_version_independent_id: c29a99d8-8419-bb0a-1433-7e3637b26a96
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/copilot-in-sharepoint-create-views.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: copilot-in-sharepoint-create-views
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/copilot-in-sharepoint-create-views.md
platformId: d12b62e7-2eb1-9dfb-6da4-575be97851e2
---

# Create views in a SharePoint document library - SharePoint in Microsoft 365 | Microsoft Learn

Copilot in SharePoint helps you create custom views of your document libraries. By showing and hiding columns, sorting, and filtering, these capabilities can configure your library to highlight what’s most important to you.

## Launch the quick action

1. In the lower-right corner of your document library, select the Copilot in SharePoint icon.
2. From the **quick actions** menu, select **Create new view**.
3. The chat panel opens and displays a list of suggested actions related to custom views.

    Note

    If this is the first time using Copilot in SharePoint in the library, it automatically generates up to three suggested columns based on the available files. These columns are auto-populated with metadata about your files and can be useful when creating views.

## Use a suggested prompt

1. From the chat panel, select an action. For this example, use **Show recently updated files first**.
2. In the chat box, review the instruction provided. If needed, modify the text to better suit your intent. When ready, select **Send** (![Screenshot of the send icon in the chat box.](sharepointonline/media/knowledge-agent/chat-box-send-icon.png)) to submit your action.
3. Based on your prompt, a view is generated. The view parameters are summarized in the chat panel.

    ![Sort column modified prompt_jpg](sharepointonline/media/knowledge-agent-create-views/sort-column-modified-prompt.jpg)

## Enter a custom prompt

1. In the chat panel’s text box, enter your own custom view instruction. When describing a view, consider what you want to see (filters) and how you want it grouped or sorted. This consideration helps ensure the view meets your needs.

    ![Show me files were product_advanced prompt_jpg](sharepointonline/media/knowledge-agent-create-views/show-me-files-were-product-advanced-prompt.jpg)

    Tip

    You can use Copilot in SharePoint to show and hide columns, sort, filter, and group. Here are some sample prompts that you can use on libraries containing different document types:

    - **Invoices**: Show me past due invoices, grouped by vendor and sorted by amount due.
    - **Product specs**: Show me products with a release date in 2020 and sort by market positioning.
    - **HR policy documents**: Display HR policies by category showing only those that are already in effect.
    - **Project plans**: I want to see project plans grouped by phase and sorted by start date. Show the owner column and hide the location column.
2. Select **Send** (![Screenshot of the send icon in the chat box.](sharepointonline/media/knowledge-agent/chat-box-send-icon.png)) to submit your action.
3. Based on your prompt, a view is created and summarized in the chat panel.

    ![Show me files were product with chat response](sharepointonline/media/knowledge-agent-create-views/show-me-files-were-product-with-chat-response.jpg)

    Tip

    In the chat panel, you can see a full description of the view created. The view is also reflected in the document library.

    [![Filter on Athletics and group by product_advanced prompt_jpg.](sharepointonline/media/knowledge-agent-create-views/filter-on-athletics-and-group-by-product-advanced-prompt.jpg)](sharepointonline/media/knowledge-agent-create-views/filter-on-athletics-and-group-by-product-advanced-prompt.jpg#lightbox)

    The generated view might also apply visual cues to help highlight important information in the library. For example, filtered results or grouped items might appear together, making it easier to quickly identify relevant files. These visual changes are part of the view configuration and reflect filters, grouping, and sorting defined by the prompt.

    Tip

    Copilot in SharePoint can generate views from library metadata. In this example, it groups files by product line, sorts by document type, and filters to display only graphene mesh content.

    [![Doc screenshot - views _ last tip complex prompt.](sharepointonline/media/knowledge-agent-create-views/doc-screenshot-views-last-tip-complex-prompt.jpg)](sharepointonline/media/knowledge-agent-create-views/doc-screenshot-views-last-tip-complex-prompt.jpg#lightbox)

## Save your changes

1. When you're ready to save the view you created and any other changes you made, select **Save changes**.
2. On the **Save changes to library?** confirmation screen, verify that you want to update the **current library view** or save as a **new view**, and then select **Apply changes**.

    Tip

    If you create a new view, the name of the library is appended with a numerical value. Future updates will improve the naming experience, but for now you can rename the view from the library command bar.
3. You're returned to the updated library and the view you created. Views created by using Copilot in SharePoint are public views and are visible to everyone who uses the document library.

## Requirements and limitations

- **Supported view actions**: Show column, Hide column, Sort, Filter, and Group-By.
- **Supported column types for filtering**: Choice, Number, Text, DateTime, Boolean, Currency, and MMD.
- **Supported column types for column creation**: Choice, Number, Text, DateTime, Boolean, Note, Currency, URL, and MMD.
- **Supported languages**: All languages supported through [Microsoft Copilot](https://support.microsoft.com/topic/26de43a1-c176-4908-bef7-29c8c37ac7ce) for text-based prompts and responses, but it can only process files in English.
- **Limitations**:

    - Encrypted files can't be analyzed to generate metadata for views.
    - Copilot in SharePoint doesn't yet support column ordering, column width changes, or conditional formatting of views.
    - Personal views aren't currently supported. Views created by using Copilot in SharePoint are public views that are visible to everyone who uses the document library.