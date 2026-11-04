---
layout: Conceptual
title: Create sites with AI - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/create-sites-with-ai
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
description: Learn how to create SharePoint sites using AI with Copilot in Microsoft SharePoint, including prerequisites, prompts, and common scenarios.
author: 695643216
manager: chichantsai
ms.author: oadeyemo
ms.service: sharepoint-online
ms.subservice: ai-copilot
ms.topic: how-to
ms.date: 2026-10-23T00:00:00.0000000Z
ms.update-cycle: 180-days
audience: Admin
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365copilot
f1.keywords:
- NOCSH
search.appverid:
- MET150
locale: en-us
document_id: 5e7024e7-474b-efbd-5b8d-941dc966d859
document_version_independent_id: 809e31fc-ceb0-6cac-0a61-503f0e6b8b41
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/create-sites-with-ai.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: create-sites-with-ai
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/create-sites-with-ai.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
platformId: 7e581535-cad1-f43a-2a53-264ce4a99ab2
---

# Create sites with AI - SharePoint in Microsoft 365 | Microsoft Learn

Copilot in Microsoft SharePoint makes it faster and easier to create SharePoint sites and solutions using natural language. Describe what you need, and Copilot in SharePoint recommends a structure—including pages, lists, libraries, and more. You can review and adjust the AI-generated plan through chat before anything is created. Once you approve the plan, your site is ready in minutes, complete with sample data.

Important

**Create sites with AI** is still in preview.

Key benefits of building sites with AI include:

- **Plan with AI:** Describe what you need and get a proposed build plan (no SharePoint expertise required).
- **Review before you build:** Edit the outline (pages, lists, libraries) before anything is created.
- **Fast execution:** After approval, Copilot in SharePoint creates the site and configures content based on the build plan.
- **Ongoing refinement:** After the site is created, continue to use Copilot in SharePoint to improve pages, organize content, and get answers.

Note

The site creation can take up to 15 minutes. Don't close the browser while creation is progressing.

## Prerequisites

Before you start, confirm the following prerequisites:

