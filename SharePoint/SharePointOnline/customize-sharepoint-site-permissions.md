---
layout: Conceptual
title: Customize SharePoint site permissions - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/customize-sharepoint-site-permissions
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
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.collection:
- M365-collaboration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: b1e3cd23-1a78-4264-9284-87fed7282048
ms.custom:
- seo-marvel-apr2020
description: This article contains information on how to customize SharePoint site permissions. Learn how to create, manage, and delete groups in SharePoint.
locale: en-us
document_id: f9e8d0f1-f6a3-82c0-e46b-974e167fe5b1
document_version_independent_id: 22b0a6c2-2e90-34ab-c3c8-bd7ba721c791
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/customize-sharepoint-site-permissions.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: customize-sharepoint-site-permissions
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/customize-sharepoint-site-permissions.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 56def763-588b-9ebc-6e72-977fa8d1f930
---

# Customize SharePoint site permissions - SharePoint in Microsoft 365 | Microsoft Learn

This article covers advanced scenarios for customizing site permissions. Most organizations don't need these options. If you just want to share files or folders, see [Share SharePoint files or folders](https://support.microsoft.com/office/1fe37332-0f9a-4719-970e-d2578da4941c). If you want to share a site, see [Share a site](https://support.microsoft.com/office/958771a8-d041-4eb8-b51c-afea2eae3658).

While SharePoint offers extensive customization for site permissions, use the built-in SharePoint groups for communication site permissions and manage team site permissions through the associated Microsoft 365 group. For more information about managing permissions in the SharePoint modern experience, see [Sharing and permissions in the SharePoint modern experience](modern-experience-sharing-permissions).

If you need to customize SharePoint groups, this article describes how.

## Customize site permissions

A SharePoint group is a collection of users who all have the same set of permissions to sites and content. Instead of assigning permissions one person at a time, use groups to conveniently assign the same permission level to many people at once.

Note

To complete the following steps, you need a permission level that includes permissions to *Create Groups* and *Manage Permissions*. The **Full Control** level has both. For more information, see [Understanding permission levels in SharePoint](understanding-permission-levels).

### Create a group

1. On your website or team site, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and select **Site permissions**.
2. On the **Permissions** page, select **Advanced Permissions Settings**.
3. On the **Permissions** tab, select **Create Group**.
4. On the **Create Group** page, in the **Name** and **About me** boxes, type a name and description for this SharePoint group.
5. In the **Owner** box, specify a single owner of this security group.
6. In the **Group Settings** section, specify who can view and edit the membership of this group.
7. In the **Membership Requests** section, select the settings that you want for requests to join or leave the group. You can specify the email address to which requests should be sent.
8. In the **Give Group Permissions to this Site** section, choose a permission level for this group.
9. Select **Create**.

### Add users to a group

You can add users to a group at any time.

If you're on a [communication site](https://support.microsoft.com/office/use-the-sharepoint-standard-communication-showcase-and-blank-communication-site-templates-94a33429-e580-45c3-a090-5512a8070732), follow these steps:

1. Select **Site access**.

    ![Screenshot of site access for communication sites.](sharepointonline/media/customize-permissions/communication-site-add-member.png)
2. In the **Site access** dialog, enter the name or email address of the user or group that you want to add. When the name appears, choose the permission level from the dropdown.

    ![Screenshot of adding a member to a group dialog.](sharepointonline/media/add-user-to-a-group.png)
3. If you want to add more names, repeat these steps.
4. Enter a message to send to the new users in the **Add a message** box.
5. Select **Share**.

If you're on a [team site](https://support.microsoft.com/office/what-is-a-sharepoint-team-site-75545757-36c3-46a7-beed-0aaa74f0401e), follow these steps:

1. Select **members**.

    ![Screenshot of adding members for team sites.](sharepointonline/media/customize-permissions/team-site-add-member.png)
2. In the **Group membership** dialog, select **Add members**. Start typing the name of the user that you want to add. When the name appears, select it. You can add multiple users at once.

    ![Screenshot of adding members to a group dialog.](sharepointonline/media/customize-permissions/add-member-team-site.png)

To make a member an owner, add them as a member and then use the drop-down arrow in the member profile to make them an owner.

### Remove users from a group

1. On your website or team site, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**. On some pages, you might need to select **Site contents**, and then select **Site settings**.
2. Under **Users and Permissions**, select **People and Groups**.
3. Under **Groups**, select the name of the group that you want to remove users from.
4. Select the check boxes next to the users you want to remove, select **Actions**, and then select **Remove Users from Group**.
5. In the confirmation window, select **OK**.

### Grant site access to a group

1. On your website or team site, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and select **Site permissions**.
2. On the **Permissions** page, select **Advanced Permissions Settings**.
3. On the **Permissions** tab, select **Grant Permissions**.
4. In the **Share** dialog, type the name of the SharePoint group that you want to give access to.
5. By default, the **Share** dialog displays the message **Invite people to Edit** or **Invite people** with **Can edit** permissions. This message grants permissions in the SharePoint Members group. To choose a different permission level, select **Show options** and then choose a different SharePoint group or permission level under **Select a permission level** or **Select a group or permission level**. The drop-down box shows both groups and individual permission levels, like **Edit** or **View Only**.
6. Select **Share.**

### Delete a group

Caution

Don't delete any of the default SharePoint groups. Deleting default SharePoint groups can make the system unstable. Only delete groups that you created and no longer want to use.

1. On your website or team site, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**. On some pages, you might need to select **Site contents**, and then select **Site settings**.
2. Under **Users and Permissions**, select **People and Groups**.
3. On the **People and Groups** page, select the name of the SharePoint group that you want to delete.
4. Select **Settings**, and then select **Group Settings**.
5. At the bottom of the **Change Group Settings** page, select **Delete**.
6. In the confirmation window, select **OK**.

### Assign a new permission level to a group

If you customize a permission level or create a new permission level, you can assign it to groups or users.

1. On your website or team site, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**. On some pages, you might need to select **Site contents**, and then select **Site settings**.
2. On the **Site Settings** page, under **Users and Permissions**, select **Site Permissions**.
3. Select the check box next to the user or group to which you want to assign the new permission level.
4. On the **Permissions** tab, select **Edit User Permissions**.
5. On the **Edit Permissions** page, select the check box next to the name of the new permission level. If you select multiple permission levels, the permission level assigned to the group is the union of the individual permissions in the different levels. That is, if one level includes permissions (A, B, C), and the other level includes permissions (C, D), the new level for the group includes permissions (A, B, C, D).
6. Select **OK**.

Note

You can't modify permissions for the default SharePoint groups (Owners, Members, and Visitors) for Team sites that are connected to a Microsoft 365 group.

### Add, change, or remove a site admin

1. On the site, select **Settings**![Settings icon](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**. On some pages, you might need to select **Site contents**, and then select **Site settings**.
2. Under **Users and Permissions**, select **Site Collection Administrators**.
3. In the **Site Collection Administrators** box, do one of the following:

    - To add a site collection administrator, enter the name or user alias of the person you want to add.
    - To change a site admin, select the **X** next to the name of the person, and then enter a new name.
    - To remove a site admin, select the **X** next to the name of the person.
4. Select **OK**.

    Note

    To see the **Site Collection Administrators** link, you must be at least a [SharePoint Administrator](sharepoint-admin-role). This link isn't displayed to site owners.