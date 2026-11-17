---
layout: Conceptual
title: How shareable links work in OneDrive and SharePoint in Microsoft 365 - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/shareable-links-anyone-specific-people-organization
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-11-06T00:00:00.0000000Z
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
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 07652f98-406e-d7fc-3df7-27a991a7d2a6
---

# How shareable links work in OneDrive and SharePoint in Microsoft 365 - SharePoint in Microsoft 365 | Microsoft Learn

Sharing links determine who can open a file or folder when they receive its link and what they can do with the item. In OneDrive and SharePoint, each item has one **hero link**. A hero link allows users to share a single link for an item, then change the audience and permissions for that link without needing to create a new URL.

## Sharing with direct access and links

Users can share an item with specific people or security groups through **Add people**. This action grants direct access to the item. The item can appear in search results and is accessible through Copilot for selected users and security group members, subject to their permissions.

To share beyond a named set of recipients, users can change who the hero link works for under **File link settings**. A item has one hero link. Two people copying the hero link from the same item get the same link. Links shared by email or copied from the browser address bar work the same way for access, although the URLs might look different.

## Hero link audience scope

The audience *scope* determines who can use the hero link. Available scopes depend on the organization's sharing policies.

### Only people added to the file have access

At this scope, the link works for people who already have access, such as through a direct permission, a group, or the parent folder or site. It grants no additional access.

This scope is the usual starting point. The default can differ based on site settings and the parent folder.

### Anyone with the link

Anyone who receives the link can use it without signing in, including people outside the organization. Anyone can forward the link, and anonymous use can't be audited to a named user.

[![Screenshot of a diagram showing how an Anyone with the link sharing link can be passed from user to user.](sharepointonline/media/dmc-sharepointsharinglinks-anyone.png)](sharepointonline/media/dmc-sharepointsharinglinks-anyone.png#lightbox)

Selecting this scope doesn't make the content globally searchable or accessible through Copilot, or grant access to everyone. A person must receive and redeem the link by selecting it before the shared content becomes searchable for them.

### People in your organization with the link

The link works for people who sign in as members of your Microsoft 365 directory. They can forward it to other members, but it doesn't work for guests or people outside the organization.

[![Screenshot of a diagram showing how a People in your organization with the link sharing link can be passed from user to user inside the company.](sharepointonline/media/dmc-sharepointsharinglinks-peopleinyourorganization.png)](sharepointonline/media/dmc-sharepointsharinglinks-peopleinyourorganization.png#lightbox)

Selecting this scope doesn't grant organization-wide access or make the item available in search or Copilot for everyone in the organization. Access through the link is established when a recipient redeems it. Microsoft 365 experiences such as SharePoint, OneDrive, Outlook, or Microsoft Teams might redeem the link automatically for recipients.

## Link permissions and changes to access

While scope determines who can use the link, *permission* determines what they can do with the shared item. For a link with organization or anyone scope, users can choose **Can edit**, **Can view**, **Can't download**, or **Can review** (for supported file types). The same permission options are available for direct access.

**Can view** is the default when a user first allows access to an item through the hero link. Administrators can't configure a different default permission for the hero link. At **Only people added to the file have access**, no link permission is in effect because the link grants no access of its own.

Changing the scope or permission doesn't create a new URL. The change applies to links already sent, so narrowing the scope limits who can use those links.

A user's effective access is the highest permission granted by any source: direct access, a group, the parent folder or site, the hero link, or another sharing link. For example, a user with **Can edit** direct access can still edit the item when the hero link grants **Can view**. Reducing access requires changing each source that grants a higher permission.

## Default scope and folder settings

In SharePoint PowerShell, set the default audience scope for the hero link, referred to as the *main link*, with `DefaultMainLinkScope` on a site. For syntax and supported values, see [Set-SPOSite](/en-us/powershell/module/sharepoint-online/set-sposite).

A file inherits its folder's hero link settings until the file's own hero link is explicitly set or changed. After that, the file's hero link settings are independent.

Folder sharing also grants permissions to all files and subfolders inside the folder that the sharer has access to. Owners can block those automatic permission updates for an item. This setting is separate from setting that item's hero link audience.

## Additional sharing links

Users can create extra links for specific needs, such as setting an expiration date or a password. They can name these links to identify the task or audience. The sharing dialog lists them under **Other links**, along with links inherited from a parent folder.

Extra links can work for people in the organization, anyone with the link, or **Specific people**, which limits the link to named recipients inside or outside the organization. Available options depend on the organization's sharing policies.

Each extra link has its own audience and permission settings. Users can choose **Can edit**, **Can view**, **Can't download**, or **Can review**, where supported for the item and link type. Changing the hero link doesn't change or remove extra links.

Note

Links created before the hero link sharing experience continue to work and appear under **Other links**.

### Specific-recipient sharing links

For the **Specific people** sharing link, the user sharing an item enters the names or email addresses of the intended recipients. Recipients must authenticate as a specified person in the link. Forwarding it doesn't grant access to someone else, and the link can be removed to stop sharing through that link.

Teams and Outlook might show **People in this chat** or **People in this email**. These are specific-people links scoped to the recipients in that chat or email, not to everyone in the organization.

For users and security group members added to a specific-recipient link, the item can appear in search results and be accessible through Copilot, subject to their permissions. For files in a Microsoft Teams shared channel site, you can send these links only to people in the channel.