1. **Enable Copilot in SharePoint (preview)**: A SharePoint Administrator must enable the preview for your tenant. Your tenant must opt into the preview by using the **All Sites** or **Exclude Selected Sites** configuration. If you opt in by using the **Selected Sites** or **No Sites** configuration, users in your organization can't use this feature. For enablement steps and prerequisites, see [Get started with Copilot in SharePoint](/en-us/sharepoint/copilot-in-sharepoint-get-started).
2. Microsoft Copilot license. Users need an active Copilot license to create sites with AI.
3. Users must be allowed to create SharePoint sites in your organization. [To enable users create new sites, admins must enable self-service site creation.](/en-us/sharepoint/manage-site-creation#manage-site-creation-in-the-new-sharepoint-admin-center)

Note

If users aren't enabled for self-service site creation, SharePoint administrators can create sites with AI on behalf of users.

## Create a site with AI

The easiest way to start is to send a prompt that includes **create new site** to Copilot in SharePoint. Copilot uses the prompts to build the site.

Alternatively, for users with the [new SharePoint experience](/en-us/sharepoint/enable-new-sharepoint-experience):

1. Select [Build](https://support.microsoft.com/office/getting-started-with-build-in-sharepoint-cb17406a-59ea-488a-beb5-f8160af3ecb5) in the left navigation.
2. Describe what you want to build in the prompt box or select one of the suggested prompts.

    [![Screenshot of the Build button and chat box on the SharePoint Build.](sharepointonline/media/create-sites-with-ai/create-site.png)](sharepointonline/media/create-sites-with-ai/create-site.png#lightbox)

Copilot in SharePoint uses a planning mode that you can use to review the proposed site build plan and the visual outline of pages, lists, and libraries before execution. The process doesn't create any assets until you formally approve the plan. Follow these steps to build a site with AI:

### Step 1: Provide a natural language description

In the prompt box, enter a comprehensive description of the site you want to create. Copilot in SharePoint might ask follow-up questions to clarify your requirements.

*Example: “Create a site to help my team collaborate and track project progress.”*

You might be asked a few clarifying questions if more information is needed. Copilot in SharePoint might ask follow-up questions, such as:

“*What kind of projects does your team work on? (e.g., marketing campaigns, software development, event planning, etc.)?”*

*“Do you need to track tasks with deadlines and assignments, or is it more about tracking overall project status?”*

Based on your description and answers to the clarifying questions, Copilot in SharePoint proposes an outline as well as a plan that can include pages, lists, libraries, columns, and views. These clarifying questions are necessary because they help Copilot in SharePoint understand the purpose of your site and your specific requirements.

### Step 2: Review the proposed plan and outline

Review the proposed plan and outline presented in the previous step to make sure it meets your needs. The visual outline shows the structure and description of each proposed site component. The following screenshot shows an example of the visual outline.

[![Screenshot of the visual outline of a proposed site plan.](sharepointonline/media/create-sites-with-ai/outline.png)](sharepointonline/media/create-sites-with-ai/outline.png#lightbox)

To reopen the visual outline, ask Copilot in SharePoint to show it again.

### Step 3: Refine the build plan through chat

Use chat to answer clarifying questions and refine the plan. Refine the plan by adding or removing components, renaming pages, updating lists and library columns, and more. Some examples of how to refine your plans include:

- *“Add a column for time estimate on the Tasks list.”*
- *“Remove the Team overview page.”*

The plan and visual outline update as you make changes. Copilot doesn't create anything until you request creation and select **Confirm** on the confirmation card. If a component is missing, ask Copilot to add it. Copilot in SharePoint also surfaces recommendations to strengthen and enhance your solution, drawing on its understanding of common scenarios and what’s typically needed to support them.

### Step 4: Create the site

When you’re ready, send a **create** request in chat and select **Confirm**.

[![Screenshot of the Confirm button.](sharepointonline/media/create-sites-with-ai/build-it.png)](sharepointonline/media/create-sites-with-ai/build-it.png#lightbox)

During execution, Copilot in SharePoint will follow the plan to:

- Create the site.
- Configure navigation and settings.
- Create lists and libraries (columns, views, metadata).
- Create pages with sample content.
- Add sample documents and list items.

Execution can take up to 15 minutes to complete, depending on how many components are in your site. When execution completes, you’ll see a confirmation and a link to navigate to your new site.

### Step 5: Explore the new site and provided content

The new site includes sample content and structure, such as:

- **Pages** with sample content based on your scenario.
- **Libraries** with relevant names and columns and sample files.
- **Lists** with sample items so teams can understand the structure quickly.

### Step 6: Post-creation refinement

After your site is created, Copilot in SharePoint remains available to help you continue refining, iterating, and configuring the site. When you land on the site homepage, a **Finish site setup** panel appears. The panel:

- Provides a summary of what was created (pages, lists, libraries).
- Offers quick links to key site components.
- Recommends next steps such as sharing your site with others.

    [![Screenshot of the Finish site setup pane.](sharepointonline/media/create-sites-with-ai/screenshot-finish-site-setup-pane1.png)](sharepointonline/media/create-sites-with-ai/screenshot-finish-site-setup-pane1.png#lightbox)

## Unsupported scenarios

During the preview, some SharePoint features and integrations aren't available. If you ask Copilot in SharePoint for something that isn't supported, you'll likely get a response during the planning phase that it can't automatically complete the task. Copilot in SharePoint might suggest to complete it manually after creating the site. A few unsupported features include complex Power Automate flows, permission and sharing set up, column and row formatting, advanced web parts, and third-party integrations.

## Related information

- [Get started with Copilot in SharePoint](/en-us/sharepoint/copilot-in-sharepoint-get-started)