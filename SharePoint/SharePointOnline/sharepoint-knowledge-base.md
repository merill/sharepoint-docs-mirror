---
layout: Conceptual
title: Plan and set up SharePoint Knowledge Base (preview) - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/sharepoint-knowledge-base
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-10-23T00:00:00.0000000Z
ms.reviewer: lsuresh
ms.author: katelynhelms
author: katelynhelms
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: ai-copilot
ms.collection:
- M365-collaboration
- m365copilot
ms.localizationpriority: medium
search.appverid:
- MET150
description: Learn how SharePoint Knowledge Base (preview) gives a project team a single source of truth, and how to plan for licensing, Copilot Credits, and permissions.
locale: en-us
document_id: df8b5fa0-509b-74b2-80e2-440a445f6d7c
document_version_independent_id: 4512eddd-7fed-51a6-8a16-2b89febd161f
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/sharepoint-knowledge-base.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: sharepoint-knowledge-base
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/sharepoint-knowledge-base.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/4b132a0c-342a-42eb-91ff-8159e1ed413d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f2b71146-ce8e-46a8-9965-8aa8b3aa8235
platformId: fcd920cf-d4d3-2e8e-889e-fae0d8883b4b
---

# Plan and set up SharePoint Knowledge Base (preview) - SharePoint in Microsoft 365 | Microsoft Learn

