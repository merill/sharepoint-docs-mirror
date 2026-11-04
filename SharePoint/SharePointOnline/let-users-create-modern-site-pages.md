---
layout: Conceptual
title: Allow users to create modern pages - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/let-users-create-modern-site-pages
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-06-25T00:00:00.0000000Z
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords:
- CSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: sites-pages
ms.localizationpriority: medium
ms.collection:
- Strat_SP_admin
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
search.appverid:
- SPO160
- BSA160
- MET150
ms.assetid: c41d9cc8-c5c0-46b4-8b87-ea66abc6e63b
description: In this article, you learn how to allow or prevent users from adding modern pages on SharePoint sites.
locale: en-us
document_id: 6de79eee-3a56-4611-7654-0be9c9ccdf51
document_version_independent_id: 9c60ba38-755e-b1a9-eef2-c91bd600840e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/let-users-create-modern-site-pages.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: let-users-create-modern-site-pages
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/let-users-create-modern-site-pages.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 3718e965-41d2-2d32-1ebe-ba10c3151ba3
---

# Allow users to create modern pages - SharePoint in Microsoft 365 | Microsoft Learn

Using modern pages in Microsoft SharePoint is a great way to share ideas using images, Office files, video, and more. Users can [Add a page to a site](https://support.office.com/article/b3d46deb-27a6-4b1e-87b8-df851e503dec) quickly and easily, and modern pages look great on any device.

If you have at least a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) role or [more](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365, you can allow or prevent users from creating modern pages. You can do this at the organization level by changing settings in the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219). If you allow the creation of site pages as the organization level, you can turn it on or off at the site level by using PowerShell. Site owners can also [turn it on or off at the site level](https://support.office.com/article/787F3BA1-9DF6-480A-AB4C-9F4525490CB9).

Note

If you want to prevent members from creating or modifying any SharePoint pages on a site, go to Site Pages, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) &gt; **Library settings** &gt; **Permissions for this document library**, and then set the Members group to Read.

## Change page creation settings at the organization level

1. Go to [**Settings** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185072), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the Settings page.
2. Select **Pages**.
3. Select or clear **Allow users to create new modern pages**.

    Note

    Preventing users from creating modern pages hides the following options:

    - On the Site Pages and Site contents pages &gt; **New** &gt; **Page**.
    - **Settings**![](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) &gt; **Add a page**.

    Users can still add pages from other modern pages, either from the New menu or from modern webparts (such as News).
4. You can also select to allow or prevent commenting on modern pages. If you allow commenting, it can be turned on or off at the page level.

    ![Pages settings in the new SharePoint admin center](sharepointonline/media/pages-setting.png)

## Prevent users from creating modern pages on a specific site by using PowerShell

If you allow the creation of site pages as the organization level, you can turn it off at the site level by using PowerShell.

1. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    Note

    If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell."
