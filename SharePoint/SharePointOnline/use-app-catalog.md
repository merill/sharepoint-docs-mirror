---
layout: Conceptual
title: Manage apps using the Apps site - SharePoint - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/use-app-catalog
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-04-03T00:00:00.0000000Z
ms.reviewer: yihan1
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
f1.keywords:
- CSH
ms.topic: how-to
ms.custom:
- ManageAppCatalog
- seo-marvel-mar2020
- admindeeplinkSPO
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Strat_SP_admin
- M365-collaboration
- M365-sam
search.appverid:
- SPO160
- BSA160
- MET150
ms.assetid: 0b6ab336-8b83-423f-a06b-bcc52861cba0
description: Learn how to create and use the Apps site to manage custom business apps and apps from the SharePoint Store.
locale: en-us
document_id: 1bc1e9c0-2e35-3357-7f57-5bd02b0e10bc
document_version_independent_id: 1443a95a-ce5b-024d-d942-001b83bf8d8c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/use-app-catalog.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: use-app-catalog
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/use-app-catalog.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: c8b0dad6-ea8a-7eef-63ff-c27101d9853d
---

# Manage apps using the Apps site - SharePoint - SharePoint in Microsoft 365 | Microsoft Learn

As a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365, you can acquire solutions from the SharePoint Store or distribute custom apps that can be used across SharePoint, Microsoft Teams, and Viva Connections.

For information about your options for developing custom apps for SharePoint, see [Overview of the SharePoint Framework](/en-us/sharepoint/dev/spfx/sharepoint-framework-overview) and [SharePoint add-ins](/en-us/sharepoint/dev/sp-add-ins/sharepoint-add-ins).

Important

Starting April 2, 2026, SharePoint add-ins will be retired for SharePoint in Microsoft 365 and users will no longer be able to use SharePoint add-ins. Installing SharePoint add-ins from the SharePoint Store will not be possible as of July 1, 2024. [Learn more about the retirement of add-ins](/en-us/sharepoint/dev/sp-add-ins/retirement-announcement-for-add-ins).

## Add apps from the SharePoint Store

When you add an app from the SharePoint Store to the Apps site, you make it available for site owners to add from the My apps page.

1. Go to the [More features](https://go.microsoft.com/fwlink/?linkid=2185077) page in the SharePoint admin center and select **Open** under **Apps**.
2. On the Manage apps page, select **SharePoint Store** in the left pane.
3. Search for an app or select a category to scroll through available apps.
4. Select an app you want to add. In some cases, adding the app might be supported in the SharePoint Store classic experience only.
5. Select **Add to Apps site**.
6. Some apps can be added to all sites in the organization so that site owners don't have to. If you want to do this, select **Enable this app and add it to all sites**.
7. Select **Add**.
8. If the app requires additional permissions, a message appears. [Go to **API access page** in SharePoint admin Center to approve the permission requests](/en-us/sharepoint/api-access#approve-a-pending-request).

## Add custom apps

When you upload a custom app to the Apps site, it's available for users to install when they browse apps under **From Your Organization**.

1. Go to [**More features** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185077), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.
2. Under **Apps**, select **Open**.
3. On the Manage apps page, select **Upload**, and browse to the app you want upload, or drag the app into the library. SharePoint Framework solutions have the file name extension .sppkg.
4. Review the info in the **Enable app** panel. Depending on the functionality that the app provides, the developer can set a flag that allows you to add the app to all sites in the organization. To do this, select **Enable this app and add it to all sites**.

    ![Screenshot of the Enable app confirmation dialog box.](sharepointonline/media/apps-enable-app.png)

    If the app can be added to Teams, you can check the **Add to Teams** option that appears under **Enable this app and add it to all sites**.

    ![Screenshot of the Add to Teams box.](sharepointonline/media/apps-add-app-teams.png)

Note

We recommend testing solutions before deploying them broadly.

1. Select **Enable app** or **Add** for apps that can be added to Teams.
2. Select **Close**.
3. To help site owners identify and use the app, select the app, and then select **Properties**.

    ![Screenshot of the menu dropdown with Properties option.](sharepointonline/media/apps-select-properties.png)
4. Review and edit the **Name** for the app and enter optional information like a description, images, category, publisher, and support URL. Follow the instructions on the screen for details like image size.
5. Make sure the **Enabled** checkbox is selected so that users are able to add this app to sites.
6. If it appears, in the **Hosting Licenses** box, specify the number of licenses you think you need.
7. Close the panel.

## Add an app to all sites

App developers can choose to allow administrators to automatically add an app to all sites. This makes the app available for site owners.

If you didn't choose to add an app to all sites when you enabled it, you can do so later on the Apps site.

To add an app to all sites:

1. On the **Manage apps page**, select the app that you want to add to all sites.
2. Select **Add to all sites**.
3. Select **Confirm**.
4. Select **Close**.

## Stop automatically adding an app to new sites

If you chose to have an app automatically added to all sites, you can stop adding it to new sites by changing the setting on the Apps site.

To stop adding an app to new sites:

1. On the Manage apps page, select the app that you want to stop adding to new sites.
2. Select **Stop adding to new sites**.
3. Select **Save**.
4. Select **Close**.

## Add an app to Teams

Some apps can be added to Teams. You can add them on the Apps site.

To add an app to Teams:

1. On the Manage apps page, select the app that you want to add to Teams.
2. Select **Add to Teams**.

## Disable an app

If you want to prevent users from using an app that you've already enabled, you can disable it.

![screenshot of where to find the properties option.](sharepointonline/media/apps-properties.png)

1. On the Manage apps page, select the app that you want to disable, and then select **Properties**.
2. Clear the **Enabled** check box.
3. Close the panel.

## Delete an app from the Manage apps page

If you just want to remove an app from a specific site, see [Remove an app from a site](https://support.microsoft.com/office/remove-an-app-from-a-site-03198d1b-c33b-498d-9469-af641a587d6c).

If you no longer want a specific app to be available for users to add, you can delete it from on the Manage apps page. Any instances of the app that have already been added to sites by users remain, but the app is no longer available for users to add to more sites.

Important

If you delete an app, existing instances of the app will no longer work.

1. On the Manage apps page, select the app that you want to delete.
2. Select **Delete**.
3. Select **Delete** to confirm that you want to send the app to the recycle bin.