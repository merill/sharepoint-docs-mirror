---
layout: Conceptual
title: Delete a site - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/delete-site-collection
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2024-05-28T00:00:00.0000000Z
ms.reviewer: 
manager: jtremper
ms.author: ruihu
author: maggierui
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.collection:
- Strat_SP_admin
- M365-collaboration
- m365initiative-spsitemanagement
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
search.appverid:
- SPO160
- MET150
ms.localizationpriority: medium
ms.assetid: 4dc86d69-84c9-426c-b83f-e6e674722d85
description: In this article, you'll learn how to delete SharePoint sites in the SharePoint admin center.
locale: en-us
document_id: a3bd11d3-f2a4-2811-09bd-449c3c3607da
document_version_independent_id: 2f47da99-02e6-3357-ed41-b28bd5190907
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/delete-site-collection.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: delete-site-collection
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/delete-site-collection.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 4ac30a8d-f8d5-79ce-9318-3166a740b395
---

# Delete a site - SharePoint in Microsoft 365 | Microsoft Learn

When you, as a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) and [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365, delete a site (previously called a "site collection"), it's retained as a deleted site for 93 days. Deleting a site deletes everything within it, including:

- Document libraries and files.
- Lists and list data.
- Site settings and history.
- Any subsites and their contents.

You should notify the site admins and any subsite owners before you delete a site so they can move their data to another location, and also tell users when the sites will be deleted.

Warning

We do not recommend deleting the root site for your organization. If you do, all your SharePoint sites will be inaccessible until you restore the site or create a new root site. Instead of deleting the root site, we recommend replacing it. [Learn more about the root site and how to replace it](modern-root-site)

Note

Deleted sites in the Recycle Bin do not count toward the organization’s total storage usage. It will take up to 48 hours for the storage usage to update.

## Delete a site in the new SharePoint admin center

By using the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219), you can delete both classic and modern sites. As a a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) and [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365, you can now delete sites that belong to Microsoft 365 groups. Deleting these sites will delete the group and all its resources, including the Outlook mailbox and calendar, and any Teams channels.

1. Go to [**Active sites** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185220), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the Active sites page.
2. In the left column, select a site.
3. Select **Delete**, and to confirm, select **Delete**.

    ![Deleting a site on the Active sites page](sharepointonline/media/delete-site.png)

Note

To delete a hub site, you first need to unregister it as a hub site.Deleted Microsoft 365 groups are retained for only 30 days.For info about deleting a site by using PowerShell, see [Remove-SPOSite](/en-us/powershell/module/sharepoint-online/remove-sposite).

## Permanently delete a site

To reuse a URL from a deleted site (recreate a site), you need to permanently delete the site. After the site is permanently deleted, it might take up to 24 hours for the URL to become available. On the Deleted sites page of the new SharePoint admin center, you can permanently delete all sites except those that belong to Microsoft 365 groups.

1. Go to [**Deleted sites** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185070), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the Deleted sites page.
2. In the left column, select a site.
3. Select **Delete**, and to confirm, select **Delete**.

To permanently delete sites (including Microsoft 365 group-connected team sites) by using PowerShell, follow these steps:

1. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    Note

    If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell."
2. Connect to SharePoint as a [Global Administrator or SharePoint Administrator](sharepoint-admin-role) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
3. Run the following command:

    ```PowerShell
    Remove-SPODeletedSite -Identity https://contoso.sharepoint.com/sites/sitetoremove
    ```

(Where `https://contoso.sharepoint.com/sites/sitetoremove` is the URL of the site you want to permanently delete). For more info about using this command, see [Remove-SPODeletedSite](/en-us/powershell/module/sharepoint-online/remove-spodeletedsite).

## Summary of options

| Site type | How to delete | How to permanently delete |
| --- | --- | --- |
| Root site | Not recommended. [Replace the root site with a different site](modern-root-site#replace-your-root-site). When the site is no longer a root site, its URL will be /sites/archive-*datetime*, and you can delete it from the Active sites page of the new SharePoint admin center or by using PowerShell | From the Deleted sites page of the new SharePoint admin center or by using PowerShell |
| Communication sites | Delete them from the Active sites page of the new SharePoint admin center or by using PowerShell | From the Deleted sites page of the new SharePoint admin center or by using PowerShell |
| Microsoft 365 group-connected team sites | Delete Microsoft 365 groups and all their resources from the Microsoft 365 admin center, the Active sites page of the new SharePoint admin center, or by using PowerShell | From PowerShell only |
| Hub sites (those designated with "(Hub site)" in the Hub column) | [Unregister them as hub sites](remove-hub-site) from the Active sites page of the new SharePoint admin center, or by using PowerShell, and then delete them based on their site type | Based on their site type |
| Classic sites | Delete them from the Active sites page of the new SharePoint admin center or by using PowerShell | From the Deleted sites page of the new SharePoint admin center or by using PowerShell |

Note

Sites associated with a hub can be deleted like any other site based on their template.