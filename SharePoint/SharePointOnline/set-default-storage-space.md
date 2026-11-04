---
layout: Conceptual
title: Set the default storage space for OneDrive users - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/set-default-storage-space
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2024-11-04T00:00:00.0000000Z
ms.reviewer: jmcdowe
ms.author: v-mactran
author: MachelleTranMSFT
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: onedrive
ms.localizationpriority: medium
ms.collection:
- Strat_OD_admin
- M365-collaboration
- essentials-manage
search.appverid:
- ODB160
- ODB150
- MET150
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
- onedrive-toc
ms.assetid: cec51d07-d7e0-42a3-b794-9c00ad0f0083
description: In this article, you learn how to change the default storage space for OneDrive users.
locale: en-us
document_id: 8580c479-232b-5f69-fc12-b363af4f315a
document_version_independent_id: 3491c0e3-7009-408c-4e1b-49785efd8142
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/set-default-storage-space.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: set-default-storage-space
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/set-default-storage-space.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 748bb2d5-263a-50c0-ce1f-492a9a794ba9
---

# Set the default storage space for OneDrive users - SharePoint in Microsoft 365 | Microsoft Learn

For most subscription plans, the default storage space for each user's OneDrive is 1 TB. Depending on your plan and the number of licensed users, you can increase this storage up to 5 TB. For info, see the [OneDrive service description](/en-us/office365/servicedescriptions/onedrive-for-business-service-description). If you change a user's license, the available storage space is updated automatically within 24 hours after they access OneDrive.

Note

For help with finding out which subscription you have, see [What Microsoft 365 Apps for business subscription do I have?](/en-us/office365/admin/admin-overview/what-subscription-do-i-have).

## Set the default OneDrive storage space in the SharePoint admin center

This storage space setting applies to all new and existing users who are licensed for a qualifying plan and for whom you haven't set specific storage limits. (To check if a user has a specific storage limit, see the next section.) To change the storage space for specific users, see [Change a specific user's OneDrive storage space](change-user-storage).

Warning

If you decrease the storage limit and a user is over the new limit, their OneDrive will become read-only.

1. Go to [**Settings** in the new SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185072), and sign in with an account that has [admin permissions](/en-us/sharepoint/sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the Settings page.
2. Select the OneDrive **Storage limit** setting.

    ![Default storage limit in the SharePoint admin center](sharepointonline/media/storage-limit.png)
3. In the **Default storage limit** box, enter the default storage amount (in GB), and then select **Save**.

    Note

    The minimum storage is 1 GB.

## Check if a user has the default storage limit or a specific limit

1. Sign in to https://admin.microsoft.com as an IT administrator. (If you see a message that you don't have permission to access the page, you don't have Microsoft 365 admin permissions in your organization.)

    Note

    If you have Office 365 operated by 21Vianet (China), sign in at https://login.partner.microsoftonline.cn/. Then select the Admin tile to open the admin center.
2. In the left pane, select **Users**, and then select **Active users**.
3. Select the user.
4. Select the **OneDrive** tab.
5. Next to "Storage used," look at the max value (for example, 3 GB **of 1024 GB**).

## Set the default OneDrive storage space using PowerShell

1. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    Note

    If you installed a previous version of the SharePoint Online Management Shell, go to **Installed apps** and uninstall "SharePoint Online Management Shell."
2. Connect to SharePoint as a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
3. Run the following command:

    ```PowerShell
    Set-SPOTenant -OneDriveStorageQuota <quota>
    ```

    Where *&lt;quota&gt;* is the value in megabytes for the storage space. For example, 1048576 for 1 TB or 5242880 for 5 TB. You can specify any value that you want, however, if you specify a value greater than that allowed by a given user's license, that user's storage space is rounded down to the maximum value allowed by their license.

    To reset an existing user's OneDrive to the new default storage space, run the following command:

    ```PowerShell
    Set-SPOSite -Identity <user's OneDrive URL> -StorageQuotaReset
    ```

    Note

    When you set site storage limits in PowerShell, you enter them in MB. The values are converted and rounded down to the nearest integer to appear in the admin centers in GB, so a value of 5000 MB becomes 4 GB. If you set a value of less than 1024 MB using PowerShell, it's rounded up to 1 GB.