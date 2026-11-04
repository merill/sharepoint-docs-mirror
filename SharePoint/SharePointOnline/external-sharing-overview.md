---
layout: Conceptual
title: Overview of external sharing in SharePoint and OneDrive in Microsoft 365 - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/external-sharing-overview
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-05-07T00:00:00.0000000Z
ms.reviewer: srice
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
f1.keywords:
- CSH
ms.topic: concept-article
ms.custom:
- quickshare
- o365p_enablespextluser
- O365P_AddSPExtlUser
- O365M_EnableSPExtlUser
- O365E_EnableSPExtlUser
- seo-marvel-apr2020
- Adm_O365
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Strat_OD_share
- M365-collaboration
search.appverid:
- SPO160
- MOE150
- MED150
- MBS150
- BSA160
- BCS160
- GSP150
- MET150
ms.assetid: c8a462eb-0723-4b0b-8d0a-70feafe4be85
customer-intent: As a SharePoint Administrator, I want to understand the external sharing options in SharePoint and OneDrive so that I can securely collaborate with people outside my organization.
description: Learn about the external sharing options in SharePoint and OneDrive in Microsoft 365. These options allow users in your organization to share content with people outside the organization.
locale: en-us
document_id: 6cadc974-5434-4647-6480-996c1e40a2f8
document_version_independent_id: 7953c446-e5ac-6a46-4ab4-7acd4b75f3b0
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/external-sharing-overview.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: external-sharing-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/external-sharing-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: b19ad0d3-f2aa-510a-ba5d-f8a8c9a93bef
---

# Overview of external sharing in SharePoint and OneDrive in Microsoft 365 - SharePoint in Microsoft 365 | Microsoft Learn

Note

As of June 2024, invitations sent through the legacy SharePoint Invitation Manager no longer grant access. Users must reshare documents to generate valid invitations.

External sharing in SharePoint and OneDrive allows users to share content with people outside your organization, such as partners, vendors, clients, or customers. You can also use external sharing to share between licensed users on multiple Microsoft 365 subscriptions. External sharing in SharePoint is part of [secure collaboration with Microsoft 365](/en-us/microsoft-365/solutions/setup-secure-collaboration-with-teams). Also see [Overview of external collaboration options in Microsoft 365](/en-us/microsoft-365/enterprise/external-guest-access).

Important

Trial tenants can use SharePoint's robust collaboration features, but the scope of external sharing is restricted compared to licensed tenants. This restriction helps prevent potential abuse and ensures a safe experience for all users.

Include external sharing as part of your overall permissions planning for SharePoint and OneDrive. This article describes what happens when users share, depending on what they're sharing and with whom.

If you want to get straight to setting up sharing, choose the scenario you want to enable:

- [Collaborate with guests on a document](/en-us/Office365/Enterprise/collaborate-on-documents)
- [Collaborate with guests in a site](/en-us/Office365/Enterprise/collaborate-in-a-site)
- [Collaborate with guests in a team](/en-us/Office365/Enterprise/collaborate-as-a-team)

