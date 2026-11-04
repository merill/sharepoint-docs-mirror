---
layout: Conceptual
title: Remove users from SharePoint - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/remove-users
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-05-29T00:00:00.0000000Z
ms.reviewer: jmcdowe
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords:
- CSH
ms.topic: troubleshooting-general
ms.custom:
- ViewUserProfiles
- SPOTAMgUserProfiles
- seo-marvel-apr2020
ms.service: sharepoint-online
ms.subservice: admin
ms.collection: M365-collaboration
ms.localizationpriority: medium
search.appverid:
- SPO160
- MOE150
- BSA160
- GSP150
- MET150
ms.assetid: 494bec9c-6654-41f0-920f-f7f937ea9723
description: In this article, you learn how to troubleshoot user profile removal issues in SharePoint and Remove users from SharePoint.
locale: en-us
document_id: 50aa0393-41e2-de3b-4380-74bf012a7914
document_version_independent_id: 09b51e37-62d7-01f8-9d34-723b03b8ee80
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/remove-users.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: remove-users
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/remove-users.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 73863d8f-07c6-1780-dcaa-10e7f25eeb0b
---

# Remove users from SharePoint - SharePoint in Microsoft 365 | Microsoft Learn

This article describes how to remove users so they no longer appear in SharePoint. It should be used to troubleshoot Profile Property synchronization or mismatched ID issues only as advised by Microsoft Customer Support Services.

- **Scenario 1: Someone is deleted from the Microsoft 365 admin center but still appears in SharePoint.**

    When a user or guest browses to a SharePoint site, their user information is cached in the UserInfo list. When the user or guest is deleted, their related UserInfo information isn't removed. Their profile still appears, which may cause confusion when people view the people picker.
- **Scenario 2: [Site User ID Mismatch](/en-us/sharepoint/troubleshoot/sharing-and-permissions/fix-site-user-id-mismatch).**

    This issue most frequently occurs when a user is deleted and the account is then re-created with the same user name. The account in the Microsoft 365 admin center or Active Directory (in directory synchronization scenarios) is deleted and re-created with the same user principal name (UPN). The new account is created by using a different ID value. When the user tries to access a site collection or their OneDrive, the user has an incorrect ID. A second scenario involves directory synchronization with an Active Directory organizational unit (OU). If users have already signed in to SharePoint, and then are moved to a different OU and resynced with SharePoint, they may experience this problem.

## Delete a user from the Microsoft 365 admin center

For the steps to delete a user in the Microsoft 365 admin center, see [Delete a user from your organization](/en-us/office365/admin/add-users/delete-a-user).

Note

If you're using directory synchronization, you must remove the user from the on-premises Active Directory environment.

After you delete a user, a series of jobs will remove the user from SharePoint. After the next incremental profile import job, the user (or users) will be marked as deleted, the user's profile page will be deleted, and the user's OneDrive will be marked for deletion by the MySite cleanup job.

## Delete a guest from the Microsoft 365 admin center

1. Sign in to https://admin.microsoft.com as a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) and [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365. (If you see a message that you don't have permission to access the page, you don't have Microsoft 365 admin permissions in your organization.)

    Note

    If you have Office 365 operated by 21Vianet (China), sign in at https://login.partner.microsoftonline.cn/. Then select the Admin tile to open the admin center.
2. In the left pane, select **Users** &gt; **Guest users**.
3. Select the user, then select **Delete a user**.

## Delete a guest user using Microsoft Graph PowerShell

1. **Install Microsoft Graph PowerShell Module:**

    - Open PowerShell with elevated permissions (right-click on your Start menu or press Windows key + X).
    - Type the following command and press Enter:

        ```PowerShell
        Install-Module -Name Microsoft.Graph
        ```
    - When prompted, type "Y" to install the NuGet provider.
2. **Connect to Microsoft Graph:**

    - Now that the Microsoft Graph module is installed, connect to Microsoft Graph using the following command:

        ```PowerShell
        Connect-MgGraph -Scopes "User.ReadWrite.All", "Group.ReadWrite.All"
        ```
    - Enter your admin credentials when prompted.
3. **Get the Guest User's UPN/Object ID:**

    - Once connected, run the following command to get a list of all user accounts in your tenant:

        ```PowerShell
        Get-MgUser -All | Format-List  ID, DisplayName, Mail, UserPrincipalName
        ```
    - Note down the UPN or Object ID of the guest user you want to remove.
4. **Remove the Guest User:**

    - Run the following command to remove the specified guest user (replace `TestUser@example.com` with the actual UPN or Object ID):

        ```PowerShell
        Remove-MgUser -UserId "TestUser@contoso.com#EXT#@contoso.onmicrosoft.com"
        ```
    - This command will permanently remove the user from Microsoft Entra ID.

## Remove people from the UserInfo list

The preceding steps removed access to Microsoft 365 and SharePoint. However, the user or guest still appears in people searches and in the SharePoint Online Management Shell when you use the Get-SPOUser cmdlet. To completely remove people from SharePoint, you must remove them from the UserInfo list. There are two ways to do this:

### Browsing site by site in SharePoint

You have to browse to each site collection that the user or guest visited, and then follow these steps:

Note

This option is available only if the user previously browsed to the site collection. They won't be listed if they were granted access but never visited the site.

1. Browse to the site and edit the URL by adding the following string to the end of it: **/\_layouts/15/people.aspx?MembershipGroupId=0**

    For example, the full URL resembles the following: **`https://fabrikam.sharepoint.com/_layouts/15/people.aspx?membershipGroupId=0`.**
2. Select the person from the list, and then on the **Actions** menu, select **Delete Users from Site Collection**.

### Using the SharePoint Online Management Shell

1. [Install the SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
2. Connect to SharePoint as a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
3. Run the following command for each site collection that the user or guest visited:

    ```PowerShell
    Remove-SPOUser -Site https://fabrikam.sharepoint.com/sites/sc1 -LoginName jondoe@fabrikam.com
    ```

    Note

    Replace the *jondoe@fabrikam.com* placeholder with the person in question.

## Clear browser history

SharePoint uses browser caching in several scenarios, including in the people picker. Even when a user is fully removed, he or she may still remain in the browser cache. Clearing the browser history resolves this issue. For info about doing this in Microsoft Edge, see [View and delete browser history in Microsoft Edge](https://support.microsoft.com/help/10607).

When you clear the browser history, make sure that you also select to clear cookies and website data.