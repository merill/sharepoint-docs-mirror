---
layout: Conceptual
title: Create document library with AI - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/copilot-in-sharepoint-create-document-library
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-09-24T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.author: karlha
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
description: Learn how to use and create a SharePoint document library with AI.
locale: en-us
document_id: fbce7038-ba63-c21d-6f11-59c906b2bd89
document_version_independent_id: c0d11328-2cfa-0c87-31f0-ecf2a1f80d70
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/copilot-in-sharepoint-create-document-library.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: copilot-in-sharepoint-create-document-library
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/copilot-in-sharepoint-create-document-library.md
platformId: 795ef557-f42c-6d5e-1dfa-1aab896baee3
---

# Create document library with AI - SharePoint in Microsoft 365 | Microsoft Learn

By using Copilot in SharePoint to create a document library, you can go from a simple description to a well configured, metadata-rich document library. Instead of manually creating a library, defining columns, and setting up tagging rules, describe what the library is for and optionally provide a sample file. Copilot in SharePoint then generates the library name, description, and a complete metadata schema - with columns that automatically tag new documents as they're added.

This feature is useful for organizations that need to quickly create well-organized document libraries, such as:

- **Finance and accounting:** Invoice repositories, expense report libraries, financial statement archives.
- **Legal and compliance:** Contract libraries, regulatory filing repositories, policy document collections.
- **Project management:** Project deliverable libraries, product specs, milestone documentation.
- **Human resources:** Employee records libraries, benefits documentation, training material collections.

## How AI-powered library creation works

The library creation process uses AI to handle the setup that would otherwise require manual configuration by a site owner or content manager.

1. **You describe the purpose:** Provide a natural language description of what the library is for, for example, "I need a library for vendor invoices."
2. **You provide a sample file (recommended):** Upload an example or seed file that represents the type of content to store. AI uses this file to better understand the document structure and suggest relevant metadata fields. If you don't provide a sample file, AI generates the library configuration from your description alone.
3. **AI generates the configuration:** Based on your description and sample file, AI proposes a library name, description, and a metadata schema with columns tailored to your type of document.
4. **AI creates and configures the library:** The library is created, your sample file is copied to the library if you provided one, and AI-powered columns are configured. These columns use prompts to extract metadata from supported files added to the library.

## Prerequisites

1. Users must have a Microsoft Copilot license assigned.
2. Copilot in SharePoint is on by default for licensed users; no opt-in step is required. To control availability, see [Get started with Copilot in SharePoint](copilot-in-sharepoint-get-started#manage-availability-of-copilot-in-sharepoint).
3. Users must have permissions to create document libraries on the SharePoint site.

## Steps for creating a library with AI

1. From the site home page or site contents page, select **+ New** &gt; **Document library**.
2. Select the AI-assisted creation process.
3. Describe the purpose of the library in the text field. For example:
    - "I need a library to store and organize vendor invoices."
    - "A library for marketing campaign assets and deliverables."
    - "Repository for employee onboarding documents."
4. Optionally, upload a sample file to help AI understand the structure of your documents. You can select a file from:
    - The current SharePoint site
    - A OneDrive location
    - Your local device
5. Review the AI-generated library configuration:
    - **Library name:** A descriptive name based on your input.
    - **Library description:** A summary of the library's purpose.
6. Select **Create** to confirm. AI creates the library, copies over your sample file, and configures the metadata columns.

## AI-powered columns

When you create the library, it includes AI-powered columns based on the metadata schema generated from your description and sample file. These columns use prompts to extract and populate metadata from supported files.

- **Automatic tagging:** When you upload or drop documents into the library, AI reads the content and automatically populates the column values. You can review and update values as needed.
- **User control:** You can review the schema and the underlying prompts during creation and anytime after that.

## Supported file types

AI-powered library creation uses the same underlying [Autofill feature](/en-us/microsoft-365/documentprocessing/autofill-overview) that reads document content and populates metadata values. This feature means the same file type compatibility applies to both the initial sample file you provide during library creation and to any documents you add to the library afterward.