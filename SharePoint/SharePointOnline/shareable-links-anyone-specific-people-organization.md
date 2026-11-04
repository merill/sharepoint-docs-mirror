---
layout: Conceptual
title: How shareable links work in OneDrive and SharePoint in Microsoft 365 - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/shareable-links-anyone-specific-people-organization
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-08-12T00:00:00.0000000Z
ms.reviewer: 
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
f1.keywords: NOCSH
ms.topic: article
ms.service: sharepoint-online
ms.subservice: sync
ms.localizationpriority: medium
ms.collection:
- Strat_SP_admin
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
search.appverid: MET150
description: Learn about how shareable links work in OneDrive and SharePoint in Microsoft 365.
locale: en-us
document_id: ec933129-54c8-796e-0bb9-6079ef994c3e
document_version_independent_id: 9311492a-d99f-fc1d-d5d4-6f7e0f01fdc6
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/shareable-links-anyone-specific-people-organization.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: shareable-links-anyone-specific-people-organization
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/shareable-links-anyone-specific-people-organization.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
platformId: 07652f98-406e-d7fc-3df7-27a991a7d2a6
---

# How shareable links work in OneDrive and SharePoint in Microsoft 365 - SharePoint in Microsoft 365 | Microsoft Learn

When a user shares a file or folder in Microsoft 365, they create a shareable link with permissions to the item. There are three primary link types:

- "Anyone" links
- "People in your organization" links
- "Specific people" links

It's important for everyone to understand how sharing links work and which ones to use to maintain data security. This article describes different types of sharing links and includes links to more resources.

## "Anyone" links

*Anyone* links give access to the item to anyone who has the link. People using an *Anyone* link don't have to authenticate, and their access can't be audited.

![Diagram showing how anyone links can be passed from user to user.](sharepointonline/media/dmc_sharepointsharinglinks_anyone.png)

An *Anyone* link is a transferable, revocable secret key.

- It's transferable because it can be forwarded to others.
- It's revocable because you can revoke access for everyone who used the link by deleting it.
- It's secret because it can't be guessed or derived.

The only way to get access is to get the link, and the only way to get the link is for somebody to give it to you. *Anyone* links can't be used with files in a Microsoft Teams shared channel site.

Creating an *Anyone* link doesn't make the associated content appear in search results or make it accessible through Copilot. It also doesn't immediately grant access to the content to everyone. An *Anyone* link must be activated by clicking the link (redemption) before the shared content becomes searchable by the person who has the link.

## "People in your organization" links

*People in your organization* links work only for people inside your Microsoft 365 organization. They don't work for guests in the directory, only members.

![Diagram showing how people in my organization links can be passed from user to user inside the company.](sharepointonline/media/dmc_sharepointsharinglinks_peopleinyourorganization.png)

Like an *anyone* link, a *People in my organization* link is a transferable, revocable secret key. These links only work for people who are inside your Microsoft 365 organization. When somebody opens a *People in my organization* link, they need to be authenticated as a member in your directory. If they're not currently signed in, they're prompted to sign in.

Creating a *People in your organization* link doesn't make the associated file or folder appear in search results or make it accessible through Copilot. It also doesn't grant access to everyone within the organization. Creating this link doesn't provide organizational-wide access to the content. For individuals to access the file or folder, they must possess the link, and it needs to be activated through redemption (clicking it). A user redeems the link by selecting it.

If you send the link from the SharePoint or OneDrive Web UI, or by using email in Outlook or a chat message in Microsoft Teams, you automatically redeem it for individual recipients, up to a limit of 100. This feature isn't supported for group recipients, or for messages posted in Microsoft Teams channels. The link doesn't work for guests or other people outside your organization.

**Expiration of "People in your organization" links**

Administrators can configure expiration policies for *People in your organization* sharing links in SharePoint and OneDrive. When an expiration policy is enabled, newly created links get an expiration date and stop working after that date.

Existing *People in your organization* links aren't automatically modified when an expiration policy is enabled. However, when an existing link is accessed after the policy is in effect, the link is evaluated against the configured expiration limit using its original creation date. If the link exceeds the allowed age, it's treated as expired and can no longer be used to access the content.

When a sharing link expires, only the link is affected. The file or folder isn't deleted, and users who have access through other permissions can continue to access the content.

## "Specific people" links

*Specific people* links only work for the people that users specify when they share the item.

![Diagram showing how specific people links only work for the people specified.](sharepointonline/media/dmc_sharepointsharinglinks_specific.png)

A *Specific people* link is a nontransferable, revocable secret key. *Specific people* links don't work if they're opened by anybody other than the persons who are specified by the sender. Moreover, *Specific people* links make the associated file or folder appear in search results and make it accessible through Copilot for all user and security group members who are added to the sharing link.

*Specific people* links can be used to share with users in the organization and people outside the organization. In both cases, the recipient needs to authenticate as the user specified in the link. For files in a Microsoft Teams shared channel site, *Specific people* links can only be sent to others in the channel.