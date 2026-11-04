---
layout: Conceptual
title: Restricted SharePoint Search - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/restricted-sharepoint-search
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-07-06T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.reviewer: ngrevious, yangpan, shsingar
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: administrator
ms.topic: concept-article
ms.service: sharepoint-online
ms.subservice: ai-copilot
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- M365-collaboration
- m365copilot
- magic-ai-copilot
- trust-pod
- M365-sam
description: A temporary solution that can help prevent some SharePoint sites from showing up in enterprise search and Copilot chat or agentic responses.
locale: en-us
document_id: 6b169cda-8456-66f8-cbbd-176277d95a98
document_version_independent_id: 5ab9a3d0-e324-1d48-2d3b-a697c6ad21ef
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/restricted-sharepoint-search.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: restricted-sharepoint-search
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/restricted-sharepoint-search.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
platformId: fb3ee31c-e37c-06fa-19d1-7c1ac47b6362
---

# Restricted SharePoint Search - SharePoint in Microsoft 365 | Microsoft Learn

Important

Restricted SharePoint Search is retiring. Starting July 31, 2026, new enablement is blocked. Use comprehensive data controls such as [Restricted Content Discovery](/en-us/sharepoint/restricted-content-discovery) (RCD) for content discoverability.

Restricted SharePoint Search is designed for customers of Microsoft Copilot Chat and agentic experiences. It's a short-term solution that gives your organization's administrators time to review and audit site and file permissions. It's not intended or scalable for long-term use. Comprehensive data security solutions are available, including [SharePoint Advanced Management](/en-us/sharepoint/advanced-management) and [Microsoft Purview](/en-us/purview/ai-microsoft-purview).

## What is Restricted SharePoint Search?

Restricted SharePoint Search is a setting that you, as a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [other Microsoft 365 administrator](/en-us/microsoft-365/admin/add-users/about-admin-roles), use to maintain a list of SharePoint sites (an "allow list") for which you check permissions and apply data governance. The allow list defines which SharePoint sites can be used in organization-wide search queries. As a temporary measure, it also applies to Copilot chat and agentic experiences.

By default, the Restricted SharePoint Search setting is turned off and the allow list is empty. If you turn on Restricted SharePoint Search, users can interact with files and content they own or previously accessed in Copilot.

## How to use Restricted SharePoint Search

Use Restricted SharePoint Search as a temporary measure to prevent certain content on SharePoint sites from being shared too widely. This feature lets you as an administrator decide which SharePoint sites appear in search results across your organization and Copilot chat or agentic experiences. However, it's important to note that Restricted SharePoint Search isn't a security boundary and doesn't change any permissions on SharePoint sites.

Restricted SharePoint Search doesn't guarantee that only sites on the allow list show up in search or in Copilot chat and agentic experiences. If a user recently accessed a site, or the site was shared with that user in Teams or Outlook, the site appears in the user's results and responses, even if it's not on the allow list.

**Recommended process**:

1. If you use Restricted SharePoint Search, use it to temporarily help limit results in search or Copilot chat and agentic experiences. Keep in mind that it's not intended to be a long-term solution.
2. Use [SharePoint Advanced Management](/en-us/sharepoint/advanced-management) to identify and remediate oversharing risks, such as broad access and unmanaged sharing.
3. Use [Microsoft Purview](/en-us/purview/ai-microsoft-purview) to apply data security and AI governance controls with sensitivity labels, data loss prevention (DLP), and auditing.
4. After you validate permissions and governance controls, disable Restricted SharePoint Search.
5. Notify Copilot agent owners and your IT team that Copilot and agentic responses use existing SharePoint permissions. Users' search and Copilot responses can change after Restricted SharePoint Search is disabled, so it's important to keep them informed.

## Why disable Restricted SharePoint Search after validation?

Restricted SharePoint Search is designed as a temporary measure, not a long-term solution. If you keep Restricted SharePoint Search enabled, the user experience is affected in the following ways:

- Restricted SharePoint Search limits to 100 sites, which isn't sustainable as your organization scales Copilot and agentic operations.
- Search results are limited to sites on the allow list, users' frequently visited sites, sites that users have permissions to, and users' recently accessed files. Restricted SharePoint Search affects the overall search experience, even for users who aren't using Copilot chat or agents.
- When Restricted SharePoint Search is enabled, Copilot has less information available to reference, which can affect its ability to provide accurate and comprehensive responses.

Disabling Restricted SharePoint Search enables Copilot chat and agentic experiences to rely on standard permission-based access, rather than a restricted hub-site scope. This configuration helps Copilot chat and agents retrieve SharePoint content with more consistency and accuracy, while still respecting the permissions set on SharePoint sites.

Neither Copilot nor Restricted SharePoint Search prevents users from accessing content they own or previously accessed.

## How does Restricted SharePoint Search work?

As a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [other Microsoft 365 administrator](/en-us/microsoft-365/admin/add-users/about-admin-roles), you can:

