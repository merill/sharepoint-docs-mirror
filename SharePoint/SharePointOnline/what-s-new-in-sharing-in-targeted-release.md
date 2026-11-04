---
layout: Conceptual
title: Secure external sharing in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/what-s-new-in-sharing-in-targeted-release
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2024-04-24T00:00:00.0000000Z
ms.reviewer: srice
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords: NOCSH
ms.topic: article
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Strat_SP_admin
- M365-collaboration
search.appverid:
- SPO160
- MET150
ms.assetid: cc78357c-6d48-499c-9cc7-dae447d0d391
description: In SharePoint, if you share with a user who isn't in the directory, they're sent a one-time code that they can use to verify their identity.
locale: en-us
document_id: f75d2b5a-bc14-e0f3-1269-716383939212
document_version_independent_id: 879c8636-ab9a-0440-039a-f3eac8d41a1f
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/what-s-new-in-sharing-in-targeted-release.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: what-s-new-in-sharing-in-targeted-release
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/what-s-new-in-sharing-in-targeted-release.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 1eb9bad2-2604-a37e-8097-06ef6de61b85
---

# Secure external sharing in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn

In SharePoint, if you share with a person who isn't in the directory, they're sent a one-time code that they can use to verify their identity.

This article describes the current default one-time-passcode experience. However, we recommend that you enable [SharePoint and OneDrive integration with Microsoft Entra B2B](sharepoint-azureb2b-integration), which replaces this experience.

Recipients of secure external sharing who also use Microsoft 365 in their organization can sign in using their work or school account to access the document. After they enter the one-time passcode for verification the first time, they authenticate with their work or school account and have a guest account created in the host's organization. IT admins can manage them like any other guest account in their directory.

Guest accounts are used for sharing sites, and you can always add guests to your directory if you need to give them access to more than just a file or folder.

The following table shows the differences between sharing with people who have guest accounts and with ad hoc external recipients.

| - | Guest account | Ad hoc external recipient |
| --- | --- | --- |
| Can access shared files and folders | Yes | Yes |
| Verify access by... | Signing in to Microsoft 365 | Entering a time-sensitive and single-use code sent to the email address that the file or folder was share with |
| Actions are audited | Yes | Yes |
| Can have friendly name | Yes | Friendly name is the email address that the file or folder was shared with |
| Can be Group members | Yes | No |
| Can edit in Word, Excel, PowerPoint, or other Microsoft 365 apps | Yes | No |
| Access controlled by Microsoft Entra Conditional Access policies | Yes | No |

When you use the Share dialog box to share with "specific people" and the recipients are all outside the organization, then a secure link is created and the specified email addresses are secured, or added, to the link. This appears in audit logs in the following ways.

Note

If the UserType property of a User object is "guest", the user is outside of your organization but may be an ad hoc external recipient that does not have a guest account.

Note

Auditing operations related to sharing invitations can still appear in situations when SharePoint items other than files and folders are shared with guests (for example, when you share a SharePoint site with guests).

| Operation | Description |
| --- | --- |
| SecureLinkCreated | A link that only works for specific people was created. It's usually followed by a series of AddedToSecureLink operations, which signify the users who were secured to the link. The value in the **Detail** column for this activity identifies the UniqueSharingId for this link, which can be used to match against future AddedToSecureLink and RemovedFromSecureLink operations. |
| SecureLinkDeleted | A link that only works for specific people was deleted. It's usually preceded by a series of RemovedFromSecureLink operations, which signify the users who used to be secured to the link. The value in the **Detail** column for this activity identifies the UniqueSharingId for this link, which can be used to match against future AddedToSecureLink and RemovedFromSecureLink operations. |
| AddedToSecureLink | A link that only works for specific people was secured to a user. The value in the **Detail** column for this activity identifies the name or email of the user the link was secured to and whether this user is a guest. The value also has a UniqueSharingId column that identifies the link they were secured to. |
| RemovedFromSecureLink | A user was removed from a link that only works for specific people. The value in the **Detail** column for this activity identifies the name or email of the user the link was previously secured to and whether this user is a guest. The value also has a UniqueSharingId column that identifies the link they were secured to. |