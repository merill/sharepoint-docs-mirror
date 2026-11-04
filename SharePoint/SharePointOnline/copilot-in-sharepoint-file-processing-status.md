---
layout: Conceptual
title: Monitor file processing status - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/copilot-in-sharepoint-file-processing-status
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: 
ms.date: 2026-09-24T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.reviewer: ssquires
ms.author: chucked
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
description: Learn how to monitor the processing status of files in a SharePoint document library.
locale: en-us
document_id: 3446a79a-f9f2-c483-9b93-f019a95b9ea4
document_version_independent_id: 10df4759-3486-6fb2-14cc-7431af3208e0
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/copilot-in-sharepoint-file-processing-status.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: copilot-in-sharepoint-file-processing-status
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/copilot-in-sharepoint-file-processing-status.md
platformId: 11cf49ab-d926-3bd8-9bbe-d0aaf47f6734
---

# Monitor file processing status - SharePoint in Microsoft 365 | Microsoft Learn

You can monitor real-time updates on files processed in a SharePoint library. This feature lets you:

- See when a file is being processed.
- Check the status of the file: **In progress**, **Completed**, or **Failed**.
- Understand what worked, what didn’t, and why.

You can view the processing status for a file that is being processed, for a selected file or for all files in a document library.

## Prerequisites

To use this feature, you need:

- [Microsoft Copilot license](/en-us/microsoft-365/copilot/microsoft-365-copilot-licensing)
- [Copilot in SharePoint](copilot-in-sharepoint-get-started)

## Monitor the status of a file being processed

When you submit an on-demand request to process a file:

1. A message bar appears at the top of the library, indicating the action is in progress.
2. On the right side of the message bar, select **View status** to open the activity panel.
3. The activity panel shows the current action being processed.

## Monitor the status of any file

To view the processing status of one or more files:

1. In a SharePoint document library, select the files.
2. From the **More options** (**...**) menu next to the file name or on the command bar, select the service, and then select **View recent activity**.
3. The activity panel shows the current action being processed.

## Monitor the status of all files

To view the processing status of all files in the library:

1. In a SharePoint document library, on the command bar, select **More options** (**...**), select the service, and then select **View recent activity**.
2. The activity panel shows the current actions being processed.

## View the activity panel

The activity panel displays a list of file processing events, including:

- File name
- Summary of the action that was performed, or information about why it failed
- Processing status: **In progress**, **Completed**, or **Failed**
- Date and time of the event

Note

If you select no files or more than 30 files, the activity pane displays the processing status for the entire library, rather than for individual files.

### Filter activity options

By default, the panel shows activity for the last 60 days.

- To filter by date, select **Filter** &gt; **Date range**.
- To show only failed files, select **Filter** &gt; **Failed status**.

### Status definitions

| Status | Description |
| --- | --- |
| In progress | The service starts processing the file. A timestamp is displayed. |
| Completed | The service finishes processing successfully. A description of the completed actions is provided. |
| Failed | The service encounters an error. A description of the cause of the failure is provided. |