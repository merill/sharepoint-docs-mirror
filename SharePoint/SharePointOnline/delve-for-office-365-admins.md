---
layout: Conceptual
title: Delve for admins - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/delve-for-office-365-admins
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-03-10T00:00:00.0000000Z
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: overview
ms.service: sharepoint-online
ms.subservice: admin
ms.collection: M365-collaboration
ms.localizationpriority: medium
ms.custom: admindeeplinkSPO
search.appverid:
- SPO160
- MOE150
- DEL150
- FRP150
- MET150
ms.assetid: 54f87a42-15a4-44b4-9df0-d36287d9531b
description: The more you and your colleagues use Microsoft 365 to work together, by viewing, editing, and sharing each other's documents, the more useful Delve will be for all of you. Learn more about how you as an admin can help users get the most out of Delve.
locale: en-us
document_id: b21ad738-c2a1-ef1f-d745-eebe907311ac
document_version_independent_id: e931c7e1-fdb4-414b-986d-d7755fc797c4
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/delve-for-office-365-admins.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: delve-for-office-365-admins
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/delve-for-office-365-admins.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 5e0403c9-42af-6371-1050-50504ae03b50
---

# Delve for admins - SharePoint in Microsoft 365 | Microsoft Learn

Important

Delve was retired in December 2024. For more information, see [Guidance for retiring Delve in your organization](delve-retirement).

The more you and your colleagues use Microsoft 365 to work together by viewing, editing, and sharing each other's documents, the more useful [Delve](https://support.microsoft.com/office/what-is-delve-1315665a-c6af-4409-a28d-49f8916878ca) is for all of you. Learn more about how you as an admin can help users get the most out of Delve.

Delve is powered by the Microsoft Graph and shows users the most relevant content based on who they work with and what they're working on. The information in Delve is tailored to each user. Delve doesn't change permissions and users see only what they already have access to.

As an admin, you can make sure that your organization can access Delve, and that you set up other Microsoft 365 services that Delve uses, such as SharePoint and OneDrive. You can also help people get started with Delve, and address questions that users might have.

## What you need to get Delve

Delve is available for Microsoft 365 Enterprise (E1, E3, and E5), Microsoft 365 Education (E1, E3, and E5), Microsoft 365 Government (E1, E3, and E5), Microsoft 365 Business Basic, and Microsoft 365 Business Standard.

Regardless of which Microsoft 365 or Office 365 subscriptions you have, you need to activate the SharePoint service and assign users a SharePoint license before they can start using Delve. You also have to set up Exchange Online if you want attachments to show up on users' Home pages in Delve. If you set up Microsoft Teams, users can start Microsoft Teams conversations directly from Delve.

Important

Microsoft 365 apps and services ended support for Internet Explorer 11 on August 17, 2021 (Microsoft Teams ended support for Internet Explorer 11 earlier, on November 30, 2020). [Learn more](https://aka.ms/AA97tsw). IE mode enables backward compatibility and will be supported through at least 2029. Additionally, Microsoft will provide notice one year prior to retiring IE mode. Please [follow the Lifecycle Policy](/en-us/lifecycle/faq/internet-explorer-microsoft-edge) for the product on which it is installed.

The Delve app is also enabled for modern authentication. For more information, see [How modern authentication works](/en-us/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016).

## Control access to Delve

You control access to Delve from the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219). By default, users in your organization have access to Delve.

