---
layout: Conceptual
title: Turn on OneDrive file activity notifications - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/turn-on-external-sharing-notifications
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-04-07T00:00:00.0000000Z
ms.reviewer: sstewart
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
f1.keywords:
- CSH
ms.topic: how-to
ms.service: onedrive
ms.localizationpriority: medium
ms.custom:
- admindeeplinkSPO
- onedrive-toc
ms.collection:
- Strat_OD_admin
- M365-collaboration
search.appverid:
- ODB160
- MOE150
- MED150
- MBS150
- ODB150
- MET150
ms.assetid: b640c693-f170-4227-b8c1-b0a7e0fa876b
description: Allow users to receive notifications about file activity in OneDrive and SharePoint.
locale: en-us
document_id: 0e1da1b7-17f0-ca81-37aa-3af522094f97
document_version_independent_id: 9cc8d249-3b53-8fff-ca6f-085f969c268b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/turn-on-external-sharing-notifications.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: turn-on-external-sharing-notifications
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/turn-on-external-sharing-notifications.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
2PlusCloud:
- M365
- Azure
- Power
__autotagging_hash:
- 6DF569FF4B192C739745B6368E8579E198B2F6510E3B2D74E9DE68C308B1BD4F
platformId: 4a6bf9b6-7ff0-00cd-fa60-f343fa443264
---

# Turn on OneDrive file activity notifications - SharePoint in Microsoft 365 | Microsoft Learn

By default, users receive notifications about file activity in OneDrive and SharePoint. These notifications appear across apps and devices. For example, the service sends notifications through the Firebase Cloud Messaging service to the Office mobile app for Android or the Apple Push Notification service to the Office mobile app for iOS. It also sends notifications to the OneDrive sync app for Windows or Mac. As a global or SharePoint admin in Microsoft 365, you can turn off these notifications for all users for compliance purposes. If you allow these notifications, users can select to turn them off app by app where they don't want them.

Note

Currently, the service sends notifications to users when files are shared with them. Later, it sends notifications when people @mention the user in a comment. Other notifications might be added in the future.

## Allow or block notifications

1. Go to [**Settings** in the new SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185072), and sign in with an account that has [admin permissions](/en-us/sharepoint/sharepoint-admin-role) for your organization.
2. Select the **Notifications** setting for OneDrive.
3. Select or clear **Allow notifications**.

You can also control this setting in PowerShell by using [Set-SPOTenant -NotificationsInOneDriveForBusinessEnabled](/en-us/powershell/module/microsoft.online.sharepoint.powershell/set-spotenant).

The **Notifications** page of the OneDrive admin center includes three other settings under **Email OneDrive owners when**:

- Other users invite more external users to shared files. You can control this setting by using [Set-SPOTenant -NotifyOwnersWhenItemsReshared](/en-us/powershell/module/microsoft.online.sharepoint.powershell/set-spotenant).
- External users accept invitations to access files. (This setting no longer works for the new sharing experience that appears in most places.)
- An anonymous access link is created or changed. You can control this setting by using [Set-SPOTenant -OwnerAnonymousNotification](/en-us/powershell/module/microsoft.online.sharepoint.powershell/set-spotenant).