---
layout: Conceptual
title: Change a specific user's OneDrive storage space - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/change-user-storage
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-11-12T00:00:00.0000000Z
ms.reviewer: pramod.balusu
ms.author: v-mactran
author: MachelleTranMSFT
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: onedrive
ms.localizationpriority: medium
search.appverid:
- ODB160
- ODB150
- MET150
ms.collection:
- Strat_OD_admin
- M365-collaboration
- Essentials-manage
ms.custom:
- seo-marvel-apr2020
- onedrive-toc
ms.assetid: 7448173d-a38c-48cf-acbb-09ac1b6237d4
description: In this article, you learn how to change a user's OneDrive storage space in Microsoft 365 using either PowerShell or the SharePoint admin center.
locale: en-us
document_id: feeb9370-51c8-dbb3-57b9-792f4d22624d
document_version_independent_id: 7337e3b2-278f-f12f-a041-fc7e372205f0
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/change-user-storage.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: change-user-storage
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/change-user-storage.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 526166fa-efbb-fa00-6d2b-dbc49a232986
---

# Change a specific user's OneDrive storage space - SharePoint in Microsoft 365 | Microsoft Learn

As an IT administrator, you can adjust a user's OneDrive storage space using the SharePoint admin center or PowerShell.

Note

For setting the default storage space for all users, see [Set the default storage space for OneDrive users](set-default-storage-space). For details on available storage for your Microsoft 365 subscription, see the [OneDrive service description](/en-us/office365/servicedescriptions/onedrive-for-business-service-description).

Important

If a user has run out of storage, advise them to proactively review and manage their storage. Instructions can be found at [Manage your OneDrive for work](https://support.microsoft.com/office/manage-your-onedrive-for-work-or-school-storage-31519161-059c-4764-b6f8-f5cd29f7fe68).

If your tenant has Microsoft 365 OneDrive Storage enabled, you can set a user's OneDrive storage limit higher than the storage included with their license. For more information, see [Add Microsoft 365 OneDrive Storage](/en-us/microsoft-365/commerce/add-storage-space?view=o365-worldwide).

## Change storage space in the Microsoft 365 admin center

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your admin credentials.

    Note

    For Office 365 operated by 21Vianet (China), [sign in here](https://login.partner.microsoftonline.cn).
2. In the left pane, expand **Users** and select **Active users**.
3. Select the user whose storage you want to change.
4. Go to the **OneDrive** tab.
5. Under **Storage used**, select **Edit**.
6. Choose the **Maximum storage for this user** option and set the storage limit.
7. Select **Save**.

    ![OneDrive storage settings screenshot](sharepointonline/media/edit-user-storage-limit.png)

    Note

    For Office 365 A1 users, storage is limited to 100 GB. For more information, see [Office 365 Education service descriptions](/en-us/office365/servicedescriptions/office-365-platform-service-description/office-365-education).

## Change storage space using PowerShell

1. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    Note

    Uninstall any previous versions of the SharePoint Online Management Shell before installing the latest version.
2. Save the following PowerShell script to a file (for example, you can save it as *UpdateOneDriveStorage.ps1*):

    ```PowerShell
    $TenantUrl = Read-Host "Enter the SharePoint admin center URL"
    Connect-SPOService -Url $TenantUrl
    
    $OneDriveSite = Read-Host "Enter the OneDrive Site URL"
    $OneDriveStorageQuota = Read-Host "Enter the OneDrive Storage Quota in MB"
    $OneDriveStorageQuotaWarningLevel = Read-Host "Enter the OneDrive Storage Quota Warning Level in MB"
    Set-SPOSite -Identity $OneDriveSite -StorageQuota $OneDriveStorageQuota -StorageQuotaWarningLevel $OneDriveStorageQuotaWarningLevel
    Write-Host "Done"
    ```
3. Open the SharePoint Online Management Shell and run the following script:

    ```PowerShell
    PS C:\>.\UpdateOneDriveStorage.ps1
    ```

    Note

    If you receive an error regarding script execution, you may need to adjust your PowerShell execution policies. For more information, see [About execution policies](/en-us/powershell/module/microsoft.powershell.core/about/about_execution_policies).
4. Enter the required values when prompted, including:

    - The SharePoint admin center URL (for example, `https://contoso-admin.sharepoint.com`)
    - The OneDrive site URL (for example, `https://contoso-my.sharepoint.com/personal/user_contoso_onmicrosoft_com`)
    - Storage Quota in MB
    - Storage Quota Warning Level in MB

Here's a reference table for MB to TB conversions:

| MB | TB |
| --- | --- |
| 1,048,576 | 1 |
| 2,097,152 | 2 |
| 3,145,728 | 3 |
| 4,194,304 | 4 |
| 5,242,880 | 5 |

Note

To change storage space for multiple users, you can list OneDrive accounts via PowerShell and use the [Set-SPOSite](/en-us/powershell/module/sharepoint-online/set-sposite) command to apply changes.

## Troubleshooting OneDrive storage issues

If you encounter issues when adjusting storage or if the storage amount reverts to its original value, a Microsoft 365 administrator can run diagnostics in the Microsoft 365 admin center.

1. Select the following **Run Tests** button, which populates the diagnostic in the Microsoft 365 admin center.

    Note

    Diagnostics are unavailable for GCC High, DoD, Microsoft 365 operated by 21Vianet, and Microsoft 365 Education.
2. Follow the recommendations provided by the diagnostic.

    Note

    For information on disabling OneDrive creation for specific users, see [Manage user profiles in the SharePoint admin center](/en-us/sharepoint/manage-user-profiles).