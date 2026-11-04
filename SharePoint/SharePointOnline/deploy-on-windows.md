---
layout: Conceptual
title: Deploy OneDrive apps using Microsoft Endpoint Configuration Manager - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/deploy-on-windows
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-04-04T00:00:00.0000000Z
ms.reviewer: baladell
ms.author: v-mactran
author: MachelleTranMSFT
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: install-set-up-deploy
ms.service: onedrive
ms.localizationpriority: medium
ms.collection:
- Strat_OD_admin
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- onedrive-toc
search.appverid:
- MET150
- ODB160
- MOE150
- MED150
- MBS150
- ODB150
ms.assetid: 3f3a511c-30c6-404a-98bf-76f95c519668
description: In this article, you'll learn how to deploy OneDrive apps using Microsoft Endpoint Configuration Manager.
locale: en-us
document_id: 068634d0-772a-1818-61bf-05927956e49d
document_version_independent_id: 799a77c7-b615-cb97-1867-769fc5ddb3b3
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/deploy-on-windows.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: deploy-on-windows
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/deploy-on-windows.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: be4b1606-26d8-6ba9-0a87-c37407c1dd66
---

# Deploy OneDrive apps using Microsoft Endpoint Configuration Manager - SharePoint in Microsoft 365 | Microsoft Learn

You can use Microsoft Endpoint Configuration Manager to deploy the new OneDrive sync app (OneDrive.exe), and the mobile apps for iOS and Android. Before you begin deploying, make sure you have reviewed the planning information and deployment options in the [Plan file sync for SharePoint and OneDrive in Microsoft 365](plan-file-sync).

## Deploy the OneDrive sync app for Windows

The OneDrive sync app (OneDrive.exe) can be installed on Windows 7 and later. It can also be installed on macOS. For info about deploying the OneDrive sync app on macOS, see [Configure the new OneDrive sync app on macOS](deploy-and-configure-on-macos).