(If you're trying to share a file or folder, see [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) or [Share SharePoint files or folders in Microsoft 365](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c).)

Note

External sharing is turned on by default for your entire SharePoint and OneDrive environment. You might want to [turn it off globally](turn-external-sharing-on-or-off) before people start using sites or until you know exactly how you want to use the feature.

### How do SharePoint and OneDrive integrate with Microsoft Entra B2B?

SharePoint and OneDrive use two external sharing models:

- SharePoint external authentication
- SharePoint and OneDrive integration with Microsoft Entra B2B

When you use Microsoft Entra B2B integration, Microsoft Entra external collaboration settings, such as [guest invite settings and collaboration restrictions](/en-us/azure/active-directory/external-identities/external-collaboration-settings-configure), apply.

The following table shows the differences between the two sharing models.

| Sharing method | What happens when sharing files and folders? | What happens when sharing sites? |
| --- | --- | --- |
| SharePoint external authentication(Microsoft Entra B2B integration not enabled) | No guest account created\*Microsoft Entra settings don't apply | N/A(Microsoft Entra B2B always used) |
| Microsoft Entra B2B integration enabled | Guest account always createdMicrosoft Entra settings apply | Guest account always createdMicrosoft Entra settings apply |

\*A guest account might already exist from another sharing workflow, such as sharing a team, in which case it's used for sharing.

For information on how to enable or disable Microsoft Entra B2B integration, see [SharePoint and OneDrive integration with Microsoft Entra B2B](sharepoint-azureb2b-integration).

## How do external sharing settings work?

SharePoint has external sharing settings at both the organization level and the site level (previously called the "site collection" level). To allow external sharing on any site, you must allow it at the organization level. You can then restrict external sharing for other sites. If a site's external sharing option and the organization-level sharing option don't match, the most restrictive value always applies. OneDrive sharing settings can be the same as or more restrictive than the SharePoint settings.

Whichever option you choose at the organization or site level, the more restrictive functionality is still available. For example, if you choose to allow unauthenticated sharing by using "Anyone" links, users can still share with guests, who sign in, and with internal users.

Note

Even if your organization-level setting allows external sharing, not all new sites allow it by default. See [Default site sharing settings](/en-us/microsoft-365/solutions/microsoft-365-guest-settings#default-site-sharing-settings) for more information.

## What are the security and privacy considerations?

If you have confidential information that you shouldn't share externally, store it in a site that has external sharing turned off. Create extra sites as needed for external sharing. This approach helps you manage security risk by preventing external access to sensitive information.

Note

To limit *internal* sharing of contents on a site, you can prevent site members from sharing, and enable access requests. For info, see [Set up and manage access requests](https://support.office.com/article/94B26E0B-2822-49D4-929A-8455698654B3).

When users share a folder with multiple guests, the guests can see each other's names in the Manage Access panel for the folder (and any items within it).

## How do I share Microsoft 365 group-connected team sites?

When you or your users create Microsoft 365 groups (for example in Outlook, or by creating a team in Microsoft Teams), you also create a SharePoint team site. Admins and users can also create team sites in SharePoint, which creates a Microsoft 365 group. For group-connected team sites, the group owners are site owners, and the group members are site members. In most cases, you want to share these sites by adding people to the Microsoft 365 group. However, you can share only the site.

Important

It's important that all group members have permission to access the team site. If you remove the group's permission, many collaboration tasks (such as sharing files in Teams chats) won't work. Only add guests to the group if you want them to access the site. For info about guest access to Microsoft 365 groups, see [Manage guest access in Groups](/en-us/office365/admin/create-groups/manage-guest-access-in-groups).

## What happens when users share content?

When users share with people outside the organization, an invitation is sent to the person in email, which contains a link to the shared item.

Because these guests don't have a license in your organization, they're limited to basic collaboration tasks:

- They can use Office.com for viewing and editing documents. If your plan includes Office Professional Plus, they can't install the desktop version of Office on their own computers unless you assign them a license.
- They can perform tasks on a site based on the permission level that you give them. For example, if you add a guest as a site member, they have Edit permissions and they can add, edit, and delete lists. They can also view, add, update, and delete list items and files.
- They can see other types of content on sites, depending on the permissions you give them. For example, they can navigate to different subsites within a shared site. They can also do things like view site feeds.

If your authenticated guests need greater capability such as OneDrive storage or creating a Power Automate flow, you must assign them an appropriate license.

## How do I stop sharing?

To stop sharing with guests, remove their permissions from the shared item or remove them as a guest in your directory.

To stop sharing with people who have an *Anyone* link, go to the file or folder that you shared and delete the link or turn off *Anyone* links for the site.

[Learn how to stop sharing an item](https://support.office.com/article/0a36470f-d7fe-40a0-bd74-0ac6c1e13323)

## Need more help?

![Ask a question](/en-us/office/media/icons/pngs/users-group-blue-32.png) If you have technical questions about this topic, you might find it helpful to post them on the [SharePoint discussion forum](https://social.technet.microsoft.com/Forums/sharepoint/home?forum=onlineservicessharepoint). It's a great resource for finding others who have worked with similar issues or who have encountered the same situation.