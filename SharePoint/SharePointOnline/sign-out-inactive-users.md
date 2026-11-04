---
layout: Conceptual
title: Sign out inactive users - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/sign-out-inactive-users
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-01-26T00:00:00.0000000Z
ms.reviewer: samust
manager: dansimp
ms.author: deniseb
author: denisebmsft
audience: Admin
f1.keywords:
- CSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Strat_SP_admin
- M365-collaboration
- M365-sam
ms.custom: admindeeplinkSPO
search.appverid:
- SPO160
- ODB160
- MET150
ms.assetid: 5d94efb4-ab46-429d-a021-d71eec787522
description: Learn how to set an idle session sign-out policy for SharePoint and OneDrive browser sessions on unmanaged devices.
locale: en-us
document_id: cfaf9fb8-afec-06b3-ed85-244a7af5b6dd
document_version_independent_id: 016c6f7d-8fd1-ba7f-ab54-a0ef1d34d026
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/sign-out-inactive-users.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: sign-out-inactive-users
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/sign-out-inactive-users.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 110cc4e9-a874-aae6-5c2d-4a46eb5a04b9
---

# Sign out inactive users - SharePoint in Microsoft 365 | Microsoft Learn

This article is for [SharePoint Administrators](/en-us/sharepoint/sharepoint-admin-role) or [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365 who want to control user access to SharePoint and OneDrive data on unmanaged devices. Idle session sign-out lets you specify a time at which users are warned and are later signed out of Microsoft 365 after a period of browser inactivity in SharePoint and OneDrive.

Note

- Idle session sign-out applies to the entire organization and can't be set for specific sites or users. To target different settings for different users, use Microsoft Entra Conditional Access policies instead (and see the next important note about the Microsoft Entra ID P1 or P2 requirement).
- This feature relies on Microsoft Entra Conditional Access policies being available. You need a Microsoft Entra ID P1 or P2 subscription for this to work. For more info about this, refer to the [Microsoft Entra licensing](/en-us/entra/fundamentals/licensing).

Idle session sign-out is one of many policies you can use with SharePoint and OneDrive to balance security and user productivity and help keep your data safe irrespective of where users access the data from, what device they're working on, and how secure their network connection is. For more ways to control access in SharePoint and OneDrive, see [How SharePoint and OneDrive safeguard your data in the cloud](safeguarding-your-data).

## The idle session sign-out experience

When a user is inactive in SharePoint and OneDrive for the time period you specify, the following message appears:

![Inactive Microsoft 365 sign out warning message](sharepointonline/media/80c0d10b-df78-4e3c-9df0-b94a923b3871.png)

Note

Activity is counted as requests sent to SharePoint, such as mouse clicks on a UI element like a button, list entry, or a link. Moving the mouse and scrolling aren't counted as activity.

If users don't select **Continue**, they're automatically signed out, and the following message appears.

![Microsoft 365 signed out due to inactivity message](sharepointonline/media/acc48304-dacd-41db-a4b6-8702cb6afa04.png)

Note

If a user is active in another Microsoft 365 service (such as Outlook), but inactive in SharePoint and OneDrive, they're signed out across Microsoft 365. If a user has multiple tabs to OneDrive and SharePoint sites open at the same time, they won't be signed out unless they're inactive on all the sites. Users won't be signed out if they selected to stay signed in when they signed in. For info about hiding this option, see [Add company branding to your sign-in page in Microsoft Entra ID](/en-us/azure/active-directory/fundamentals/customize-branding). Users won't be signed out on a managed device (one that is compliant or joined to a domain), unless they're using inPrivate mode or a browser other than Microsoft Edge or Internet Explorer. If they use Google Chrome, you need to use an extension to pass the device state claim. For more info about device state claims, see [Microsoft Entra Conditional Access settings](/en-us/azure/active-directory/conditional-access/concept-conditional-access-conditions).

Important

Microsoft 365 apps and services won't support Internet Explorer 11 starting August 17, 2021 (Microsoft Teams won't support Internet Explorer 11 earlier, starting November 30, 2020). [Learn more](https://aka.ms/AA97tsw). Please note that Internet Explorer 11 will remain a supported browser. Internet Explorer 11 is a component of the Windows operating system and [follows the Lifecycle Policy](/en-us/lifecycle/faq/internet-explorer-microsoft-edge) for the product on which it's installed.

## Specify idle session sign-out settings in the new SharePoint admin center

1. Go to [**Access control** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185071), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the Access control page.
2. Select **Idle session sign-out**.

    ![The Idle session sign-out panel](sharepointonline/media/idle-session-sign-out.png)
3. Turn on **Sign out inactive users automatically**, and then select when you want to sign out users and how much notice you want to give them before signing them out.
4. Select **Save**.

## Specify idle session sign-out settings by using PowerShell

1. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    Note

    If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell." On the Download Center page, select your language and then select the Download button. You'll be asked to choose between downloading a x64 and x86 .msi file. Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version. If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system) After the file downloads, run it and follow the steps in the Setup Wizard.
2. Connect to SharePoint as a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
3. Run the following command:

    ```PowerShell
    Set-SPOBrowserIdleSignOut -Enabled $true -WarnAfter (New-TimeSpan -Seconds 2700) -SignOutAfter (New-TimeSpan -Seconds 3600)
    ```

    Where:

    - **-Enabled** specifies whether idle session sign-out is enabled or disabled by using **$true** or **$false**.
    - **-WarnAfter** specifies the amount of after which a user is notified that they'll be signed out after a period of inactivity as a **New-TimeSpan** which can be configured in seconds, minutes, or hours.
    - **-SignOutAfter** specifies the amount of time after which is a user is signed out of Microsoft 365 if they don't respond to the **-WarnAfter** prompt.

Note

You must specify values for both **WarnAfter** and **SignOutAfter**. The **SignOutAfter** must be greater than the **WarnAfter** value.

It takes about 15 minutes for the policy to take effect across your organization. The policy doesn't affect existing sessions. To view the idle session sign-out values you've set, use **Get-SPOBrowserIdleSignOut**.

For info about Microsoft 365 session lengths (regardless of activity), see [Session timeouts for Microsoft 365](/en-us/office365/enterprise/session-timeouts).