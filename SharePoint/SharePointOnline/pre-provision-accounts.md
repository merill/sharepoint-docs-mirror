---
layout: Conceptual
title: Pre-provision OneDrive for users in your organization - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/pre-provision-accounts
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-04-05T00:00:00.0000000Z
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
search.appverid:
- SPO160
- ODB160
- ODB150s
- GOB150
- GOB160
- MET150
ms.collection:
- Strat_OD_admin
- M365-collaboration
- essentials-manage
ms.assetid: ceef6623-f54f-404d-8ee3-3ce1e338db07
ms.custom:
- seo-marvel-apr2020
- onedrive-toc
- has-azure-ad-ps-ref
- azure-ad-ref-level-one-done
description: Learn how to use PowerShell to create OneDrive file storage for your users instead of waiting for the storage space to be automatically provisioned by the service.
locale: en-us
document_id: a44f106d-ea01-b0b3-a538-ffca3eeeb29f
document_version_independent_id: 074a92aa-3117-8795-c6ff-149cff16ca25
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/pre-provision-accounts.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: pre-provision-accounts
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/pre-provision-accounts.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 64c92947-5e78-1267-61a6-462c6d946dcd
---

# Pre-provision OneDrive for users in your organization - SharePoint in Microsoft 365 | Microsoft Learn

By default, the first time that a user browses to their OneDrive it's automatically created (provisioned) for them. In some cases, such as the following, you might want your users' OneDrive locations to be ready beforehand, or pre-provisioned:

- Your organization has a custom process for adding new employees, and you want to create a OneDrive when you add a new employee.
- Your organization plans to migrate from SharePoint Server on-premises to Microsoft 365.
- Your organization plans to migrate from another online storage service.

This article describes how to pre-provision OneDrive for your users by using PowerShell.

- For info about setting the default storage size, see [Set the default storage space for OneDrive users](set-default-storage-space).
- For info about the storage you get with each plan, see [OneDrive Service Description](/en-us/office365/servicedescriptions/onedrive-for-business-service-description).

Important

The user accounts that you're pre-provisioning must be allowed to sign in and must also have a SharePoint license assigned. To provision OneDrive by using this cmdlet, you must be a SharePoint Administrator and must be assigned a SharePoint license.

Note

If you're pre-provisioning OneDrive for a large number of users, it might take multiple days for the OneDrive locations to be created.

## Pre-provision OneDrive for users

1. If you're pre-provisioning OneDrive for many users, create a list of these users and save it as a file. For example, create a text file named Users.txt that contains:

    ```
    user1@contoso.com
    user2@contoso.com
    user3@contoso.com
    ```
2. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    Note

    If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell."
3. Connect to SharePoint as a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

    Note

    The PowerShell command Request-SPOPersonalSite works only for users who are allowed to sign in. If you've blocked users from signing in, you can allow them to sign in by running the PowerShell command **Update-MgUser** using the text file you created in Step 1.

    ```PowerShell
    Get-Content -path "C:\Users.txt" | ForEach-Object { Update-MgUser -UserPrincipalName $_ -BlockCredential $False }
    ```
4. Run the PowerShell command [Request-SPOPersonalSite](/en-us/powershell/module/sharepoint-online/request-spopersonalsite?view=sharepoint-ps&amp;preserve-view=true), consuming the text file you previously created in Step 1.

    ```PowerShell
    $users = Get-Content -path "C:\Users.txt"
    Request-SPOPersonalSite -UserEmails $users
    ```

To verify that OneDrive has been created for your users, see [Get a list of all user OneDrive URLs in your organization](list-onedrive-urls).

## Pre-provision OneDrive for all licensed users in your organization

The following code snippet pre-provisions OneDrive in batches of 199.

Note

You need to provide your Microsoft 365 Tenant ID. For more information, see [Find IDs and domain names](/en-us/partner-center/account-settings/find-ids-and-domain-names).

```PowerShell
Param(
    [Parameter(Mandatory = $True)]
    [String]
    $SharepointURL,
    [Parameter(Mandatory = $True)]
    [String]
    $tenantID
)

$scope = 'User.Read.All'
Connect-MgGraph -TenantId $tenantId -Scopes $scope
Connect-SPOService -Url $SharepointURL;

$list = @() #list of UPN to pass to the SP command
$Totalusers = 0 #total user provisioned.

#Get licensed users
$users = Get-MgUser -Filter 'assignedLicenses/$count ne 0' -ConsistencyLevel eventual -CountVariable licensedUserCount -All -Select UserPrincipalName

foreach ($u in $users) {
    $Totalusers++
    Write-Host "$Totalusers/$($users.Count)"
    $list += $u.userprincipalname

    if ($list.Count -eq 199) {
        #We reached the limit
        Write-Host "Batch limit reached, requesting provision for the current batch"
        Request-SPOPersonalSite -UserEmails $list -NoWait
        Start-Sleep -Milliseconds 655
        $list = @()
    }
}

if ($list.Count -gt 0) {
    Request-SPOPersonalSite -UserEmails $list -NoWait
}
Disconnect-SPOService
Disconnect-MgGraph
Write-Host "Completed OneDrive Provisioning for $Totalusers users"
```