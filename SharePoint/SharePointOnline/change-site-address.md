---
layout: Conceptual
title: Change a site address - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/change-site-address
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-12-22T00:00:00.0000000Z
ms.reviewer: waynewin
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
customer_intent: As a SharePoint Administrator, I want to change a site address
f1.keywords:
- CSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Strat_SP_admin
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
search.appverid:
- SPO160
- MOE150
- FRP150
- MET150
ms.assetid: aa93f89b-ffce-4edb-aa89-22b16d6915a7
description: Learn how to change the URL of a SharePoint site.
locale: en-us
document_id: 5475fd83-52fa-6d49-d08f-fc75fabee09c
document_version_independent_id: 19ede247-e62c-9f1a-700c-4c878fec7f78
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/change-site-address.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: change-site-address
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/change-site-address.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 10a67db3-bf7b-2453-f576-9bb359669a30
---

# Change a site address - SharePoint in Microsoft 365 | Microsoft Learn

Important

There is currently a known issue caused by the retirement of BCS that is affecting changing of site addresses. The fix is currently being worked on. Currently, if you are facing issues, please try changing the site address using the PowerShell cmdlet while using the -SuppressBcsCheck parameter.

Note

This feature isn't supported for Microsoft 365 Sovereign Cloud customers, except GCC Low.

As a [SharePoint Administrator](sharepoint-admin-role) in your organization, you can change the URL for the following types of SharePoint sites (previously called "site collections"):

- Microsoft 365 group-connected team sites
- Modern team sites that don't belong to a Microsoft 365 group
- Communication sites
- Classic team sites

Changing the site address isn't supported in the following situations:

- The Publishing feature is currently activated or was previously activated for the site.
- The site contains more than 15 million documents.

You can change only the address of the site within the URL, for example:

https://contoso.sharepoint.com/sites/*project-x* to https://contoso.sharepoint.com/sites/*project-y*

You can't move the site from "/sites" to "/teams." For info about changing your SharePoint domain name, see [Change your SharePoint domain name](change-your-sharepoint-domain-name).

It can take about 10 minutes to change the site address (depending on the size of the site), and the site is read-only during this time. We recommend changing addresses during times when site usage is low.

You can change the address of up to 100 sites at a time. To change another site address, wait for ongoing changes to finish.

Note

If you need to revert a site address change, follow the steps in Revert a site address change.

## How do I communicate the address change to users?

Before you change the address of a site, it's important to communicate the change to site users (generally anyone with the ability to edit or view the site). This can help reduce user confusion and calls to your help desk. Review the effects of changing a site address and let users know the following information:

- The planned date of the change
- The planned URL
- Users should close their files and not make edits during the address change
- Users should check the site recycle bin to make sure it contains no files they want to keep
- File permissions and sharing stay the same

## How do I change a site address in the SharePoint admin center?

1. Go to [**Active sites** in the new SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185220), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the Active sites page.
2. Select the site name to open the details panel.
3. On the **General** tab, under **Site address**, select **Edit**.

    ![Changing the address of a site](sharepointonline/media/change-site-address.png)
4. Enter the new site address, and then select **Save**.

    Note

    You can't change the address of hub sites, sites that are locked or on hold, Project Web App (PWA) sites, or sites that have BCS connections.

    When you change a site address, we create a redirect at the previous address. If you want to reuse the previous address, you need to delete the redirect. [Learn how](manage-site-redirects)

## How do I change site addresses by using PowerShell?

1. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    Note

    If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell."
2. Connect to SharePoint as at least a [SharePoint Administrator](sharepoint-admin-role) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
3. Run the following command to verify that the site address can be changed:

    ```PowerShell
    Start-SPOSiteRename -Identity https://contoso.sharepoint.com/sites/project-x -NewSiteUrl https://contoso.sharepoint.com/sites/project-y -ValidationOnly
    ```
4. Run the following command to change the site address:

    ```PowerShell
    Start-SPOSiteRename -Identity https://contoso.sharepoint.com/sites/project-x -NewSiteUrl https://contoso.sharepoint.com/sites/project-y
    ```

    For more information about this cmdlet, see [Start-SPOSiteRename](/en-us/powershell/module/sharepoint-online/start-spositerename?view=sharepoint-ps&amp;preserve-view=true).

## What are the effects of changing a site address?

While the change is in progress, the site is set to read-only, and a redirect is created. After the change is complete, users are redirected to the new URL if they've saved the site as a favorite, or if they select a link to the site.

**Apps** If apps in your organization refer to the site's URL, you might need to republish the apps when you change the site's address.