The new OneDrive sync app can be used with SharePoint Server 2019, but not earlier versions of SharePoint Server. For more information about the restrictions and limitations of the OneDrive sync app, see [Invalid file names and file types in OneDrive and SharePoint](https://support.office.com/article/64883a5d-228e-48f5-b3d2-eb39e07630fa).

OneDrive is installed per user by default. You can also install it per machine. For more information, see [Learn about installing OneDrive per machine](per-machine-installation).

### Make sure that WNS is set up correctly

The OneDrive sync app uses Windows Push Notification Services (WNS) for optimum performance and battery life. Make sure you allow access from your network to the [endpoints that OneDrive uses](/en-us/office365/enterprise/urls-and-ip-address-ranges#sharepoint-online-and-onedrive-for-business). To see all our recommendations for configuring the sync app, see [Recommended sync app configuration](ideal-state-configuration).

### Check if users already have the OneDrive sync app

If the computers in your organization are running Windows 10, they already have the new sync app installed. If the computers have Office 2016 or Office 2013 (Home & Student, Home & Business, Professional, Personal, Home, or University) installed, they might also have the new sync app.

### Deploy any administrative settings

To set registry keys on computers in your domain, install OneDrive and copy the OneDrive.admx and OneDrive.adml files from %localappdata%\Microsoft\OneDrive\BuildNumber\adm\ to your Group Policy central store. For more info, see [Use OneDrive policies to control OneDrive sync app settings](use-group-policy).

### Use Microsoft Endpoint Configuration Manager to deploy the OneDrive sync app

1. In Configuration Manager, select **Create Device Collection**, and follow the steps in the Create Device Collection wizard.
2. Save the OneDriveSetup.exe installer for Windows to your local computer or a network share. [Download the Production ring OneDriveSetup.exe installer for Windows](https://go.microsoft.com/fwlink/?linkid=844652) or [download the Deferred ring OneDriveSetup.exe installer for Windows](https://go.microsoft.com/fwlink/p/?linkid=860987).
3. Download the [sample Configuration Manager package](https://go.microsoft.com/fwlink/p/?LinkId=824069). It's a .zip file that contains the script installer deployment type. For more information about packages and programs in Configuration Manager, see [Packages and programs in Configuration Manager](/en-us/configmgr/apps/deploy-use/packages-and-programs).

    Note

    The script installer deployment type already has a detection method script and will correctly assess the installation. Also, there is an uninstall switch, which means that you can easily remove the OneDrive sync app, if necessary.
4. Copy the installer to a folder in the Configuration Manager source content share.
5. In Configuration Manager, select the **Software Library** workspace. Under **Application Management**, right-click **Applications**, and then select **Import Application**.

![Importing an application](sharepointonline/media/deploy-onedrive-enterprise_image6.png)
6. Select the sample package.
7. On the bottom of Configuration Manager, select the **Deployment Types** tab, right-click the deployment, and to update the **Content location**, edit the properties.
8. Right-click the package, select **Deploy**, and follow the steps in the Deploy Software Wizard.

If you don't use the sample package, run the following command using Microsoft Endpoint Configuration Manager:

`Execute <pathToExecutable>\OneDriveSetup.exe /silent`

(where pathToExecutable is a location on the local computer or an accessible network share).

Note

This command must be run at user logon and using Administrator permissions. It must be run for each user on a machine. For an example of how to deploy an .exe on every user account, see [How to deploy the OneDrive sync app with Configuration Manager](/en-us/archive/blogs/paulodias/how-to-deploy-onedrive-next-generation-sync-client-with-sccm).

If you run the command with no command-line parameter, users will see the installation status. After installation, OneDriveSetup.exe will automatically execute OneDrive.exe and display OneDrive Setup to users. If you run the command with the **/silent** parameter, OneDrive.exe will be installed transparently and OneDrive Setup won't appear. You'll need to run OneDrive.exe with an additional command. If you want to control the launch of OneDrive across your organization, we recommend using the **/silent** parameter.

[Learn more about application management in Configuration Manager](/en-us/previous-versions/system-center/system-center-2012-R2/gg699373%28v=technet.10%29). The installer will install the OneDrive executable file under **%localappdata%\Microsoft\OneDrive**.

## Help users sign in

To help users sign in, you can use [silent account configuration](use-silent-account-configuration) or one of these methods:

- Use the following URL to start OneDrive Setup on users' computers. When users select to begin Setup, a sign-in window appears for users can enter email address.

    `odopen://launch`
- Use the following URL with each user's email address to start Setup and prepopulate user email addresses in the sign-in window.

    `odopen://sync?useremail=youruseremail@organization.com`
- Run the following command using Configuration Manager script:

    `%localappdata%\Microsoft\OneDrive\OneDrive.exe`

    It starts the OneDrive process. If users haven't set up any accounts, it displays OneDrive Setup. To display OneDrive Setup specifically to users who haven't set up an account for your organization, use the command-line parameter:

    `/configure_business:<tenantId>`

Note

When you use Microsoft Endpoint Configuration Manager, make sure you run OneDrive.exe with User permissions (not as an Administrator).  For help finding your tenant ID, see [Find your Microsoft 365 tenant ID](find-your-office-365-tenant-id).

## Autoconfigure SharePoint site synchronization

If you want to autoconfigure a SharePoint site to be synced, you can use the URL below as a guide to build the path to the SharePoint site you want to sync automatically. You can also use a policy to sync sites automatically. For info, see [Configure team site libraries to sync automatically](use-group-policy#configure-team-site-libraries-to-sync-automatically).

`odopen://sync/?siteId=<siteId>&webId=<webId>&webUrl=<webURL>&listId=<listId>&userEmail=<userEmail>&webTitle=<webTitle>&listTitle=<listTitle>`

where:

- **&lt;siteId&gt;** is the SharePoint site siteId GUID, enclosed in curly brackets. You can get this GUID visiting https://&lt;TenantName&gt;.sharepoint.com/sites/&lt;SiteName&gt;/\_api/site/id.
- **&lt;webId&gt;** is the SharePoint site webId GUID, enclosed in curly brackets. You can get this GUID visiting https://&lt;TenantName&gt;.sharepoint.com/sites/&lt;SiteName&gt;/\_api/web/id.
- **&lt;webUrl&gt;** is the SharePoint site URL. You can get this URL visiting https://&lt;TenantName&gt;.sharepoint.com/sites/&lt;SiteName&gt;/\_api/web/url.
- **&lt;listId&gt;** is the SharePoint site documents library GUID, enclosed in curly brackets. You can get this GUID visiting the document library in the browser, select in the gear icon and choosing "Library Settings". The URL shows the listId GUID at the end of URL, i.e. https://&lt;tenant&gt;.sharepoint.com/sites/&lt;SiteName&gt;/\_layouts/15/listedit.aspx?List=%7B**xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx**%7D (a GUID with escaped curly brackets).
- **&lt;userEmail&gt;** is the OneDrive's user email address used to sign in into OneDrive.
- **&lt;webTitle&gt;** and **&lt;listTitle&gt;** are used to compose the name of the local folder where the OneDrive content is synchronized. By default, when you use the "Sync" button when in the browser to synchronize a document library, OneDrive uses the SharePoint site name and the document library name to compose the local folder name, in the form of %userprofile%\&lt;TenantName&gt;\&lt;SiteName&gt; - &lt;DocumentLibraryName&gt;. You could use any other values if you prefer to. If you don't use these parameters, the local folder is named "&lt;TenantName&gt; - Documents", despite of site and library names.

For example, if you want to synchronize `https://contoso.sharepoint.com/sites/SalesTeam-01/ProjectX`, where "ProjectX" is the documents library to synchronize, to "%userprofile%\Contoso\Sales - Unicorn" folder, you need the following parameters to compose the odopen:// URL:

- siteId: {ssssssss-ssss-ssss-ssss-ssssssssssss}
- webId: {wwwwwwww-wwww-wwww-wwww-wwwwwwwwwwww}
- webUrl: `https://contoso.sharepoint.com/sites/SalesTeam-01`
- listId: {llllllll-llll-llll-llll-llllllllllll}
- userEmail: user@contoso.com
- webTitle: Sales (you would use *SalesTeam-01* to mimic Sync button behavior instead)
- listTitle: Unicorn (you would use *ProjectX* to mimic Sync button behavior instead)

The resulting odopen:// URL is:

`odopen://sync/?siteId={ssssssss-ssss-ssss-ssss-ssssssssssss}&webId={wwwwwwww-wwww-wwww-wwww-wwwwwwwwwwww}&webUrl=https://contoso.sharepoint.com/sites/SalesTeam-01&listId={llllllll-llll-llll-llll-llllllllllll}&userEmail=user@contoso.com&webTitle=Sales&listTitle=Unicorn`

Note

You will need Client Side Object Model (CSOM) knowledge if you want to automate querying the team site to determine the appropriate siteId, webId, and listId to build the appropriate URL.

## Deploy the OneDrive app on mobile devices running iOS or Android

You can use Microsoft Endpoint Configuration Manager to deploy apps to mobile devices. Before you do, however, you need to complete a few prerequisite steps because integration with Intune is required to manage mobile devices in Configuration Manager. For information about managing mobile devices with Configuration Manager and Intune, see [Manage Mobile Devices with Configuration Manager and Microsoft Intune](/en-us/previous-versions/system-center/system-center-2012-R2/jj884158%28v=technet.10%29).

### Deploy the OneDrive app for iOS

1. In Configuration Manager, on the Home ribbon, select **Create Application**.
2. In the **Type** box, select **App Package for iOS from App Store**.
3. In the **Location** box, enter the app store URL, https://itunes.apple.com/us/app/onedrive/id823766827?mt=12.

![Entering the App Store URL](sharepointonline/media/deploy-onedrive-enterprise_image4.png)
4. Target the app to users.

For more info, see [Create iOS applications with Configuration Manager](/en-us/configmgr/mdm/deploy-use/creating-ios-applications/), and use as the app location, as shown below.

### Deploy the OneDrive app for Android

1. In Configuration Manager, on the Home ribbon, select **Create Application**.
2. In the **Type** box, select **App Package for Android on Google Play**.
3. In the **Location** box, enter the app store URL, [https://play.google.com/store/apps/details?id=com.microsoft.skydrive&hl=en](https://play.google.com/store/apps/details?id=com.microsoft.skydrive&amp;hl=en).

![Entering the Google Play URL](sharepointonline/media/deploy-onedrive-enterprise_image5.png)
4. Target the app to users.

For more info, see [Create Android applications with Configuration Manager](/en-us/configmgr/mdm/deploy-use/creating-android-applications/).