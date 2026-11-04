---
layout: Conceptual
title: Restore a deleted OneDrive - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/restore-deleted-onedrive
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-02-07T00:00:00.0000000Z
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
- Essentials-manage
ms.custom:
- admindeeplinkSPO
- onedrive-toc
search.appverid:
- ODB160
- MET150
ms.assetid: e487f40d-5321-46a8-9504-92b600b65cb9
description: Learn how to restore a deleted user's OneDrive when the deleted user no longer appears in the Microsoft 365 admin center.
locale: en-us
document_id: 42531982-8c57-550c-e108-f72992368510
document_version_independent_id: 5c90f1d2-e171-a242-737d-9f3113f12eb2
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/restore-deleted-onedrive.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: restore-deleted-onedrive
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/restore-deleted-onedrive.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 21dea730-8e26-14e6-18c3-f292b8e06277
---

# Restore a deleted OneDrive - SharePoint in Microsoft 365 | Microsoft Learn

When you delete a user in the Microsoft 365 admin center (or when a user is removed through Active Directory synchronization), the user's OneDrive is retained for the number of days you specify in the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219). (For info, see [Set the default file retention for deleted OneDrive users](set-retention).) The default is 30 days. During this time, other users can still access shared content. At the end of the time period, the OneDrive remains in a deleted state for 93 days and can only be restored by a SharePoint Administrator.

For info about using Files Restore to restore a OneDrive to a previous point in time, see [Restore your OneDrive](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15).

For info about restoring items from the recycle bin in OneDrive, see [Restore deleted files or folders](https://support.office.com/article/949ada80-0026-4db3-a953-c99083e6a84f).

## Restore a deleted OneDrive when the deleted user no longer appears in the Microsoft 365 admin center

If the user was deleted within 30 days, you can restore the user and all their data from the Microsoft 365 admin center. To learn how, see [Restore a user in Microsoft 365](/en-us/office365/admin/add-users/restore-user). If you deleted the user more than 30 days ago, the user will no longer appear in the Microsoft 365 admin center, and you need to use PowerShell to restore the OneDrive.

1. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    Note

    If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell."
2. Connect to SharePoint as a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
3. Determine if the OneDrive is available for restore.

    - If you know the URL of the OneDrive, run the following command:

        ```PowerShell
        Get-SPODeletedSite -Identity <URL>
        ```

        A user's OneDrive URL is based on their username. For example, `https://contoso-my.sharepoint.com/personal/user1_contoso_com`. You can find their username on the Active users (or Deleted users) page in the Microsoft 365 admin center.
    - If you don't know the URL of the deleted OneDrive, run the following command:

        ```PowerShell
        Get-SPODeletedSite -IncludeOnlyPersonalSite | FT url
        ```
    - If the OneDrive appears in the results, it can be restored.
4. Restore the OneDrive to an active state:

    ```PowerShell
    Restore-SPODeletedSite -Identity <URL>
    ```
5. Assign an administrator to the OneDrive to access the needed data:

    ```PowerShell
    Set-SPOUser -Site <URL> -LoginName <UPNofDesiredAdmin> -IsSiteCollectionAdmin $True
    ```

For more info about these cmdlets, see [Get-SPODeletedSite](/en-us/powershell/module/sharepoint-online/get-spodeletedsite) and [Restore-SPODeletedSite](/en-us/powershell/module/sharepoint-online/restore-spodeletedsite).

Note

When a OneDrive is restored, it continues to remain available until it's explicitly deleted.

## Permanently delete a OneDrive

After you recover the data you need from the OneDrive, we recommend that you permanently delete the OneDrive by running the following command:

```PowerShell
Remove-SPOSite -Identity <URL>
Remove-SPODeletedSite -Identity <URL>
```

Caution

When you permanently delete a OneDrive, you won't be able to restore it.