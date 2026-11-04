---
layout: Conceptual
title: Manage site storage limits in SharePoint in Microsoft 365 - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/manage-site-collection-storage-limits
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-07-30T00:00:00.0000000Z
ms.reviewer: trgreen
ms.author: deniseb
author: denisebmsft
manager: dansimp
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
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
search.appverid:
- SPO160
- BSA160
- GSP150
- MET150
ms.assetid: 77389c2c-8e7e-4b16-ab97-1c7103784b08
description: In this article, you'll learn how to use the SharePoint admin center to manage the storage limits for sites in your organization.
locale: en-us
document_id: d657793d-ad57-3801-6586-9c36b949386f
document_version_independent_id: ce570a07-c861-b43c-67c3-088780ee8fec
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/manage-site-collection-storage-limits.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-site-collection-storage-limits
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/manage-site-collection-storage-limits.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: f5636a18-b92e-7b13-0df0-c294b87909f6
---

# Manage site storage limits in SharePoint in Microsoft 365 - SharePoint in Microsoft 365 | Microsoft Learn

The amount of SharePoint space your organization has is based on the number of licenses (see [SharePoint Limits](/en-us/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)) you have. If you're a Global Administrator in Microsoft 365, you can [Add storage space for your subscription](/en-us/office365/admin/subscriptions-and-billing/add-storage-space) if you run out of storage space.

Important

Microsoft recommends that you use roles with the fewest permissions. Using lower permissioned accounts helps improve security for your organization. Global Administrator is a highly privileged role that should be limited to emergency scenarios when you can't use an existing role.

## View the total and available storage space for your organization

1. Go to [Active sites](https://go.microsoft.com/fwlink/?linkid=2185220) in the SharePoint admin center, and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.
2. In the upper right of the page, see the amount of storage available and the total storage for your subscription. (If your organization has configured Multi-Geo in Microsoft 365, you can point to the bar to see the amount of storage used in the current geo location and all other geo locations.)

    [![Storage bar on the Active sites page showing total and available storage space.](sharepointonline/media/active-sites-storage-bar.png)](sharepointonline/media/active-sites-storage-bar.png#lightbox)

    Note

    Storage usage doesn't include changes made within the last 24-48 hours. SharePoint storage is calculated in binary Gigabytes (GB), where 1 GB = 2^30^. Deleted sites in the Recycle Bin do not count toward the organization’s total storage usage.

## Set automatic or manual site storage limits

By default, your SharePoint storage is available in a central pool from which all sites can draw. You, as a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) and [above](/en-us/microsoft-365/admin/add-users/about-admin-roles), don't need to divvy up storage space or reallocate space based on usage. That's all handled automatically: sites use what they need when they need it. If you previously set storage limits manually and switch to using pooled storage, SharePoint resets all the limits to 25 TB (25600 GB). (Note that the total storage for your organization might be less than 25 TB.)

If you prefer to fine-tune the storage space allocated to each site, you can set your storage management option to "manual" and specify individual site storage limits.

Note

Some functionality is introduced gradually to organizations that have opted in to the [Targeted release option in Microsoft 365](/en-us/office365/admin/manage/release-options-in-office-365). This means that you might not yet see some features described in this article, or that some of the features (described in this article) might look different.

1. Go to [Settings](https://go.microsoft.com/fwlink/?linkid=2185072) in the SharePoint admin center, and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.
2. Select **Site storage limits**.

    [![Managing site storage limits in the SharePoint admin center.](sharepointonline/media/site-storage-limits.png)](sharepointonline/media/site-storage-limits.png#lightbox)
3. Select **Automatic** or **Manual**, and then select **Save**.

## Manage individual site storage limits

Follow these steps to specify individual site storage limits *when your storage management option is set to "manual."* We recommend that you also set an email alert so that you and the site owners can be notified when sites are nearing the storage limit. To learn how to set the default storage limit for new sites, see [Manage site creation](manage-site-creation).

1. Go to [Active sites](https://go.microsoft.com/fwlink/?linkid=2185220) in the SharePoint admin center, and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.
2. In the left column, select the site, or for a channel site, select the link in the **Channel sites** column.
3. On the **General** tab, under **Storage limit**, select **Edit** to open the edit storage limit panel.

    [![Changing the storage limit for a site in the SharePoint admin center.](sharepointonline/media/site-storage-limit.png)](sharepointonline/media/site-storage-limit.png#lightbox)
4. Enter the maximum storage in GB for the site.

    Note

    The maximum value you can enter is 25600 GB, although this may be more space than your organization has. To learn how your total storage is calculated, see [SharePoint Limits](/en-us/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits).
5. Make sure **Notifications** is turned on to send an email to site owners when the site approaches the storage limit. Then, enter a value as a percent for how full you want the storage to be when the email is sent.
6. Select **Save**.

If a site runs out of storage, site admins can request for more by performing the following steps:

1. Go to the Site Settings page.
2. Under **Site Collection Administration**, select **Storage Metrics**.

    Note

    Depending on your site, you may need to perform the following steps to see the **Site Collection Administration** section:

    On the upper right corner of your site, select **Settings** and then select **Site Settings**. If you don't see **Site settings**, select **Site information** and then select **View all site settings**.
3. Select **Request more quota** in the upper right.

This step sends a storage request email to the Global Administrators in the organization.