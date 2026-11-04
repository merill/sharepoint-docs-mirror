---
layout: Conceptual
title: Sharing errors in SharePoint and OneDrive - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/sharepoint-onedrive-error-message
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-05-07T00:00:00.0000000Z
ms.reviewer: srice
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
f1.keywords:
- NOCSH
ms.topic: article
ms.service: sharepoint-online
ms.subservice: admin
ms.collection: M365-collaboration
ms.custom: admindeeplinkSPO
ms.localizationpriority: high
search.appverid:
- SPO160
- MET150
description: Find the solution to SharePoint and OneDrive sharing errors
locale: en-us
document_id: 82cc67a6-222b-ac02-ab4e-5696ebba6da9
document_version_independent_id: b94e8ace-1824-e6df-375b-5f7b558348f4
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/sharepoint-onedrive-error-message.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: sharepoint-onedrive-error-message
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/sharepoint-onedrive-error-message.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
platformId: 2c8c4859-5e3e-0c9c-55a4-4cd3c7fa975d
---

# Sharing errors in SharePoint and OneDrive - SharePoint in Microsoft 365 | Microsoft Learn

This article covers the different errors that you might encounter when sharing files or folders from SharePoint or OneDrive in Microsoft 365. To fix these errors, you need to be a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [other administrator](/en-us/microsoft-365/admin/add-users/about-admin-roles) in your organization. If you're not an administrator, contact your help desk and give them your error code.

Changing these settings changes the types of external sharing that are allowed in your organization. In some cases, someone in your organization sets these settings for business reasons.

## OSE201

Error OSE201 indicates that external sharing is turned off for all of your SharePoint and OneDrive sites.

First, change the external sharing setting for your organization:

1. Go to [**Sharing** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185222), and sign in.

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then browse to the SharePoint admin center and open the Sharing page.
2. Under **External sharing**, for both SharePoint and OneDrive, select **Anyone** or **New and existing guests**.
3. Select **Save**.

Next, check the external sharing settings for the site that you want to share from.

### If you're sharing from a SharePoint site

