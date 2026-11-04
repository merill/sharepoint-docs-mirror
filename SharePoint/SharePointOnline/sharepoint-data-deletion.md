---
layout: Conceptual
title: Microsoft 365 SharePoint Data Deletion - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/sharepoint-data-deletion
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
description: Learn how data deletion works in SharePoint, such as where deleted content is stored and for how long.
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.reviewer: danielgluck
audience: ITPro
ms.topic: overview
ms.service: sharepoint-online
search.appverid:
- MET150
ms.collection:
- MS-Compliance
- MS-Compliance-Assurance
- MCAT
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.date: 2026-08-28T00:00:00.0000000Z
locale: en-us
document_id: 12de3d9c-cb30-d359-a00b-3e0d2f0503e3
document_version_independent_id: 8b2aa1fe-827e-b805-fa2b-97f79d2ef7dc
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/sharepoint-data-deletion.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: sharepoint-data-deletion
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/sharepoint-data-deletion.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: f5f5dcef-84c8-33cc-eca1-646213bc5173
---

# Microsoft 365 SharePoint Data Deletion - SharePoint in Microsoft 365 | Microsoft Learn

SharePoint stores objects as abstracted code within application databases. When a user uploads a file to SharePoint, SharePoint disassembles the file and translates it into application code. SharePoint stores the code in multiple tables across multiple databases. In SharePoint, all content that a customer uploads is broken into chunks, encrypted (potentially with multiple AES 256-bit keys), and distributed across the datacenter. For specific details about the chunking and encryption process, see [Encryption in the Microsoft Cloud](/en-us/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview).

When you use the SharePoint application within a browser, any user who deletes an item retains the item in the site Recycle Bin for 93 days from the time they deleted it from its original location. The items stay in the site Recycle Bin the entire time, unless someone deletes them from the site Recycle Bin or empties that Recycle Bin. In that case, the items go to the site collection Recycle Bin, also known as the second-stage Recycle Bin, where they stay for the remainder of their retention period. Items deleted from the site collection Recycle Bin are purged immediately. If the item deleted causes the site collection Recycle Bin to exceed its quota, it starts purging the oldest items until there's space for the most recently deleted item. For info about restoring deleted items, see [Restore items in the Recycle Bin of a SharePoint site](https://support.office.com/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online) and [Restore deleted items from the site collection recycle bin](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b).

When you delete a site collection, you also delete the hierarchy of sites in the collection, and all content within them:

- Documents and document libraries
- Lists and list data
- Site configuration settings
- Role and security information that is related to the site or its subsites
- Subsites of the top-level website, their contents, and user information

If you accidentally delete a site collection, a global or SharePoint admin can restore it by using the SharePoint admin center.

Deleted site collections are retained for 93 days. After 93 days, sites and all their content and settings are permanently deleted, including lists, libraries, pages, and any subsites.

Hard deletion occurs when a user purges deleted items from the site collection Recycle Bin, when the retention and backup periods expire, or when an administrator permanently deletes a site collection by using the [Remove-SPODeletedSite cmdlet](/en-us/powershell/module/sharepoint-online/remove-spodeletedsite). When a user hard deletes (permanently deletes, or purges) content from SharePoint, SharePoint also deletes all encryption keys for the deleted chunks. The blocks on the disks that previously stored the deleted chunks are marked as unused and available for reuse.

Users can also interact with the SharePoint platform by using CSOM/REST APIs. API calls can recycle or delete items on SharePoint such as files and folders. Recycling an item adds it to the Recycle Bin, similar to the browser application behavior described earlier in this article. However, deleting results in the item being immediately purged and it isn't recoverable from the site or site collection Recycle Bins. You can read more about SharePoint APIs here.

