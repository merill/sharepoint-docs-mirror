---
layout: Conceptual
title: Restore deleted items from the site collection recycle bin - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/restore-deleted-items-from-site-collection-recycle-bin
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
description: Learn how to manage the SharePoint Site Collection recycle bin for SharePoint Online.
ms.author: jillth
author: JillTh
manager: jmcdowe
ms.reviewer: 
audience: Admin
ms.topic: how-to
ms.service: sharepoint-online
ms.date: 2026-08-28T00:00:00.0000000Z
locale: en-us
document_id: a2e62437-f83b-dd2d-ca9a-d43fe445544a
document_version_independent_id: 471ff1f2-d31a-23b5-7389-63894ffb3806
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/restore-deleted-items-from-site-collection-recycle-bin.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: restore-deleted-items-from-site-collection-recycle-bin
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/restore-deleted-items-from-site-collection-recycle-bin.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: b6034cb9-90aa-d2c9-87d1-aa61ae60865b
---

# Restore deleted items from the site collection recycle bin - SharePoint in Microsoft 365 | Microsoft Learn

When you delete items (including OneDrive files) from a SharePoint site, they're sent to the site Recycle Bin (also called the first-stage Recycle Bin), from where you can restore them if you need to. When you delete items from a site Recycle Bin, they're sent to the site collection Recycle Bin (also called the second-stage Recycle Bin). The first-stage Recycle Bin contributes to the storage-used metric while the second-stage Recycle Bin does not.

Note

Web items (subsites) go directly to the second-stage Recycle Bin and still count toward the storage-used metric. The quota is returned when the web items are purged from the second-stage Recycle Bin.

A SharePoint site collection administrator can view and restore deleted items from the site collection Recycle Bin to their original locations. If an item is deleted from the site collection Recycle Bin, or it exceeds the retention time, it is permanently deleted.

Important

The SharePoint Recycle Bin is different from the Recycle Bin in Windows. If you delete files or folders that you're syncing, you can restore them from the Windows Recycle Bin on your PC. To put your Windows Recycle Bin on your desktop, see [Customize the Desktop Icons in Windows](https://go.microsoft.com/fwlink/?linkid=864585).

## Restore an item from the SharePoint in Microsoft 365 site collection Recycle bin

1. On modern team sites and classic sites (subsites), in the left pane, select **Recycle bin**.

    ![Screenshot shows Choose Recycle Bin on left navigation.](sharepointonline/media/restore-deleted-items-from-site-collection-recycle-bin/spo-viewadminrecyclebin.png)

    On modern communication sites, select **Site contents**, and then select **Recycle bin** in the top navigation bar. If you don't see the Recycle Bin, follow these steps:

    1. Select **Settings**![](sharepointonline/media/restore-deleted-items-from-site-collection-recycle-bin/spo-settings-button.png) and then select **Site settings**.

        Note

        If you don't see Site settings, select **Site information** and then select **View all site settings**. Some pages might require you to select **Site contents** and select **Site settings**.
    2. Under **Site Collection Administration**, select **Recycle bin**.

        ![Screenshot showing Recycle Bin highlighted under Site Collection Administration in Settings.](sharepointonline/media/restore-deleted-items-from-site-collection-recycle-bin/spo-sitecollectionadmin-recycle-bin.png)
2. At the bottom of the **Recycle Bin** page, select **second-stage recycle bin**.

    ![Screenshot shows SharePoint online recycle bin with Second-level link highlighted.](sharepointonline/media/restore-deleted-items-from-site-collection-recycle-bin/spo-2ndlevel-recycle-link.png)

    Note

    You need administrator or owner permissions to use the site collection Recycle Bin. If you don't see it, it might have been disabled or you don't have permission to access it.
3. Point to the items you want to restore, select the check icon to the right of each one, and then select **Restore**.

    ![Screenshot shows SharePoint Online Restore button highlighted.](sharepointonline/media/restore-deleted-items-from-site-collection-recycle-bin/spo-site-recycle-restore.png)

    Note

    If you restore an item that was originally located in a deleted folder, the folder is recreated in its original location and the item is restored in that folder.

## Restore an entire site collection

If you're a global admin or SharePoint admin in Microsoft 365, you can also restore entire site collections from the site collection Recycle Bin. For info, see [Restore deleted sites](restore-deleted-site-collection).

## How long are deleted items kept in the Recycle Bin?

In SharePoint in Microsoft 365, items are retained for 93 days from the time you delete them from their original location. They stay in the site Recycle Bin the entire time, unless someone deletes them from there or empties that Recycle Bin. In that case, the items go to the site collection Recycle Bin, where they stay for the remainder of the 93 days unless:

- The site collection Recycle Bin exceeds its quota and starts purging the oldest items.
- The items are manually deleted by the site collection administrator from the site collection Recycle Bin (for info about doing this, see [SharePoint data deletion in Microsoft 365](sharepoint-data-deletion)).

The site Recycle Bin storage counts against your site collection storage quota and the quota specified in [Manage large lists and libraries](https://support.microsoft.com/topic/b8588dae-9387-48c2-9248-c24122f07c59). The amount of space allocated to the site collection Recycle Bin is 200% of the site collection quota. These values are not configurable.

SharePoint Online retains backups of all content for 14 additional days beyond actual deletion. If content can't be restored via the Recycle Bin or the feature specified in [Restore your OneDrive](https://support.microsoft.com/topic/fa231298-759d-41cf-bcd0-25ac53eb8a15), an administrator can contact Microsoft Support to request a restore any time inside the 14-day window.

Note

Restorations from backups can only be completed for site collections, not for specific files, lists, or libraries. If you need to recover a specific item, find it in the Recycle Bin, right-click it, and choose **Restore**.

In addition to the above, customers also have the option to utilize [Microsoft 365 Backup](/en-us/microsoft-365/syntex/backup/backup-overview) for data recovery. Microsoft 365 Backup offers a longer protection time and provides uniquely fast recovery from common business continuity and disaster recovery (BCDR) scenarios like ransomware or accidental/malicious employee content overwrite/deletion. Additional BCDR scenario protections are also built directly into the service, offering an enhanced level of data protection.

## A few basics about restoring from the Recycle Bin

- **Securable objects bring all their contents back with them** When you restore any securable object (any object to which access can be controlled), it is restored with all of the objects that it contained when it was deleted. For example, if you restore a list, library, folder, or Document Set, the restored version contains all the documents and other items that it contained when it was deleted. If you restore a file or other item that has multiple versions, the restored file or item includes all the versions it contained when it was deleted.
- **Most objects can't be restored if their container objects aren't present** If you delete an object and then delete the object that contained it, you must restore the container before you can restore the object. For example, if you delete a file and then delete the library in which it was stored, you must restore the library before you can restore the file. If you delete an earlier version of a file and then delete the current version of the file itself, you must restore the file itself before you can restore the earlier version.
- **Exception: An object deleted from a folder can be restored without first restoring the folder** The folder is automatically re-created in its former location, but now contains *only* the object that you restored. (Alternatively, you can also restore the folder manually from the Recycle Bin, in which case it's restored with all the contents that it had when it was deleted.)