1. In the new SharePoint admin center, select **Sites** &gt; [**Active sites**](https://go.microsoft.com/fwlink/?linkid=2185220).
2. Select the site that you want to share from, and then select **Sharing**.
3. Make sure that either **New and existing guests** or **Anyone** is selected. If you made changes, select **Save**.

Try sharing again.

### If you're sharing from OneDrive

1. In the Microsoft 365 admin center, in the left pane, under **Users**, select **Active users**.
2. Select the user, and then select the **OneDrive** tab.
3. Select **Manage external sharing**.
4. Make sure **Let people outside your organization access your site** is turned on, and **Allow sharing with anonymous guest links and authenticated users** or **Allow sharing to authenticated guest users with invitations** is selected.

Try sharing again.

## OSE202

Error OSE202 indicates you can share with only those guests who are already in your directory. You can [add guests directly through Microsoft Entra ID](/en-us/azure/active-directory/b2b/b2b-quickstart-add-guest-users-portal), or change the setting by following these steps:

First, change the external sharing setting for your organization.

1. Go to [**Sharing** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185222), and sign in.

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then browse to the SharePoint admin center and open the Sharing page.
2. Under **External sharing**, select **Anyone** or **New and existing guests** for both SharePoint and OneDrive.
3. Select **Save**.

Next, check the external sharing settings for the site that you want to share from.

### If you're sharing from a SharePoint site

1. In the navigation pane of the new SharePoint admin center, select **Sites** &gt; [**Active sites**](https://go.microsoft.com/fwlink/?linkid=2185220).
2. Select the site that you want to share from, and then select **Sharing**.
3. Make sure that either **New and existing guests** or **Anyone** is selected. If you made changes, select **Save**.

Try sharing again.

### If you're sharing from OneDrive

1. In the Microsoft 365 admin center, in the left pane, under **Users**, select **Active users**.
2. Select the user, and then select the **OneDrive** tab.
3. Select **Manage external sharing**.
4. Make sure **Let people outside your organization access your site** is turned on, and **Allow sharing with anonymous guest links and authenticated users** or **Allow sharing to authenticated guest users with invitations** is selected.

Try sharing again.

## OSE204

Error OSE204 indicates sharing is turned off for the site that you're trying to share from. In this scenario, change the setting as follows:

1. Go to [**Active sites** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185220), and sign in.

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the Active sites page.
2. Select the site that you want to share from, and then select **Sharing**.
3. Make sure that either **New and existing guests** or **Anyone** is selected, and then select **Save**.

Try sharing again.

## OSE205

Error OSE205 indicates you can share the site with only those guests who are already in your directory. You can [add guests directly through Microsoft Entra ID](/en-us/azure/active-directory/b2b/b2b-quickstart-add-guest-users-portal), or change the setting by doing the following steps:

1. Go to [**Active sites** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185220), and sign in.

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the Active sites page.
2. Select the site that you want to share from, and then select **Sharing**.
3. Make sure that either **New and existing guests** or **Anyone** is selected, and then select **Save**.

## OSE207

Error OSE207 indicates external sharing is turned off for OneDrive. In this scenario, change this setting as follows:

1. Go to [**Sharing** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185222), and sign in.

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then browse to the SharePoint admin center and open the Sharing page.
2. Under **External sharing**, select **Anyone** or **New and existing guests** for OneDrive.
3. Select **Save**.

Try sharing again.

## OSE208

Error OSE208 indicates you can share OneDrive files and folders with only those guests who are already in your directory. You can [add guests directly through Microsoft Entra ID](/en-us/azure/active-directory/b2b/b2b-quickstart-add-guest-users-portal), or change the setting by doing the following steps:

1. Go to [**Sharing** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185222), and sign in.

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then browse to the SharePoint admin center and open the Sharing page.
2. Under **External sharing**, change the OneDrive setting to either **Anyone** or **New and existing external users**.
3. Select **Save**.

Try sharing again.

## OSE303

Error OSE303 indicates the person sharing the file or folder isn't a member of the security groups that are allowed to share with guests and by using "Anyone" links. To change this setting:

1. Go to [**Sharing** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185222), and sign in.

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then browse to the SharePoint admin center and open the Sharing page.
2. Select **Limit external sharing to specific security groups**.
3. Under **Who can share outside your organization**, note the security groups listed for **Let only users in selected security groups share with authenticated external users and using anonymous links**. You need to add the user to one of the listed security groups. (Instead, you can clear the check box and remove the sharing restriction.)

### Add a user to a security group

1. On the [Groups page of the Microsoft 365 admin center](https://admin.microsoft.com/Adminportal/Home#/groups), find the group you want to edit.
2. Select the group. On the **Members** tab, select **View all and manage members**.
3. Select **Add members**.
4. Enter the user's name in the search box, select the check box in the results list, and then select **Save**.
5. Select **Close** three times.

Try sharing again.

## OSE304

Error OSE304 indicates the person sharing the file or folder isn't a member of the security groups that are allowed to share with guests. To change this setting:

1. Go to [**Sharing** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185222), and sign in.

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then browse to the SharePoint admin center and open the Sharing page.
2. Select **Limit external sharing to specific security groups**.
3. Under **Who can share outside your organization**, note the security groups listed for **Let only users in selected security groups share with authenticated external users**. You need to add the user to one of the listed security groups. (Instead, you can clear the check box and remove the sharing restriction.)

### Add a user to a security group

1. On the [Groups page of the Microsoft 365 admin center](https://admin.microsoft.com/Adminportal/Home#/groups), find the group you want to edit.
2. Select the group. On the **Members** tab, select **View all and manage members**.
3. Select **Add members**.
4. Enter the user's name in the search box, select the check box in the results list, and then select **Save**.
5. Select **Close** three times.

Try sharing again.

## OSE401

Error OSE401 indicates your organization-level setting lets you share with only people on specific domains. The person you're trying to share with isn't on one of the listed domains. To change this setting:

1. Go to [**Sharing** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185222), and sign in.

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then browse to the SharePoint admin center and open the Sharing page.
2. Under **Advanced settings for external sharing**, select **Add domains**, add the domain that you want to share with to the list of allowed domains, and select **OK**. Instead, you can turn off domain filtering by clearing the **Limit external sharing by domain** check box.
3. Select **Save**.

Try sharing again.

## OSE402

Error OSE402 indicates your organization-level setting blocks sharing with people on specific domains. The person you're trying to share with is on one of the listed domains. To change this setting:

1. Go to [**Sharing** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185222), and sign in.

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then browse to the SharePoint admin center and open the Sharing page.
2. Under **Advanced settings for external sharing**, select **Add domains**, remove the domain from the list of blocked domains, and select **OK**. Instead, you can turn off domain filtering by clearing the **Limit external sharing by domain** check box.
3. Select **Save**.

Try sharing again.

## OSE403

Error OSE403 indicates the site from which you're sharing lets you share with only people on specific domains. The person you're trying to share with isn't on one of the listed domains. To change this setting:

1. Go to [**More features** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185077), and sign in.

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.
2. Under **Classic site collections page**, select **Open**.
3. Select the site that you're sharing from, and in the ribbon, select **Sharing**.
4. Under **Site collection additional settings**, add the domain that you want to share with to the list of allowed domains. Instead, you can turn off domain filtering by clearing the **Limit external sharing using domains** check box.
5. Select **Save**.

Try sharing again.

## OSE404

Error OSE404 indicates the site from which you're sharing blocks sharing with people on specific domains. The person you're trying to share with is on one of the listed domains. To change this setting:

1. Go to [**More features** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185077), and sign in.

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.
2. Under **Classic site collections page**, select **Open**.
3. Select the site that you're sharing from, and in the ribbon, select **Sharing**.
4. Under **Site collection additional settings**, remove the domain that you want to share with from the list of blocked domains. Instead, you can turn off domain filtering by clearing the **Limit external sharing using domains** check box.
5. Select **Save**.

Try sharing again.