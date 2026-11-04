---
layout: Conceptual
title: Copilot skills in the SharePoint admin center - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/copilot-skills-sharepoint-admin-centers
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-06-25T00:00:00.0000000Z
ms.reviewer: nvasudevan, pasalinas
manager: dansimp
ms.author: deniseb
author: denisebmsft
audience: Admin
customer-intent: As a SharePoint admin, I want to use Copilot skills in the SharePoint admin center to ask questions and get assistance so that I can be more productive.
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: ai-copilot
ms.localizationpriority: medium
ms.collection:
- Highpri
- Tier2
- M365-sam
- M365-collaboration
- essentials-manage
search.appverid: 
description: Learn how to use Copilot skills in the SharePoint admin center to ask questions and get assistance.
locale: en-us
document_id: 832dded4-537e-3db0-d83b-176add996ba9
document_version_independent_id: 10999780-a98f-84c8-9161-0648c35112d0
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/copilot-skills-sharepoint-admin-centers.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: copilot-skills-sharepoint-admin-centers
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/copilot-skills-sharepoint-admin-centers.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: db5f817d-6cd3-0b48-0711-c6459b73a15a
---

# Copilot skills in the SharePoint admin center - SharePoint in Microsoft 365 | Microsoft Learn

Copilot in the SharePoint admin center uses generative AI to make you more productive by simplifying administration of SharePoint and OneDrive. It helps you focus on more strategic priorities. Copilot skills in the SharePoint admin center provide natural language interactions, contextual guidance, and proactive suggestions.

You can use Copilot to help manage your organization and focus on what's important. Try using the prepopulated prompt options in the Copilot pane for the best results. Or, try using Voice input controls to dictate your question.

The following sections describe what you can do with Copilot in the SharePoint admin center.

Note

To maintain your security and privacy, Copilot doesn't make any configuration changes on your behalf.

## Prerequisites

You must have a Microsoft 365 subscription that includes SharePoint and a license for Microsoft Copilot (see [License options for Microsoft Copilot](/en-us/microsoft-365/copilot/microsoft-365-copilot-licensing)).

For more information, see [Prerequisites for SharePoint Advanced Management](sharepoint-advanced-management-prerequisites).

## Get started with Copilot in the SharePoint admin center

To use Copilot in the SharePoint admin center, follow these steps:

1. Sign in to the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219).
2. Select the **Copilot** button in the upper right shell to launch Copilot in the SharePoint admin center.

### Get step-by-step guidance with Copilot

Copilot can walk you through the exact steps required to complete common admin tasks. For example, you can ask questions like "How can I find sites that are potentially over-permissioned?"

Copilot recommends clear, sequential instructions to guide you from start to finish. It first runs the site permissions report for your organization, then runs activity-based reports, and finally initiates site access reviews for site owners to review and remediate their sites.

![Screenshot showing Copilot in the SharePoint admin center providing step-by-step guidance for finding over-permissioned sites with sequential instructions.](sharepointonline/media/copilot-skills/step-by-step-copilot-skills.png)

### Multi-criteria site search

Copilot can help you find sites by querying on multiple conditions at once. For example, you can type a query like "Find sites created in the last month that are shared externally."

Copilot generates a filtered list of sites based on your criteria. In this case, the list includes sites that were created last month and that are shared externally. You can then ask for more details or apply more filters to refine your results.

[![Screenshot showing Copilot in the SharePoint admin center displaying multi-criteria site search results with filtered list of sites that are inactive and shared externally.](sharepointonline/media/copilot-skills/multi-criteria-site-search.png)](sharepointonline/media/copilot-skills/multi-criteria-site-search.png#lightbox)

### Getting details about a specific site

You can ask Copilot to show you details about a specific site right in the chat. For example, you can type a query like "Show details about the site `site_name`."

Copilot returns details about the specific site, including site name, URL, creation date, creator, external sharing status, sensitivity labels, storage status, template, and site ID.

[![Screenshot showing Copilot in SharePoint admin center providing details about a specific site including site name, URL, creation date, creator, external sharing status, sensitivity labels, storage status, template, and site ID.](sharepointonline/media/copilot-skills/site-details.png)](sharepointonline/media/copilot-skills/site-details.png#lightbox)

## Voice input controls for Copilot in the SharePoint admin center

Voice input enables you to dictate queries into Copilot, improving accessibility and ease of use. When you use voice input with Copilot, the transcribed text appears in the Copilot chat box in real time, where you can review and edit it before submitting to Copilot.

### How to use the voice input feature

1. In the SharePoint admin center, with Copilot open, select the microphone in your chat window. The first time, you're prompted to grant permission in your browser window.

    [![Screenshot showing first use of voice in Copilot in the SharePoint admin center.](sharepointonline/media/copilot-skills/copilot-microphone-first-use.png)](sharepointonline/media/copilot-skills/copilot-microphone-first-use.png#lightbox)
2. With the microphone on, speak your query and see the transcription in the Copilot chat experience. You can modify the text during and after audio capture, and then submit your query when you're ready.

    [![Screenshot showing the Copilot experience using a transcribed query.](sharepointonline/media/copilot-skills/copilot-voice-query-experience.png)](sharepointonline/media/copilot-skills/copilot-voice-query-experience.png#lightbox)

    Copilot automatically stops transcribing if no audio is detected.

## Frequently asked questions

### How do I enable Copilot in the SharePoint admin center?

Copilot is automatically enabled for customers whose subscriptions include SharePoint and Microsoft Copilot.

### How do I disable Copilot in the SharePoint admin center?

To disable Copilot in the SharePoint admin center, set up a custom security group called `CopilotForM365AdminExclude`, and then add the administrators you don't want to have the Copilot experience. Once the group is configured, the Copilot experience is automatically disabled for those users.

### Which admin roles can use Copilot in the SharePoint admin center?

The feature is available to SharePoint administrators. Copilot in the SharePoint admin center respects role-based access controls and only shows information and controls that the user has access to. Copilot doesn't make any configuration changes on your behalf.

### Does Copilot in the SharePoint admin center support audit logging?

Yes. Copilot in the SharePoint admin center aligns with Microsoft's commitment to providing enterprise-grade compliance capabilities for all Copilot products. These capabilities include features such as auditing, eDiscovery, legal hold, and data retention controls.

### How much does Copilot in the SharePoint admin center cost?

This feature is included with a Microsoft Copilot license. When you purchase and assign Microsoft Copilot licenses for your tenant, admin users who have a Copilot license can use Copilot in the SharePoint admin center.