1. Go to [**Settings** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185072), and sign in with an account that has [admin permissions](/en-us/sharepoint/sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the **Settings** page.
2. At the bottom of the page, select **classic settings page**.
3. Under **Delve**, select one of the following options:

    - **Enable Delve**
    - **Disable Delve**

Note

Previously, when you turned Delve on or off in the SharePoint admin center, it also affected a few other insights-driven experiences in Microsoft 365. Starting July 1, 2021, the Delve setting is decoupled from the back end and only affects Delve. Use the item insights privacy settings to control item insights in Microsoft 365.

For more information about disabling Delve, see [What is the effect of enabling or disabling Delve](/en-us/sharepoint/delve-for-office-365-admins#BKMK_EffectOfficegraphOnOff).

### Control access to documents in Delve

Users can limit their Delve experience to only show profile information by turning off **Show documents in Delve** under **Settings** &gt; **Feature settings** in Delve. As an admin, you can also remove documents from Delve through the item insights privacy settings. For more information about item insights privacy settings, see [Customizing item insights privacy in Microsoft Graph (preview)](/en-us/graph/insights-customize-item-insights-privacy).

## Introducing Delve in your organization

Use these resources to get your organization started with Delve.

**Before you announce Delve**

- SharePoint and OneDrive are the primary sources of content in Delve. How you and users manage permissions on documents and sites affects what users see in Delve. For more info, see [Overview: best practices for managing how people use your team site](https://support.office.com/article/95e83c3d-e1b0-4aae-9d08-e94dcaa4942e) and [Plan your permissions strategy](/en-us/sharepoint/plan-your-permissions-strategy).

**Using Delve on a day-to-day basis**

- You can point users to the Delve help articles. [What is Delve?](https://support.office.com/article/1315665a-c6af-4409-a28d-49f8916878ca) is a great starting point, and users might be particularly interested in the information in the articles [Are my documents safe in Delve?](https://support.office.com/article/f5f409a2-37ed-4452-8f61-681e5e1836f3), [Connect and collaborate in Delve](https://support.office.com/article/46f92806-b52c-4187-b60e-b3bf8d25f73e), and [Store your documents where Delve can get to them](https://support.office.com/article/49a0db49-5e6c-4dda-816e-e11dd77de49d).

**Data and geographic region**

- When users go to Delve, for example by entering **delve.office.com** in a browser, they're automatically redirected to the geographic region where your organization's environment is located. After the redirect, a three letter prefix indicating the region is added to the URL, for example **https://nam.delve.office.com** for North America, or **https://eur.delve.office.com** for Europe.

## Help users troubleshoot Delve

To help troubleshoot issues with Delve, see the following info.

- [Users don't see Delve in the Microsoft 365 app launcher](delve-for-office-365-admins#BKMK_DelveGlobalNav)
- [Users see incorrect colleagues in Delve](delve-for-office-365-admins#BKMK_DelveIncorrectColleague)
- [Users don't see user pictures in Delve](delve-for-office-365-admins#BKMK_DelvePictures)
- [Users see documents from other users who have turned off Documents in Delve](delve-for-office-365-admins#BKMK_DelveOff)
- [Users see little or no content in Delve](delve-for-office-365-admins#BKMK_DelveNotMuchContent)
- [Users can't find a specific item in Delve](delve-for-office-365-admins#BKMK_DelveNoItem)
- [Users are concerned that private or sensitive documents are available in Delve](delve-for-office-365-admins#BKMK_DelveHide)

### Users don't see Delve in the Microsoft 365 app launcher

If one or more users in your organization don't see Delve in the app launcher, check the following settings. All these settings need to be in place for your organization before people can start using Delve.

#### Solutions

- Check that you allow your organization to access Delve.
- Check that you're using a subscription that supports Delve.
- Check that you've assigned the correct user licenses.

##### Check that you allow your organization to access Delve

1. Go to [**Settings** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185072), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the Settings page.
2. At the bottom of the page, select **classic settings page**.
3. Under **Delve**, make sure that you've selected **Enable Delve**.

    Note

    If you have a SharePoint standalone service (SharePoint Plan 1 or SharePoint Plan 2) you'll see the Delve setting in the SharePoint admin center. However, users won't be able to use Delve or see Delve in the app launcher, because Delve is not available for standalone services yet.

##### Check that you're using a subscription that supports Delve

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) as a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [other administrator](/en-us/microsoft-365/admin/add-users/about-admin-roles). (If you see a message that you don't have permission to access the page, you don't have Microsoft 365 admin permissions in your organization.)

    Note

    If you have Office 365 operated by 21Vianet (China), sign in at https://login.partner.microsoftonline.cn/. Then select the Admin tile to open the admin center.
2. In the left pane, select **Billing** &gt; **Licenses**.
3. Verify that you have one of the following subscriptions:

    - Office 365 Enterprise (E1, E3, or E5)
    - Office 365 Education
    - Office 365 Government (E1, E3, or E5)
    - Microsoft 365 Business Basic
    - Microsoft 365 Business Standard
    - Microsoft 365 Business Premium

##### Check that you've assigned the correct user licenses

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) as a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [other administrator](/en-us/microsoft-365/admin/add-users/about-admin-roles). (If you see a message that you don't have permission to access the page, you don't have Microsoft 365 admin permissions in your organization.)

    Note

    If you have Office 365 operated by 21Vianet (China), sign in at https://login.partner.microsoftonline.cn/. Then select the Admin tile to open the admin center.
2. Select **Users** &gt; **Active users**.
3. Select the box in front of the name of the user who you want to check the licenses for.
4. Verify that the user has one of the following combinations of licenses:

    - Office 365 Plan E1 plus SharePoint (Plan 1 or Plan 2)
    - Office 365 Plan E3 plus SharePoint (Plan 1 or Plan 2)
    - Office 365 Plan E5 plus SharePoint (Plan 1 or Plan 2)
    - Microsoft 365 Business Basic plus SharePoint (Plan 1 or Plan 2)
    - Microsoft 365 Business Standard plus SharePoint (Plan 1 or Plan 2)
    - Microsoft 365 Business Premium plus SharePoint (Plan 1 or Plan 2)

    For more information about how to manage licenses, see [Assign licenses to users](/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).

### Users see incorrect colleagues in Delve

If Microsoft Entra ID has outdated information or isn't synced with the SharePoint user profiles, Delve might not show the most relevant colleagues.

Delve uses information from user profiles to determine who users in your organization work with most closely. These profiles contain information from Microsoft Entra ID and from SharePoint user profiles. Every 24 hours, people information from Microsoft Entra ID is automatically added to SharePoint user profiles.

#### Solutions

- Check and clean up your Microsoft Entra ID, and wait for the information to sync to SharePoint user profiles.
- If you're an academic organization, the sync between Microsoft Entra ID and user profiles isn't automatic. Your users need to sign in to SharePoint at least once to create user profiles.
- If you have an on-premises Active Directory and if you set up Active Directory synchronization, make sure it's synced correctly with Microsoft Entra ID.

### Users don't see user pictures in Delve

The user pictures in Delve come from the SharePoint user profiles. If there's no picture for a user in their SharePoint user profile, Delve has no picture to show.

#### Solution

- Make sure that users upload their user profile picture to SharePoint. For more info, point users to [View and update your profile in Delve](https://support.office.com/article/4e84343b-eedf-45a1-aeb9-8627ccca14ba).

### Users see documents from other users who turn off documents in Delve

When users turn off documents in Delve, they don't see any documents in Delve, and Microsoft Graph excludes their **activities** and **relationships**.

However, if other users still have *access* to documents from a user who turns off documents, they can still see those documents in Delve, just as they can search for them in SharePoint.

Other information that's available to everyone in the organization is also visible even if a user turns off **Documents**, such as information from the Microsoft Entra ID.

#### Solution

- No action needed.

### Users see little or no content in Delve

Delve displays content from different content sources such as Exchange Online, SharePoint, and OneDrive.

If users don't have any recently modified or viewed content in these content sources, and they don't have access to other users' content, Delve might show little or no content. Users also need to have licenses to Microsoft 365 and Office 365 services and they need to have the item insights privacy settings enabled.

#### Solutions

- Encourage your users to store and share documents in SharePoint and OneDrive. For more info, point users to [Store your documents where Delve can get to them](https://support.office.com/article/49a0db49-5e6c-4dda-816e-e11dd77de49d).
- Check the permission settings on SharePoint sites to make sure that the user has access to the correct sites and their content.
- Check that the user is in Active Directory and a member of the correct Active Directory groups. To verify, go to **Microsoft 365 admin center** &gt; **Users** &gt; **Active Users**.
- Make sure that the user allows Delve to show documents. To verify, have the user go to **App launcher** &gt; **Delve** &gt; **Feature settings** and make sure that **Show documents in Delve** isn't turned off.
- Make sure that you assign users a license to access the Microsoft 365 services that you activate.

### Users can't find a specific item in Delve

Delve doesn't change any permissions and users only see what they already have access to. Not all content types appear in Delve, and it can take up to 24 hours for new documents to show up. Also, Delve prioritizes content that's been modified or viewed in the last three months.

#### Solutions

- Check the steps under [Users see little or no content in Delve](delve-for-office-365-admins#BKMK_DelveNotMuchContent).
- Check when the document was added. It can take up to 24 hours for new documents to show up in Delve.

### Users are concerned that private or sensitive documents appear in Delve

Any document that a user can view or edit in Microsoft 365 can also appear in Delve. Delve doesn't change any permissions, and users only see documents they already have access to. However, there are times when you might want to prevent a document from appearing in Delve.

**Solution(s)**

- Check the permission settings for the documents, sites and libraries and make sure that only the intended users have access to the content.

### What is the effect of enabling or disabling Delve?

When you change the Delve setting in the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219), you enable or disable the full Delve experience for all users in the tenant. If you enable Delve, users in your organization have Delve in the app launcher and they can use all the functionality in Delve. Selecting a person in Delve opens that person's page. The person page contains user profile information such as contact information and org chart details, and also documents relating to the person.

If you choose to disable Delve for your organization, Delve is removed from the app launcher for all users. When users visit a person's page, for example by clicking on a person in OneDrive, that person's page contains only user profile information. No documents are shown. Users can still search for other people, but not for documents or boards. If the Delve setting is disabled, users don't see the frequent sites and suggested sites in the SharePoint start page.

Note

Disabling Delve no longer disables *Microsoft Graph* or insights services generated on top of it. You can now control this level of control from the item insights privacy settings. For more information about the item insights settings, see [Customizing item insights privacy in Microsoft Graph](/en-us/graph/insights-customize-item-insights-privacy). For more information about Microsoft Graph, see [Overview of Microsoft Graph](/en-us/graph/overview).