SharePoint Knowledge Base gives a project team a single source of truth for its guidance, decisions, and procedures, organized as connected Knowledge Base (KB) pages on a SharePoint site. Copilot in SharePoint creates KB pages from the team’s sources, such as files, emails, and meetings, and updates them when people add sources or ask for changes. Where [Autopilot (preview)](https://blogs.microsoft.com/blog/2026/09/25/introducing-the-new-copilot-with-home-code-and-autopilot/) in the Microsoft 365 Copilot app is available, people can use it to create and update a knowledge base as well. People can also write KB pages themselves or import existing content. KB pages are Markdown files, so people can read them, and Copilot and agents can use them as context.

Important

SharePoint Knowledge Base is in Frontier preview and is rolling out to organizations in the [Frontier program](/en-us/microsoft-365/admin/manage/get-started-frontier). Features, availability, and billing terms might change before general availability.

## How SharePoint Knowledge Base works

A knowledge base is a specialized library of interlinked Markdown files on a SharePoint site. It uses SharePoint storage and governance, but it’s organized as connected KB pages instead of files. People can add a knowledge base to any SharePoint site, including sites connected to Teams channels and Microsoft 365 groups.

| Component | What to know |
| --- | --- |
| **Knowledge base** | A specialized library on a SharePoint site. By default, a knowledge base uses its site’s permissions, so site members can edit it and site visitors can read it. |
| **KB pages** | Markdown (.md) files that people read and edit in SharePoint. The Visual editor and the Source editor work on the same KB page. Page properties are stored as YAML frontmatter, and version history depends on the library’s versioning settings. People with edit access can coauthor and comment on KB pages with other people or an agent. |
| **Knowledge Base skill** | A built-in skill in Copilot in SharePoint (knowledge-base-management) that creates KB pages from sources, adds sources, updates KB pages, checks a knowledge base’s health, and answers questions. It’s turned on automatically, so you don’t need to enable it. |
| **Autopilot** (where available) | In organizations that have Autopilot in the Microsoft 365 Copilot app, people can ask Autopilot to create, update, and answer questions about a knowledge base. Autopilot uses the Knowledge Base skill and works with the same knowledge base that people open in SharePoint. |

People can create a knowledge base in three ways:

- **With Copilot in SharePoint**: People describe the knowledge base they want and include links to their sources, such as files and lists in OneDrive and SharePoint, emails, and meetings. Copilot creates KB pages from those sources, organized by topic.
- **With Autopilot**: Where available, people ask Autopilot in the Microsoft 365 Copilot app to create a knowledge base on a SharePoint site.
- **Manually**: From **+ New** on a SharePoint site or **Build** on the app bar, people start with a blank knowledge base or import Markdown files, a Confluence space, or Classic wiki pages.

After a knowledge base is created, it changes only when people ask Copilot in SharePoint or Autopilot to update it, edit it directly, or import content into it. KB pages don’t update automatically when their sources change, and each import is a one-time copy.

## Prerequisites

During the preview, ensure that your organization and users meet these requirements.

| Requirement | Details |
| --- | --- |
| **Frontier program** | Knowledge Base is rolling out to organizations in the Frontier program. Enroll the people who use Knowledge Base in Frontier, as described in Step 1. |
| **Usage-based billing** | During the preview, Knowledge Base is available only to users who are enabled for usage-based billing through a spending policy in the Microsoft 365 admin center, as described in Step 2. |
| **Microsoft 365 Copilot license** | Required to use Copilot in SharePoint, including to ask Copilot questions about KB page content. |
| **Site permissions** | To create a knowledge base, people need permission to create content on the site. To write and edit KB pages, they need permission to edit the knowledge base (by default, site members). To read a knowledge base, they need permission to view its KB pages. |
| **Copilot in SharePoint on the site** | Copilot-assisted tasks need Copilot in SharePoint to be available on the site where the knowledge base lives. For details, go to Step 3. |
| **Autopilot** (optional) | Autopilot is in preview, is available to a limited number of organizations, and rolls out on a separate schedule. |

## Licensing and Copilot Credits

Knowledge Base is currently available only to users enabled for [usage-based billing](/en-us/microsoft-365/copilot/usage-based-billing-manage-copilot-credits).

| Task | What’s required |
| --- | --- |
| Create a knowledge base with Copilot in SharePoint | Copilot Credits |
| Add sources, check for source updates, update KB pages, or check a knowledge base’s health with Copilot | Copilot Credits |
| Create or update a knowledge base with Autopilot | Copilot Credits |

### What users see

- Before Copilot in SharePoint continues with a task that uses credits, it asks the user to approve the credit use.
- After a task, users can enter `/cost` to see how many credits the task used.
- If credits aren’t available, Copilot explains what it can’t complete. The Knowledge Base skill stays visible, and people can still read the knowledge base.

## Set up Knowledge Base for your organization

During the preview, make Knowledge Base available by enrolling people in Frontier and enabling them for usage-based billing. The Knowledge Base skill in Copilot in SharePoint is turned on automatically.

### Step 1: Enroll users in Frontier

Enroll the people who’ll use Knowledge Base in the Frontier program. You can turn on Frontier access for all users or for specific users and groups. For steps, go to [Get started with the Microsoft Frontier Program](/en-us/microsoft-365/admin/manage/get-started-frontier).

### Step 2: Enable usage-based billing

For steps, see [Set up usage-based billing for Copilot Credits](/en-us/microsoft-365/copilot/usage-based-billing-copilot-credits-setup). If you already have spending policies, check whether they automatically include new agents and services as they become available.

### Step 3: Check where Copilot in SharePoint is available

Copilot-assisted Knowledge Base tasks run in Copilot in SharePoint. For more about where Copilot in SharePoint is available, go to [Get started with Copilot in SharePoint](copilot-in-sharepoint-get-started).

### Step 4: Prepare knowledge base owners

Identify the people who build and maintain knowledge bases, and share the support articles with them. Ask them to review the known limitations before they start.

### Step 5: Monitor Copilot Credit usage

Use the **Cost management** dashboard in the Microsoft 365 admin center to review Copilot Credit consumption by spending policy, user, group, agent, and service. Adjust limits and alerts as adoption grows. For details, see [Understand usage-based billing and cost management for Copilot Credits](/en-us/microsoft-365/copilot/usage-based-billing-overview-copilot-credits).

## Plan permissions and access

Knowledge bases use SharePoint site permissions. Readers can open only content they have access to, and Copilot works within each user’s license and permissions.

| Scenario | How access works |
| --- | --- |
| Edit a knowledge base | By default, site members can edit the knowledge base. |
| Read the whole knowledge base | A site owner adds people as site visitors. Site access can include more than the knowledge base. |
| Share a KB page | People can share individual KB pages and their subpages, but not the whole knowledge base. Sharing a KB page doesn’t give access to other KB pages, linked sources, or assets. |
| Open a cited source | A citation or link doesn’t grant access to its source. Readers need their own access to the original content. |

Tip

Create each knowledge base on a site whose entire audience should see everything in it. If a knowledge base needs a narrower audience than its site, consider creating it on a separate site.

## Protect sensitive information

Caution

Everyone who can access the knowledge base can see content added from a source, including people who can't open the source. KB pages don't inherit permissions from their sources.

- **Sensitivity labels**: KB pages don't support file-level sensitivity labels, and labels on source files don't carry over to KB pages. Before people add sensitive content, ensure that the site provides the protections your organization requires.
- **Imports**: Source permissions and file sensitivity labels don't carry over during an import. Imported KB pages use the destination knowledge base's SharePoint permissions.
- **Source changes and removals**: KB pages don't update automatically when their sources change or are removed, and removing a source doesn't remove guidance taken from it. Ask knowledge base owners to review the KB pages that used a changed or removed source.
- **Search and Copilot**: People can find KB pages in SharePoint and Microsoft 365 search, and Microsoft 365 Copilot Chat might use KB pages that a person has access to in its answers. Search results can also include source content.

## Plan content migration

Knowledge base is currently available only to users enabled for usage-based billing. People need permissions before they can import existing content into a knowledge base. Each import is a one-time copy that isn’t synchronized with its source.

| Source | What's brought over | What to plan for |
| --- | --- | --- |
| **Markdown files and folders** | Individual .md files, or a folder with its file hierarchy | Images that the files reference aren't copied. Renaming another file type to .md doesn't convert it. |
| **Confluence space** | Supported text, headings, lists, code, common tables, links, page hierarchy, images, and attachments, from an HTML export ZIP file | Macros, layouts, and complex tables might be simplified. Comments, reactions, version history, permissions, analytics, and users and groups might not be imported. Review the migration report for failures and warnings. |
| **SharePoint Classic wiki** | Classic wiki pages from a **Site Pages** library | Other classic pages, publishing layouts, blogs, and custom pages aren't supported. The source and destination must be in the same Microsoft 365 organization and geolocation. Web parts, custom scripts, CSS, page-level permissions, and full version history aren't migrated. Review the import report to see which pages need attention. |

Important

For large libraries, migrate in smaller batches and review each result before you continue. Don't edit the source content or start another import into the same destination until the current import finishes. Retrying an interrupted import can create duplicate content.

For steps, see [Import content into a SharePoint Knowledge Base (preview)](https://support.microsoft.com/sharepoint/knowledge-base/import-content-into-knowledge-base).

## Known limitations during the preview

Share these limitations with knowledge base owners before they start:

- **File batches**: Adding many files at once with Copilot or Autopilot can be slow or might not finish. Add 10 or fewer files per request. This recommendation isn't a limit on the size of a knowledge base.
- **Copilot sessions**: Copilot in SharePoint stops if a person leaves the session before an action finishes. They can start a new session and ask whether there's unfinished work on the knowledge base.
- **Simultaneous updates**: Copilot in SharePoint and Autopilot don't support more than one update on the same knowledge base at the same time.
- **Manual edits**: Updates from Copilot in SharePoint or Autopilot can reverse edits that people made or recreate deleted KB pages.
- **Renamed pages**: Renaming or moving a KB page manually can break links to it from other KB pages.
- **Sharing**: People can't share a whole knowledge base. They share individual KB pages and their subpages.
- **Sensitivity labels**: KB pages don't support file-level sensitivity labels.
- **Updates**: There are no automated or scheduled updates. Updates happen only when someone asks.

For workarounds, go to [Get started with SharePoint Knowledge Base (preview)](https://support.microsoft.com/sharepoint/knowledge-base/get-started-with-sharepoint-knowledge-base).

## Help users get started with Knowledge Base

Share these Microsoft Support articles with site owners, knowledge base owners, and readers.

| Article | Best for |
| --- | --- |
| [Get started with SharePoint Knowledge Base (preview)](https://support.microsoft.com/sharepoint/knowledge-base/get-started-with-sharepoint-knowledge-base) | Everyone. Explains what a knowledge base is, what's required, what's supported, and what the known limitations are. |
| [Create and update a Knowledge Base with Copilot in SharePoint (preview)](https://support.microsoft.com/sharepoint/knowledge-base/create-update-knowledge-base-with-copilot) | Knowledge base owners who use Copilot to create KB pages from sources, add sources, and check a knowledge base's health. |
| [Create and update a SharePoint Knowledge Base with Autopilot (preview)](https://support.microsoft.com/sharepoint/knowledge-base/create-update-knowledge-base-with-autopilot) | People in organizations that have Autopilot in the Microsoft 365 Copilot app. |
| [Create and edit a SharePoint Knowledge Base manually (preview)](https://support.microsoft.com/sharepoint/knowledge-base/create-edit-knowledge-base-manually) | Authors who create a knowledge base from **+ New** or **Build** and write KB pages in the Visual editor or Source editor. |
| [Import content into a SharePoint Knowledge Base (preview)](https://support.microsoft.com/sharepoint/knowledge-base/import-content-into-knowledge-base) | Teams that bring in Markdown files, a Confluence space, or Classic wiki pages. |
| [Find information and collaborate on a SharePoint Knowledge Base (preview)](https://support.microsoft.com/sharepoint/knowledge-base/find-information-collaborate-knowledge-base) | Readers and contributors who find KB pages, ask questions, comment, view version history, and share KB pages. |

## Frequently asked questions

### Why can't people see the option to create a knowledge base?

Check that they're enrolled in Frontier and that they have permission to create content on the site. After you turn on Frontier access, it might take up to three hours for Frontier features to appear. For Copilot-assisted tasks, also make sure that Copilot in SharePoint is available on the site.

### Do I need to turn on the Knowledge Base skill?

No. The Knowledge Base skill is built in to Copilot in SharePoint and is turned on automatically. It stays visible even when a person doesn't have Copilot Credits. In that case, Copilot explains what it can't complete.

### Can I choose who can use Knowledge Base?

During the preview, Knowledge Base is available to people who are enrolled in Frontier.

### Can people add a knowledge base to a site that’s connected to Teams?

Yes. People can add a knowledge base to any SharePoint site, including sites connected to Teams channels and Microsoft 365 groups.

### Do knowledge bases stay in sync with their sources?

No. KB pages change only when someone asks Copilot in SharePoint or Autopilot to update them, or edits them directly. Each import is a one-time copy.

## Related information

- [Get started with Copilot in SharePoint](copilot-in-sharepoint-get-started)
- [Get started with the Microsoft Frontier Program](/en-us/microsoft-365/admin/manage/get-started-frontier)
- [Set up usage-based billing for Copilot Credits](/en-us/microsoft-365/copilot/usage-based-billing-copilot-credits-setup)
- [Managing AI experiences enabled by usage-based billing](/en-us/microsoft-365/copilot/usage-based-billing-manage-copilot-credits)
- [Introducing a team knowledge base, curated by Copilot and agents](https://techcommunity.microsoft.com/blog/spblog/introducing-a-team-knowledge-base-curated-by-copilot-and-agents/4564203)
- [Get started with SharePoint Knowledge Base (preview)](https://support.microsoft.com/sharepoint/knowledge-base/get-started-with-sharepoint-knowledge-base)