- Check the current status of Restricted SharePoint Search to see if it's enabled or disabled.
- Enable or disable Restricted SharePoint Search (it's disabled by default).
- [Curate the allowed list](restricted-sharepoint-search-allowed-list) by identifying the top 100 widely used sites.
- Add or remove sites from the allowed list by providing the site URL.
- Get the full list of sites in the allowed list.

Restricted SharePoint Search is off by default. If you decide to enable it, users who search for content or use Copilot chat and agentic experiences can expect responses to surface content from the following sources:

- An allowed list of curated SharePoint sites (with *up to 100 SharePoint sites*), honoring existing site permissions.
- Users' OneDrive files, chats, emails, and calendars they have access to.
- Files from users' frequently visited SharePoint sites.
- Files that were shared directly with users.
- Files that users viewed, edited, or created.

Note

- The allowed list limit of up to 100 SharePoint sites includes Hub sites, but not their associated sites. When you enable Hub sites, the associated sites of a Hub site are included in the allowed list, but they don't count towards the 100-site limit. This approach allows for greater flexibility while still adhering to the existing constraints.
- When you're picking Hub sites, make sure all the associated sites have proper permissions.
- The total number of files included from the last three bullet points (frequently visited sites, files shared directly with the user, and files the users viewed, edited, or created) is limited to the last 2,000 entities.

The following diagram shows an example of an HR Hub site with eight associated sites:

[![Diagram depicting a hub site with its associated sites.](sharepointonline/media/rss-hubsite-example.png)](sharepointonline/media/rss-hubsite-example.png#lightbox)

In the preceding diagram, all eight associated sites plus the HR Hub site are counted as one site in the allowed list.

### Example: Contoso Electronics before and after using Restricted SharePoint Search

Let's consider Alex Wilber, a marketing specialist at Contoso Electronics. Before Alex's organization uses Restricted SharePoint Search, Alex can see not only his own personal contents, like his OneDrive files, chats, emails, contents that he owns or visited, but also content from some sites that haven't undergone access permission review or Access Control Lists (ACL) hygiene, and doesn't have data governance applied. For example, Contoso Electronics has a budgeting site with important business information. Most people don't know about this site, so the site owner hasn't set up proper permissions and hasn't followed correct data governance process. The site might be open to some users who aren't allowed to see it, such as Alex. When Alex asks Copilot for some budgeting information, Copilot gets information from the budgeting site.

The IT administrator at Contoso Electronics sets up Restricted SharePoint Search to limit what sites can be searched through the allowed list. After reviewing reports, the IT administrator decides to exclude the budgeting site from the allowed list. But even though Restricted SharePoint Search is now turned on, Alex can still access things that he owns or has recently visited, or that are directly shared with him. He just can't access any other sites, unless the site is in the allowed list and he has permission to it. Now, when Alex asks Copilot the same questions about budgeting, Copilot chat and agentic experiences don't show information from that site.

From here, Contoso Electronics administrators plan to use [SharePoint Advanced Management](/en-us/sharepoint/advanced-management) and [Microsoft Purview](/en-us/purview/ai-microsoft-purview), and eventually, disable Restricted SharePoint Search.

Note

Site scoped searches aren't affected by this control. This control impacts [modern search](/en-us/microsoftsearch/get-started-search-in-sharepoint-online) and Copilot experiences.

## Frequently asked questions

### Can I use RSS for creating a "deny list" instead?

No, this capability isn't part of Restricted SharePoint Search. However, SharePoint Advanced Management offers a similar feature called [Restricted Access Control for SharePoint sites](/en-us/sharepoint/restricted-access-control). If you're not ready to use SharePoint Advanced Management, you can consider specifying whether to allow specific sites to show up in search results. For more information, see [Allow this site to appear in Search results](/en-us/sharepoint/make-site-content-searchable#show-content-on-a-site-in-search-results).

Note

If you turn off the "Allow this site to appear in Search results" setting, you block the site content from showing up in both the organization-wide search and the site specific search.

### Does Restricted SharePoint Search affect other services that don't depend on SharePoint, such as Exchange, To Do, Planner, Loop, etc.?

Yes, any product where Enterprise Search is enabled and could have SharePoint content and/or files as search results will be impacted.

### Does Restricted SharePoint Search affect other features based on the Microsoft Index, such as Purview or SharePoint Advanced Management features?

No, Restricted SharePoint Search won't affect any other features based on the Microsoft Index.

### How do I enable Restricted SharePoint Search?

You can enable Restricted SharePoint Search by using PowerShell scripts. For detailed steps, see [Enable or disable Restricted Search](/en-us/sharepoint/restricted-sharepoint-search-admin-scripts#enable-or-disable-restricted-search).

### After enabling RSS, how long does it take to go into effect?

RSS goes into effect within an hour after it's enabled.

### If I give the URL of a hub site, will it also include all of the child sites or sites associated hub sites with it? Do these other sites count towards the 100 sites in the allowed lists?

Only the hub site (the URL in the Allowed list) is included in the 100. The sub sites under the hub site aren't counted against the 100 limit but RSS is effective on the sub sites.