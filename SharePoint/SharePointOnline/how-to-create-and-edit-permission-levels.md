---
layout: Conceptual
title: How to create and edit permission levels - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/how-to-create-and-edit-permission-levels
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
ROBOTS: NOINDEX
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.collection: M365-collaboration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 53c86040-07fa-4ea7-bc55-34ee96b437fe
description: Learn how to create different permission levels for different groups of people within a site collection.
locale: en-us
document_id: db58d185-0ee0-84a4-1569-3ff03555f387
document_version_independent_id: 95bd3846-4772-6130-a552-0f31df69053d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/how-to-create-and-edit-permission-levels.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: how-to-create-and-edit-permission-levels
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/how-to-create-and-edit-permission-levels.md
platformId: 76764692-67e4-b5ac-c718-0424112a7f43
---

# How to create and edit permission levels - SharePoint in Microsoft 365 | Microsoft Learn

While SharePoint offers extensive customization options for site permissions, including custom permission levels, use the built-in SharePoint groups for communication site permissions. Manage team site permissions through the associated Microsoft 365 group. This approach simplifies administration. For more information about managing permissions in the SharePoint modern experience, see [Sharing and permissions in the SharePoint modern experience](modern-experience-sharing-permissions).

If you need to create custom permission levels, this article describes how.

## Create and edit permission levels

Permissions grant SharePoint users the ability to perform specific actions, such as editing items in a list or creating a site. However, you can't assign individual permissions to individual users in SharePoint. Instead, group related permissions together into a [permission level](understanding-permission-levels). Then, assign that permission level to a [SharePoint group](customize-sharepoint-site-permissions) that includes the people you're assigning permissions to.

SharePoint includes default [permission levels](understanding-permission-levels) that you can use, such as **Contribute** and **View Only**. If one of those default permission levels doesn't meet your needs, create a new permission level. It's easier to keep track of permission levels if you don't change the default permission levels.

## Create a permission level

Create and change permission levels on the **Permissions Levels** page.

To create or change permission levels, you must belong to a SharePoint group that includes the permission to Manage Permissions. By default, you have this permission if you belong to the Owners group or if you're a Site Collection Administrator.

1. On the top-level site of the site collection, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png).

- For a classic site, select **Site settings**. On the **Site Settings** page, in the **Users and Permissions** section, select **Site permissions**.
- For a modern site, select **Site permissions**, and then **Advanced permissions settings**.

1. On the **Permissions** tab, in the Manage group, choose **Permission Levels**.

    ![Choose Permission Levels page.](sharepointonline/media/8cb4fa7f-d94f-4e15-b1c0-7f46e331bc02.jpg)
2. On the **Permission Levels** page, choose **Add a Permission Level**.
3. On the **Add a Permission Level** page, enter the name and the description.
4. In the **Permissions** area, select the check boxes next to the list, site, and personal permissions that you want this permission level to include.
5. Select **Create**.

You can change any of the listed permission levels, except **Full Control** and **Limited Access**.

After you create the permission level, assign it to a [SharePoint group](customize-sharepoint-site-permissions).

## Create a permission level by copying an existing permission level

A quick way to create a new permission level is to copy an existing permission level. You might want to copy an existing permission level when it has permissions similar to what the new permission level needs. After you make the copy, you can add or remove the permissions you need for the new permission level.

### Copy a permission level

1. On the **Permission Levels** page, select the name of the permission level that you want to copy. Be sure to select the link; don't select the checkbox next to the name. For example, **Contribute**, as shown in the following figure.

    ![Choose a permission level.](sharepointonline/media/c38a93b7-2174-4fd1-8286-e9b52893e9e7.jpg)
2. On the **Edit Permission Level** page, select **Copy Permission Level**. This option is at the bottom of the page after the **Personal Permissions** section.

    ![Copy permission level button.](sharepointonline/media/a8e9d886-2245-467a-a599-9dac64032bf2.jpg)
3. On the **Copy Permission Level** page, type a name and description for the new permission level.
4. Choose which permissions you want to add or remove, and then select **Create**.

After you create the permission level, assign it to a [SharePoint group](customize-sharepoint-site-permissions).

## Make changes to a permission level

You can make the following changes to a permission level:

- Update the name or description
- Add or remove permissions

Don't change the default permission levels that come with SharePoint. You can't change the **Full Control** and **Limited Access** default permission levels.

### Change a permission level

1. On the **Permission Levels** page, select the name of the permission level you want to edit. Be sure to select the link; don't select the checkbox next to the name. For example, **Marketing**, as shown in the following figure.

    ![Choose a permission level called Marketing.](sharepointonline/media/03082e5f-8440-42ea-bf31-df2df08bd157.jpg)
2. On **Edit Permission Level**, you can:

- Change the description.
- Add or remove permissions to the level.

1. After you make your changes, select **Submit**.

You can delete any permission level, except for **Full Control** and **Limited Access**. Don't delete a default permission level.

To delete a permission level, on the **Permission Levels** page, select the check box next to the permission level that you want to delete, and then choose **Delete Selected Permission Levels**.

Important

You can create permission levels that don't grant the minimum required permissions. The modern user experience uses client-side rendering, which requires that all users have the "Use Remote Interfaces" permission. Removing "Use Remote Interfaces" from a permissions level results in Access Denied errors that either prevent features on a modern page from loading or prevent the entire modern page from loading, resulting in an Access Denied error for the user.

## Best practices for permission levels

Permission levels apply to a specific site collection. This condition means that any changes you make to a permission level affect the entire site collection. Therefore, follow these recommendations:

- **Don't edit default permission levels** If you change a default permission level, your changes affect all the built-in SharePoint groups within the site collection. It can also cause confusion if you have two site collections that have permission levels with the same name, but each contains a different set of permissions.
- **Don't delete default permission levels** If you delete a default permission level, you remove it from all built-in SharePoint groups that contain it within the site collection. This action can cause users assigned to those groups to lose critical permissions.
- **Assign permission levels to SharePoint groups** You can assign a permission level to a single SharePoint user, but it's easier to keep track of who has permissions to which sites if you assign permission levels to a SharePoint group, and add that individual to the group. This practice can also help site performance.