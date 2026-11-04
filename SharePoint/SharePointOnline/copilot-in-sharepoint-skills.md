---
layout: Conceptual
title: Extend Copilot in SharePoint with skills - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/copilot-in-sharepoint-skills
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-09-28T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.author: akashravi
author: joekomban
manager: corywink
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: ai-copilot
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365copilot
search.appverid:
- MET150
description: Learn how to create and use skills to extend Copilot in SharePoint with repeatable, multi-step workflows.
locale: en-us
document_id: f0b85caa-c634-5a16-d7f3-f56be1616dee
document_version_independent_id: e3bb41a1-294e-4e3a-fcc0-9b5cb89128d2
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/copilot-in-sharepoint-skills.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: copilot-in-sharepoint-skills
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/copilot-in-sharepoint-skills.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
platformId: c12aaf4c-7fc5-7e7b-8d12-3b9d7c256f8e
---

# Extend Copilot in SharePoint with skills - SharePoint in Microsoft 365 | Microsoft Learn

Skills extend Copilot in SharePoint by turning a repeatable, multistep workflow into a reusable asset. Skills can support an individual's way of working or a shared process on a SharePoint site.

You can ask Copilot to create a skill by using natural language. Copilot uses the built-in **Create skill** capability to help you define the workflow and choose between a personal skill and a site skill. You can review the draft before saving it and then reuse the skill in future prompts.

## What you'll learn

- Understand the difference between personal and site skills.
- Choose the appropriate skill type for a workflow.
- Create and run personal and site skills from natural-language requests.
- Locate and manage both types of skills.

## Choose a skill type

Choose the skill type based on who needs to use the workflow.

| Consideration | Personal skill | Site skill |
| --- | --- | --- |
| Best fit | A workflow based on your individual preferences or way of working | A workflow that people on the same site should use consistently |
| Owner | The user | The site admin |
| Storage | The user's OneDrive | The site's **Agent Assets** library |
| Availability | Available to its owner across SharePoint sites | Available only on the associated site |
| Examples | Review documents with your own checklist; format content in your preferred style | Apply team review requirements; enforce shared document standards; update a shared list |

Important

Portability doesn't grant access. A personal skill can act only on sites and content that the user already has permission to access.

## What skills can do

Personal and site skills use the same built-in capabilities of Copilot in SharePoint and can chain those building blocks into a sequence of steps. Depending on what Copilot in SharePoint supports on a site, both skill types can understand and summarize content, organize files and folders, and interact with SharePoint content such as lists. Their main differences are ownership, storage, and availability.

Note

Skills can't connect to external systems or execute custom code. A skill can only perform actions the user already has permission to do and doesn't expand access or introduce new capabilities beyond what Copilot in SharePoint provides.

## Where skills are stored

### Personal skill storage

Personal skills are stored in the skill owner's OneDrive and are available to the owner across supported Copilot in SharePoint experiences.

### Site skill storage

Site skills are stored as Markdown (.md) files in the site's **Agent Assets** library, under `/Agent Assets/Skills/<skill-name>/SKILL.md`. The site admin owns and manages them, while authorized site members can create or use them according to their SharePoint permissions.

You can create and manage site skills through chat. You can also review the underlying .md file directly if needed. If you edit the .md file directly, keep the format intact so Copilot in SharePoint can continue to interpret the skill correctly.

## Governance and permissions

Skills are a native capability within Copilot in SharePoint. There are no separate admin controls to turn skills on or off. By default, skills are available only within the first-party Copilot in SharePoint experience.

Neither personal nor site skills expand user permissions. A skill can act only on sites and content that the person running it already has permission to access.

### Personal skill governance

Personal skills are owned by the user and stored in the user's OneDrive. They are subject to applicable OneDrive retention, sensitivity, auditing, and lifecycle policies.

### Site skill governance

The site admin owns and manages site skills. The **Agent Assets** library is created and managed by the product and can't be deleted. You can, however, apply standard SharePoint file governance to site skill files (for example, permissions, retention, sensitivity labels, and auditing) the same way you would for other content stored in SharePoint.

By default, any user with **Edit** permissions on the site can create a site skill, and any user with **View** permissions can use it. If you need a different model, you can break permission inheritance on the **Agent Assets** library and apply more restrictive permissions.

## Prerequisites

1. Access to a SharePoint site where Copilot in SharePoint is available.
2. Permissions to the site: **Edit** to create skills, **View** to run skills.

Note

You don't need to activate or configure Agent Assets before creating a site skill. Copilot automatically activates Agent Assets and creates the **Agent Assets** library when you create the first site skill.

## Create a personal or site skill

1. Open the Copilot in SharePoint chat panel from a site page or a document library. Make sure the page isn't in edit mode.
2. Ask Copilot to create a skill. Copilot uses the built-in **Create skill** capability to guide you through the process.
3. Describe the reusable workflow, including the steps, inputs, and expected outputs.
4. Specify whether the skill should be personal or site-specific. If you don't specify a type, Copilot can help you choose based on the workflow and where you want to use it.

    Tip

    **Personal skill example:** "Create a personal skill that reviews documents using my preferred structure, checks headings and terminology, and recommends consistent formatting."

    **Site skill example:** "Create a site skill to review legal contracts to verify whether contract documents mention a lawyer ID in the **xxx-xxx** format (where **x** is an alphanumeric character). If a contract is not valid, add the document name to the **Invalid Contracts** list. Create the list with relevant columns if it doesn't exist."
5. Review the draft skill definition that Copilot returns. If needed, ask Copilot to refine the steps, inputs, or outputs.

    ![Screenshot of the draft skill definition returned by the agent for review.](sharepointonline/media/ai-in-sharepoint-skills/skill-draft-review.png)
6. Confirm that you want to save the skill.

## Run a skill

1. In the document library, select one or more files that you want the skill to work on. This step is optional but recommended for testing.
2. In chat, ask a question or give an instruction that matches the skill's purpose. Copilot in SharePoint automatically loads the right skills needed to execute the prompt.

    A personal skill can load for its owner across SharePoint sites. A site skill can load only on its associated site.
3. If needed, invoke the skill explicitly by name. For example, "Run *skill name* on the selected documents."
4. When Copilot runs your request, look for the skill indicator card in the chat UI to confirm that a skill was loaded. Provide any additional details Copilot asks for.

    ![Screenshot of a saved skill being used in the Copilot in SharePoint chat.](sharepointonline/media/ai-in-sharepoint-skills/using-saved-skill.png)

## Built-in skills

Copilot in SharePoint includes built-in skills that are available by default. These skills help you manage the skill lifecycle, including creating, checking, and improving skills. Microsoft creates and maintains built-in skills as part of Copilot in SharePoint.

Built-in skills aren't personal or site skills, and they aren't stored in OneDrive or the **Agent Assets** library. Users can't edit them directly, but they can extend their functionality by creating their own skills. The built-in **Create skill** capability guides users through creating personal and site skills.

To view the built-in skills currently available, enter `/skills` in the Copilot in SharePoint chat and review the skills listed under **Built-in skills**.