**Custom Forms Created in Power Apps** You need to recreate the Custom Form after the site address change.

**Hub sites** If the site is associated with a hub, you must reassociate it after the site address is changed.

**InfoPath forms** InfoPath forms that refer to URLs might not work after the site address is changed.

**List View web part** If a List View web part on a page is scoped to a specific folder in that list, the web part might display an error after the site URL is changed. To fix this issue, either edit the web part and reset the folder path or remove the web part from the page, and then add it again.

**Microsoft Forms** If the site is a Microsoft 365 group-connected site that has forms in Microsoft Forms, any File Upload questions in forms break. To fix this issue, recreate the file upload questions to allow responders to upload files again.

**OneNote** If users have a notebook open during the site address change, they see a notebook sync error. After the address is changed, the following OneNote apps will automatically detect and seamlessly sync notebooks to the new site URL:

- OneNote desktop app – Version 16.0.8326.2096 and later
- OneNote for Windows 10 – Version 16.0.8431.1006 and later
- OneNote mobile app – Version 16.0.8431.1011 and later

Users don't need to sign in again or take any other action.

**Permissions** People who have permission to access the site can access the site during and after the site address change.

**Recent lists inside Office apps** The Word, Excel, and PowerPoint desktop apps and apps for the web will show the new URL after the change.

**Recycle bin** You can restore files in the recycle bin according to the usual deletion timeframe.

**SharePoint mobile apps for Android and iOS** The SharePoint mobile apps detect the site's new URL. Make sure that users have updated their apps to the latest version.

**SharePoint web parts** Any embedded URLs in any SharePoint web parts (News, List, etc.) won't be updated and may break. This includes page thumbnail images in news posts existing on the site. After the site address is changed, you might need to update individual web parts to use the new URL.

**SharePoint workflow 2013** SharePoint workflow 2013 will need to be republished after the site address is changed.

**Sharing links** After the site address is changed, sharing links will automatically redirect to the new URL.

**Site customizations and embedded code** You might need to fix site customizations and embedded code that refer to URLs after the site address change. Changing the site address preserves data stored in SharePoint but won't change URL dependencies in custom solutions.

**Synced locations** The OneDrive sync app will automatically detect and seamlessly transfer syncing to the new site URL after the site address has been changed. Users don't need to sign in again or take any other action. (Version 17.3.6943.0625 or later of the sync app required.) If a user updates a file while the site address is being changed, they see a message that file uploads are pending during the change.

**Microsoft 365 groups** The email address of the group won't be renamed. The group name is updated only if the site name is updated during the rename process.

**Teams (for Microsoft 365 group-connected sites)** When the site address change is complete, users are able to access their SharePoint files in the Teams app, with the following limitations.

| Functionality | Limitation |
| --- | --- |
| Viewing files in Teams | Files shared in channels before the address were changed can be viewed in the Teams app on the channel's Files tab. They can also be viewed in Office apps for the web from the channel's Files tab or the conversation. To view Word, Excel, and PowerPoint files in the desktop apps:Select the "Open in Desktop" option from the channel's Files tab.Open the file in the Office app for the web, and then select "Open in Desktop". |
| Uploading files to channels | Uploading files from a computer or OneDrive to a channel conversation will work after a user visits the Files tab for any channel in the site. |
| File app – Microsoft Teams page | The Microsoft Teams page in the Teams File app will work after a user visits the Files tab for any channel in the site. |
| Teams mobile app | Open and download will continue to work. To edit a Word, Excel, or PowerPoint file in the site, use the Office app for the web or the desktop app. Files shared after the site address was changed can be edited in the Office mobile apps. |

## How do I revert a site address change?

If you need to change the address of a site that was previously changed, we recommend not renaming the site again. This can cause issues if you later want to use the current address for another site. Instead, we recommend that you return the site to its original address. To do so, use an additional site rename and delete certain redirect sites. [Learn how to delete redirect sites](manage-site-redirects).

For a case where you changed https://contoso.sharepoint.com/sites/*project-x* to https://contoso.sharepoint.com/sites/*project-y* and want to revert back, the steps to follow are:

1. Delete the redirect from *project-x* to *project-y* by using the [Remove-SPOSite cmdlet](/en-us/powershell/module/sharepoint-online/remove-sposite) on the *project-x* address.
2. Initiate a new site address change from *project-y* to *project-x*.
3. Delete the redirect from *project-y* to *project-x* by using the [Remove-SPOSite cmdlet](/en-us/powershell/module/sharepoint-online/remove-sposite) on the *project-y* address.

    After following these steps, you should be back to the original state before the site address change.