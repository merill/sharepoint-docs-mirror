---
layout: Conceptual
title: deprecation of site mailboxes - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/deprecation-of-site-mailboxes
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2020-09-15T00:00:00.0000000Z
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords: 
ms.topic: article
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
search.appverid: 
ms.collection: 
ms.custom: 
description: In this article, you'll learn how to identify and remove site mailboxes.
locale: en-us
document_id: 889b5920-e016-8e4e-0f1d-a000e1e2b3ea
document_version_independent_id: db1175d4-a795-f397-fe32-d54e5ec6ad4c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/deprecation-of-site-mailboxes.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: deprecation-of-site-mailboxes
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/deprecation-of-site-mailboxes.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: ace0d163-7c21-311f-c34f-32132407d7b0
---

# deprecation of site mailboxes - SharePoint in Microsoft 365 | Microsoft Learn

The site mailboxes are being retired and will be out of service and/or removed. Use the following instructions to identify, backup, and delete site mailboxes.

## To view a list of site mailboxes

Run the following command in Exchange PowerShell:

```powershell
Get-SiteMailbox -BypassOwnerCheck -ResultSize Unlimited | ft Name, WhenCreated, ClosedTime, SharePointUrl -AutoSize
```

The 'create' date shows the recently created site mailboxes. The 'ClosedTime' in the output of 'Get-SiteMailbox' refers to the status of the associated SharePoint site. The companies set a SharePoint policy to close sites after a period of time or provide users permission to close the sites. Closing the site generally means it's out of service. Closed site mailboxes are removed from view in the Outlook desktop client, but they're available in the Outlook Web Access.

