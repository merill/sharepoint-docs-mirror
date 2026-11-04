---
layout: Conceptual
title: Control notifications in the SharePoint mobile app - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/notifications
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2021-03-01T00:00:00.0000000Z
ms.reviewer: shahna
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
f1.keywords:
- CSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Strat_OD_admin
- M365-collaboration
- M365-sam
ms.custom: admindeeplinkSPO
search.appverid:
- ODB160
- MOE150
- MED150
- MBS150
- ODB150
- MET150
description: Allow users to receive notifications about SharePoint site activity.
locale: en-us
document_id: 9e17f3ec-9489-1ab0-2f73-4a16f9f87e17
document_version_independent_id: 2ff1ac04-2a4e-a5b8-d03d-dc4b03e0ce1e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/notifications.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: notifications
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/notifications.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/7ebba99b-05c3-4387-8883-f7bbf6632cb8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/006ab567-b18c-4cf1-9a25-c24daa46ede1
platformId: 82c20413-8b83-9243-c5ee-679916a49675
---

# Control notifications in the SharePoint mobile app - SharePoint in Microsoft 365 | Microsoft Learn

By default, SharePoint mobile app users can receive notifications about site activity. The service sends these notifications through the Firebase Cloud Messaging service for Android or the Apple Push Notification service for iOS. As a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) and [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365, you can turn off these notifications for all users for compliance purposes. If you allow these notifications, users can select to turn them off.

Currently, notifications are sent for the following activities:

- SharePoint news published (users receive these based on relevancy)
- Page comment (sent to the page author)
- Page comment reply (sent to the page author and the author of the comment that is being replied to)
- Page comment mention (sent to person @ mentioned)
- Page like (sent to the page author)

Other notifications might be added in the future.

Note

Notifications aren't available for the US government environments or Office 365 operated by 21Vianet (China).

## Allow or block notifications

1. Go to [**Settings** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185072), and sign in with an account that has [admin permissions](/en-us/sharepoint/sharepoint-admin-role) for your organization.
2. Select the **Notifications** setting for SharePoint.
3. Select or clear **Allow notifications**.

You can also control this setting in PowerShell by using [Set-SPOTenant -NotificationsInSharePointEnabled](/en-us/powershell/module/microsoft.online.sharepoint.powershell/set-spotenant).