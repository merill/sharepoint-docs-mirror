---
layout: Conceptual
title: Manage site creation in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/manage-site-creation
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-10-27T00:00:00.0000000Z
ms.reviewer: metorres
ms.author: ruihu
author: maggierui
manager: jtremper
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
- m365initiative-spsitemanagement
- essentials-manage
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
search.appverid:
- SPO160
- BSA160
- GSP150
- MET150
ms.assetid: e72844a3-0171-47c9-befb-e98b23e2dcf9
description: In this article, you learn how to allow or prevent users from creating their own sites in SharePoint.
locale: en-us
document_id: b29978b1-a400-bacb-1330-55ed3d652053
document_version_independent_id: eae9fd16-57fc-1a80-3ce9-9b34b68eb1e0
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/manage-site-creation.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-site-creation
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/manage-site-creation.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: ca050114-184f-e834-f607-2fe8f5ae674d
---

# Manage site creation in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn

As a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) and [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365, you can let your users create and manage their own SharePoint sites. You can decide what kind of sites they can create and where they can create them. By default, users can create communication sites and [Microsoft 365 group-connected team sites](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2).

Note

Disabling site creation for users doesn't remove their ability to create Microsoft 365 groups or resources, such as Microsoft Teams, that rely on a group. When a Microsoft 365 group is created, a SharePoint site is also created. To restrict creation of Microsoft 365 groups and the resources that rely on groups, see [Manage who can create Microsoft 365 Groups](/en-us/office365/admin/create-groups/manage-creation-of-groups).

## Manage site creation in the new SharePoint admin center

1. Go to **Settings** in the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185072), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), go to the SharePoint admin center, and then open the **Settings** page.
2. Select **Site creation**. The **Site creation** page appears:

    [![Screenshot of the Site creation page in the SharePoint admin center.](sharepointonline/media/site-creation-screen.png)](sharepointonline/media/site-creation-screen.png#lightbox)

    - To allow users to create sites, select **Allow** under **Control site creation from tools**. This setting controls whether users can create sites from SharePoint, OneDrive, the PnP PowerShell cmdlet, and the REST API. This setting doesn't affect whether users can create teams or Microsoft 365 groups and their connected sites.
    - To prevent users from creating a site with SharePoint built-in experience, do one of the following:

        - Add the destination URL by selecting **Redirect users to an organization approved request page** to your organization custom site provisioning flow
        - Select **Turn off the built-in SharePoint experience** under **Choose the SharePoint site creation experience**.

    Note

    Even if you clear these checkboxes, users might be able to create Microsoft 365 groups from other places in Microsoft 365. Each group always comes with a team site. [Learn how to manage who can create Microsoft 365 groups](/en-us/office365/admin/create-groups/manage-creation-of-groups).
3. Under /sites or /teams, select to create Microsoft 365 group-connected team sites, and then select the default time zone and storage limit for new sites.
4. Select **Save**.

## Manage detailed site and subsite creation settings in the classic SharePoint admin center

Admins in the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219) can choose to turn on or off subsite creation across sites or enable it for classic sites only. When you turn off subsite creation, the subsite option doesn't appear in the command bar, including in classic sites. Users also can't create new subsites directly through a URL or API.

Note

For information about classifying Microsoft 365 groups, see [Manage Microsoft 365 Groups with PowerShell](/en-us/office365/enterprise/manage-office-365-groups-with-powershell).

1. In the left pane of the new SharePoint admin center, select [**Settings**](https://go.microsoft.com/fwlink/?linkid=2185072). At the bottom of the page, select **classic settings page**.
2. Under **Site Creation**, select to show or hide the **Create site** command.

    [![Screenshot of Site creation settings in the classic SharePoint admin center.](sharepointonline/media/classic-site-creation-settings.png)](sharepointonline/media/classic-site-creation-settings.png#lightbox)

    - If you choose **Disable subsite creation for all sites**, it hides the subsite creation command (including classic) and prevents users from creating new subsites through a URL or API.
    - If you choose **Enable subsite creation for classic sites only**, users can create new subsites for classic sites.
    - If you choose **Enable subsite creation for all sites**, users can create new subsites from any SharePoint site.
3. Select **OK** when you're done.

Note

Creating a subsite in OneDrive isn't supported. Trying results in the following error: *New subsites aren't available in this site. Create a new site instead.*

Tip

Instead of using subsites, we recommend using hub sites. [SharePoint hub sites](https://support.microsoft.com/office/what-is-a-sharepoint-hub-site-fe26ae84-14b7-45b6-a6d1-948b3966427f) allow you to group similar articles and content together using modern architecture design. Plan to [create hub sites.](create-hub-site)