2. Install the [SharePoint Online Client Components SDK](https://www.microsoft.com/en-us/download/details.aspx?id=42038).
3. Connect to SharePoint as a [Global Administrator or SharePoint Administrator](sharepoint-admin-role) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

    Note

    Read [About Execution Policies](/en-us/powershell/module/microsoft.powershell.core/about/about_execution_policies) and make sure you run the SharePoint Online Management Shell as an administrator and the correct execution policy to run unsigned scripts.
4. Copy the following code and paste it into a text editor, such as Notepad.

    ```PowerShell
    # Load SharePoint Online Client Components SDK Module
    Import-Module 'C:\Program Files\Common Files\microsoft shared\Web Server Extensions\16\ISAPI\Microsoft.SharePoint.Client.dll'
    
    # Set script constants
    $sitePagesFeatureIdString = 'B6917CB1-93A0-4B97-A84D-7CF49975D4EC'
    
    # Set up client context
    $userName = Read-Host "Username"
    $password = Read-Host "Password" -AsSecureString
    $siteUrl = Read-Host "Site Url"
    $webUrl = Read-Host "Server-Relative Web Url"
    $context = New-Object Microsoft.SharePoint.Client.ClientContext($siteUrl)
    $credentials = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($userName, $password)
    $context.Credentials = $credentials
    
    # Get the list of existing features
    $web = $context.Site.OpenWeb($webUrl)
    $features = $web.Features
    $context.Load($features)
    $context.ExecuteQuery()
    
    # Verify that the Site Pages feature is present in the web
    if(($features | ? { $_.DefinitionId -eq $sitePagesFeatureIdString }).Count -eq 0)
    {
        Write-Host "The Site Pages feature is already disabled in this web"
        return
    }
    
    # Remove the Site Pages feature from the web
    $features.Remove((new-object 'System.Guid' $sitePagesFeatureIdString), $false)
    $context.ExecuteQuery()
    
    # Verify that the Site Pages feature is no longer present in the Web
    $web = $context.Site.OpenWeb($webUrl)
    $features = $web.Features
    $context.Load($features)
    $context.ExecuteQuery()
    if(($features | ? { $_.DefinitionId -eq $sitePagesFeatureIdString }).Count -eq 0)
    {
        Write-Host "The Site Pages feature has been successfully disabled"
    }
    else
    {    
        throw "The Site Pages feature failed to be disabled"
    } 
    ```
5. Save the text file, and then change its extension. In this example, we name it SitePagesOut.ps1.

    Note

    You can use a different file name, but you must save the file as an ANSI-encoded text file whose extension is .ps1.
6. Change to the directory where you saved the file.
7. Run the following command:

    ```powershell
    .\SitePagesOut.ps1
    ```
8. The script prompts you for a **SiteUrl** and **WebUrl**.

    If you have a site such as: `https://contoso.sharepoint.com/sites/marketing/northwindcompete`

    For the **SiteUrl** you would enter: `https://contoso.sharepoint.com/sites/marketing`

    And for the **WebUrl** you would enter: `sites/marketing/northwindcompete`

## Allow users to create modern pages on a specific site by using PowerShell

If you prevented users from creating modern pages on a site, follow these steps to allow it again.

1. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).
2. Install the [SharePoint Client Components SDK](https://www.microsoft.com/en-us/download/details.aspx?id=42038).
3. Connect to SharePoint as a [Global Administrator or SharePoint Administrator](sharepoint-admin-role) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

    Note

    Read [About Execution Policies](/en-us/powershell/module/microsoft.powershell.core/about/about_execution_policies) and make sure you run the SharePoint Online Management Shell as an administrator and the correct execution policy to run unsigned scripts.
4. Copy the following code and paste it into a text editor, such as Notepad.

    ```PowerShell
    # Load SharePoint Online Client Components SDK Module
    Import-Module 'C:\Program Files\Common Files\microsoft shared\Web Server Extensions\16\ISAPI\Microsoft.SharePoint.Client.dll'
    
    # Set script constants
    $sitePagesFeatureIdString = 'B6917CB1-93A0-4B97-A84D-7CF49975D4EC'
    
    # Set up client context
    $userName = Read-Host "Username"
    $password = Read-Host "Password" -AsSecureString
    $siteUrl = Read-Host "Site Url"
    $webUrl = Read-Host "Server-Relative Web Url"
    $context = New-Object Microsoft.SharePoint.Client.ClientContext($siteUrl)
    $credentials = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($userName, $password)
    $context.Credentials = $credentials
    
    # Get the list of existing features
    $web = $context.Site.OpenWeb($webUrl)
    $features = $web.Features
    $context.Load($features)
    $context.ExecuteQuery()
    
    # Verify that the Site Pages feature is not present in the web
    if(($features | ? { $_.DefinitionId -eq $sitePagesFeatureIdString }).Count -gt 0)
    {
        Write-Host "The Site Pages feature is already enabled in this web"
        return
    }
    
    # Add the Site Pages feature back to the web
    $features.Add((new-object 'System.Guid' $sitePagesFeatureIdString), $false, [Microsoft.SharePoint.Client.FeatureDefinitionScope]::None)
    $context.ExecuteQuery()
    
    # Verify that the Site Pages feature is now present in the web
    $web = $context.Site.OpenWeb($webUrl)
    $features = $web.Features
    $context.Load($features)
    $context.ExecuteQuery()
    if(($features | ? { $_.DefinitionId -eq $sitePagesFeatureIdString }).Count -gt 0)
    {
        Write-Host "The Site Pages feature has been successfully enabled"
    }
    else
    {
        throw "The Site Pages feature failed to be enabled"
    }
    ```
5. Save the text file, and then change its extension. In this example, we name it SitePagesIn.ps1.

    Note

    You can use a different file name, but you must save the file as an ANSI-encoded text file whose extension is .ps1.
6. Change to the directory where you saved the file.
7. Run the following command:

    ```powershell
    .\SitePagesIn.ps1
    ```
8. The script prompts you for a **SiteUrl** and **WebUrl**.

    If you have a site such as: `https://contoso.sharepoint.com/sites/marketing/northwindcompete`

    For the **SiteUrl** you would enter: `https://contoso.sharepoint.com/sites/marketing`

    And for the **WebUrl** you would enter: `sites/marketing/northwindcompete`