SharePoint retains backups of all content for 14 more days beyond actual deletion to facilitate a full site collection restore for customers. Customers can reach out to Microsoft support to initiate a full site collection or subsite [point in time restore](https://support.microsoft.com/en-us/office/how-to-recover-missing-deleted-or-corrupted-items-in-sharepoint-and-onedrive-for-work-or-school-3d748edf-c072-46c9-81a4-4989056ebc87) if files are hard deleted, corrupted, or infected with malware and are unrecoverable using the methods described earlier. After this 14 day period, Microsoft no longer retains the data and it isn't recoverable.

## Delete an item from the site Recycle Bin

### To delete items from the SharePoint site Recycle Bin

1. Click **Recycle Bin** in the Quick Launch bar on the left of the screen. If you don't see the **Recycle Bin** on the Quick Launch bar, follow these steps:

    1. Click **Settings**![](sharepointonline/media/spo-delete-items/settingsbutton.png) and then click **Site Contents**. The **Recycle bin** option is in the top-right portion of the **Site Contents** page.

    ![Screenshot shows the SharePoint Online Site Contents page Recycle button.](sharepointonline/media/spo-delete-items/spo-site-recycle-contents-page.png)
2. On the **Recycle Bin** page, click the box to the left of the items or files you want to delete or restore.
3. Click **Delete** to delete the selected files.

    ![SharePoint Online Recycle delete item button](sharepointonline/media/spo-delete-items/spo-site-recycle-delete-button.png)

Note

If you don't see the item you're looking for, it might have already been deleted and already moved to the site collection Recycle Bin. Or it might have exceeded the holding time limit (93 days) and already been permanently deleted.

### To delete all items from the SharePoint site Recycle Bin

1. Click **Recycle Bin** in the Quick Launch bar on the left of the screen. If you don't see the **Recycle Bin** on the Quick Launch bar, follow these steps:

    1. Click **Settings**![](sharepointonline/media/spo-delete-items/settingsbutton.png) and then click **Site Contents**. The **Recycle bin** option is in the top-right portion of the **Site Contents** page.

    ![Screenshot shows the SharePoint Online Site Contents page Recycle button.](sharepointonline/media/spo-delete-items/spo-site-recycle-contents-page.png)
2. On the Recycle Bin page, click **Empty recycle bin**![](sharepointonline/media/spo-delete-items/spo-empty-recycle-bin-button.png) to delete all items. If **Empty recycle bin** isn't visible, make sure you unselect all items in the recycle bin.

## Delete items or empty the Second-stage Recycle Bin in SharePoint

Caution

When you delete an item from the Second-stage or Site Collection Recycle Bin, it is permanently removed.

1. On modern team sites and classic sites (subsites) in the left pane, choose **Recycle bin**.

    ![Screenshot shows the selection of Recycle Bin option in left navigation.](sharepointonline/media/spo-delete-items/spo-viewadminrecyclebin.png)

    On modern communication sites, select **Site contents**, and then click **Recycle bin** in the top navigation bar. If you don't see the Recycle Bin, and you do have permissions, try the following steps.

    1. Click **Settings**![](sharepointonline/media/spo-delete-items/settingsbutton.png) and then click **Site settings**. If you don't see **Site settings**, click **Site information** and then click **View all site settings**. Some pages might require you to select **Site contents**, and then **Site settings**.
    2. On Site Settings, under **Site Collection Administration**, select **Recycle bin**.

        ![Screenshot shows Recycle Bin selected in the Site Collection Administration section of Settings.](sharepointonline/media/spo-delete-items/spo-sitecollectionadmin-recycle-bin.png)
2. At the bottom of the **Recycle bin** page, click **Second-stage recycle bin**.

    ![Screenshot showing the SharePoint Online recycle bin with the second-stage link highlighted.](sharepointonline/media/spo-delete-items/spo-2ndlevel-recycle-link.png)
3. Do one of the following:

    - **Delete one or more items** - Hover and click the circle next to the item(s) you want to delete and then click **Delete**.

        ![Screenshot shows the SharePoint Online 2nd level recycle with delete button highlighted.](sharepointonline/media/spo-delete-items/spo-2ndlevel-recycle-delete-button.png)
    - **Delete all items** - Clear all check marks and click **Empty recycle bin**.

        ![Screenshot shows the SharePoint Online 2nd level recycle bin with Empty recycle bin button highlighted.](sharepointonline/media/spo-delete-items/spo-2ndlevel-empty-recycle-button.png)
4. In the confirmation box, click **Delete**.