For more information, see, [Use policies for site closure and deletion](https://support.office.com/article/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5).

## To identify active site mailboxes

Run the following command in Exchange PowerShell:

```powershell
# If you run this more than once, delete/rename the output file first because this command appends to it.
# This is a single, long command line. It could take minutes or hours depending on the number of site mailboxes; thus, the countdown.
$sms = Get-SiteMailbox -BypassOwnerCheck -ResultSize unlimited;$count = $sms.Count; $sms | %{ $count-- ; echo "$count";Get-MailboxFolderStatistics $_.Identity -FolderScope Inbox | sort LastModifiedTime -Descending | ft Identity,LastModifiedTime >> c:\temp\sitemailboxes.txt};Write-Host "Open file c:\temp\sitemailboxes.txt to check the result"
```

There are no commands to show if the site mailboxes are still active. The above example lists the number of site mailboxes that were recently updated. The details of the site mailboxes are stored in a file.

Note

The processing time varies based on the number of site mailboxes. You can open the 'sitemailboxes.txt' to view the result of the command.

## To Identify the owners of site mailboxes

Run the following command in Exchange PowerShell:

```powershell
Get-SiteMailbox -BypassOwnerCheck -ResultSize unlimited | ft Name, Owners
```

## Export site mailboxes through PST (Manually)

You must have [Microsoft 365 admin permissions](/en-us/microsoft-365/admin/add-users/assign-admin-roles) to access the [Microsoft Purview portal](/en-us/purview/purview-portal).

For more information, see [Permissions and sharing](modern-experience-sharing-permissions).

1. Go to https://purview.microsoft.com/ and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.
2. In the Microsoft Purview portal Home page, navigate to **eDiscovery**.
3. Select **Create a case**.
4. In **New case** details pane, enter the following details:

    - Enter the **Case name** (mandatory).
    - Enter the **Case description** (optional).
5. Select **Save**.
6. Select the case that you saved from the list view and select ![](sharepointonline/media/icon-for-im3.png) to open the case.

    The case opens in a new window.
7. Select **Search** &gt; **+Guided search**.

    The **New Search** details pane is displayed.
8. In the **New search** details pane, under the following tabs:

    1. In **Name your search** tab, do the following:

        1. Enter the **Name** (mandatory).
        2. Enter **Description** (optional).
        3. Select **Next**.
    2. In **Choose Locations** tab, do the following:

        1. Select **Specific locations**.
        2. In **Location**, select **Choose users, groups, or team**.

            The **Edit locations** window is displayed.
        3. In **Edit locations** window, under **Exchange email**, select **Choose users, groups, or team**.
        4. Enter the name of the site mailbox to be exported.
        5. Check the confirmation box to ensure the site mailbox is added.
        6. Select **Choose** and then select **Done**.
        7. Under **SharePoint sites** option, select **Choose sites** to add the SharePoint site associated with the site mailbox.
        8. To find the SharePoint URL for the site mailbox, run the following command in PowerShell:

            ```powershell
            Get-SiteMailbox -BypassOwnerCheck -ResultSize unlimited
            ```
        9. Enter the URL and check the confirmation box to ensure the URL is added.
        10. Select **Choose** and then select **Done**.
        11. Select **Next**.
    3. In **Create query** tab, select **Finish**.

        Note

        Leave the Condition card blank to ensure the entire mailbox content is searched. The search will take a while based on the amount of content.
9. Once the search is complete, select **More** &gt; **Export results**.

    The **Export results** window is displayed.
10. Select the appropriate options and select **Export**.

    Note

    The export wizard takes a few minutes to launch the Export window.
11. In the **Export** window, under the **Export key** section, select **Copy to clipboard**.
12. Select **Download results**.
13. In the dialog box, select **Open**.

    Note

    This will launch the Microsoft Office 365 eDiscovery Export Tool to export the mailbox to PST.
14. Select **Install** to install the **Export Tool** to export the mailbox to PST.
15. Paste the **Export key**, provide the location to save the PST file locally and then select **Start**.

    Note

    The export will take a while based on the size of the PST file.
16. Select **Close**.

    The PST can be now attached in Outlook.

Note

- Folders with no email items inside them will not be exported.
- The site mailboxes contain a special folder named, "Documents", of type IPF.ShortcutFolder. This contains "links" to files that are on SP sites. The actual SP files must be exported using eDiscovery for SP sites.
- Outlook shows the items inside the Documents folder as unsafe, this is an expected behavior.
- The document attachments in the emails of Documents folders are just placeholders, the actual documents are stored in SharePoint.

## Export site mailboxes to PST (using script)

1. Copy [process-site-mailboxes.ps1](https://github.com/MicrosoftDocs/OfficeDocs-SharePoint/blob/public/SharePoint/SharePointOnline/spodownloads/process-site-mailboxes.ps1) to a working directory.
2. Start Windows PowerShell in administrator mode.

    For more information, see, [Microsoft 365 admin permissions](/en-us/microsoft-365/admin/add-users/assign-admin-roles).

    Note

    Ensure you have admin permissions for the following roles:

    - Compliance Administrator
    - eDiscovery Manager
    - Organization Management
3. Run the script 'process-site-mailboxes.ps1' in PowerShell.
4. Enter the admin username and password when prompted.
5. You can review the list of site mailboxes by opening 'SiteMailboxesList.csv' file on a working directory, when it prompts you to review the file.
6. Remove any site mailbox(es) from the list which you wouldn't like to back up.
7. Save 'SiteMailboxesList.csv', after reviewing it.
8. Press 'y' when prompted "Do you like to proceed further? (Y/N)" to continue.
9. Once you get "Mailboxes content search are complete" message on your screen, access the export results created for each mailbox by going to the Microsoft Purview portal.

    Note

    Use Compliance center dashboard to download PST messages on your screen.

Note

- Folders with no email items inside them will not be exported.
- The site mailboxes contain a special folder named, "Documents", of type IPF.ShortcutFolder. This contains "links" to files that are on SP sites. The actual SP files must be exported using eDiscovery for SP sites.
- Outlook shows the items inside the Documents folder as unsafe, this is an expected behavior.
- The document attachments in the emails of Documents folders are just placeholders, the actual documents are stored in SharePoint.

## Import site mailboxes

For the site mailboxes to be accessible again for site owners, import the PST files to a mailbox. See one of the following articles for detailed, step-by-step instructions for bulk-importing your organization's PST files to Office 365.

- [Use network upload to import PST files to Office 365](/en-us/microsoft-365/compliance/use-network-upload-to-import-pst-files)
- [Use drive shipping to import PST files](/en-us/microsoft-365/compliance/use-drive-shipping-to-import-pst-files-to-office-365)

## Use Exchange Web Services (EWS) APIs to extract mailbox content

You can also export and import site mailboxes using EWS APIs like any other mailbox. Exporting and importing of appointments, emails, contacts, tasks, and other mailbox items can be done by using the EWS-Managed API or EWS in Exchange.

For more information, see, [Exporting and importing items by using EWS in Exchange](/en-us/exchange/client-developer/exchange-web-services/exporting-and-importing-items-by-using-ews-in-exchange).

See one of the following articles for exporting and importing of mailbox content:

- [Export items by using EWS in Exchange](/en-us/exchange/client-developer/exchange-web-services/how-to-export-items-by-using-ews-in-exchange)
- [Import items by using EWS in Exchange](/en-us/exchange/client-developer/exchange-web-services/how-to-import-items-by-using-ews-in-exchange)

## To remove the site mailboxes

Use one of the following options:

**Option 1**: Hiding the mailbox from a SharePoint site.

You can hide the site mailbox by removing it from the SharePoint site but it will still exist in Exchange. You can access the mailbox through Outlook Web Access if the browser is bookmarked.

1. Navigate to the SharePoint site from which you want to hide the mailbox.
2. Select **Settings** &gt; **Site contents**.
3. Under **Lists, Libraries, and other APPs**, point to **Site Mailbox**, and then click **...** for more information.
4. Select **Remove** and then select **OK** to remove the site mailbox app.

    Note

    If you remove a mailbox from a site, it won't be displayed on the site, but it will still be visible in Outlook (if you're using Exchange).

#### What else do I need to know?

There are a couple of things worth noting about removing a site mailbox:

- The only way to fully delete a site mailbox is to [delete the entire site itself](https://support.microsoft.com/office/delete-a-sharepoint-site-or-subsite-bc37b743-0cef-475e-9a8c-8fc4d40179fb). When a site is closed or deleted (either manually, or by following [site closure policies](https://support.microsoft.com/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5)), the site mailbox is also closed or deleted.
- After removing the site mailbox app from a site, mail sent to the mailbox will still be stored. If you [add the mailbox back to the site](https://support.microsoft.com/office/add-a-site-mailbox-to-keep-email-in-context-cccaa235-c611-48e3-9653-0b9e161840e7) later, any mail sent to the site mailbox since it was originally created will still be there.

**Option 2**: Delete the SharePoint site.

If the SharePoint site is deleted, Exchange is notified to also delete the site mailbox.

1. Navigate to the SharePoint site you want to delete.
2. Select **Settings** at the top of the site and then select **Site information**.

    Note

    If you don't see **Site information** in the **Settings** panel, work with your SharePoint Administrator to get access.
3. At the bottom of the **Site Information** panel, select **Delete site**.
4. Check the confirmation box, and then select **Delete**.

**Option 3**: Delete the site mailbox manually.

For example, run the following command in Exchange PowerShell:

```powershell
Get-Mailbox MDEL:* | ?{$_.RecipientTypeDetails -eq "TeamMailbox"} | Remove-Mailbox -Confirm:$false
```

Use `Remove-Mailbox` to delete a site mailbox. The system removes the site mailbox link from the SharePoint site when a site mailbox is deleted. In the example, change the 'MDEL' to the name of the site mailbox you want to delete.