---
layout: Conceptual
title: Manage site admins - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/manage-site-collection-administrators
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2024-11-14T00:00:00.0000000Z
ms.reviewer: trgreen
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
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
ms.assetid: 9a7e46f9-3fc4-4297-955a-82cb292a5be0
description: Learn how global and SharePoint admins can add and remove site admins.
locale: en-us
document_id: 659548ea-eb6e-8eee-2892-f352512db6a1
document_version_independent_id: 2e0e6017-2b29-e831-ff61-0a798dfb175f
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/manage-site-collection-administrators.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-site-collection-administrators
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/manage-site-collection-administrators.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 74f1285a-240b-7485-8cd4-cf69d9ff8a6c
---

# Manage site admins - SharePoint in Microsoft 365 | Microsoft Learn

This article describes how a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) and [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365 can add and remove [site admins](/en-us/sharepoint/site-permissions#site-admins) (previously called "site collection admins"). If you're an owner of a communication site, or a site that belongs to a Microsoft 365 group, see [Manage your SharePoint site settings](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42#__BKMKMngSitePermissions) for info about giving people access to your site. If you're an admin for a classic site, see [Manage your SharePoint site settings](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42#id0eaabaaa=server).

Note

If you're a Global Administrator and want info about assigning other users the SharePoint Administrator role in Microsoft 365, see [Assigning admin permissions](/en-us/office365/admin/add-users/assign-admin-roles).Microsoft recommends that you use roles with the fewest permissions. Using lower permissioned accounts helps improve security for your organization. Global Administrator is a highly privileged role that should be limited to emergency scenarios when you can't use an existing role.

## Add or remove site admins in the new SharePoint admin center

By using the new [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219), you can change the owners for sites that use the new team site and communication site templates. You can also add and remove group members in the Microsoft 365 admin center. For info, see [Add or remove members from Microsoft 365 groups](/en-us/office365/admin/create-groups/add-or-remove-members-from-groups).

1. Go to [**Active sites** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185220), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the Active sites page.
2. In the left column, select a site.
3. Select **Membership** on the command bar to open the details panel. For a group-connected team site, you can add and remove group owners and additional site admins. For other sites, you can add and remove site admins and change the primary admin. Note that if you remove a person as a primary admin, they will still be listed as an additional admin. For info about each role, see [About site permissions](site-permissions).

    ![Changing admins for a team site](sharepointonline/media/change-admins.png)
4. In the details panel, you can add or remove the owners, members, site admins, site owners, site members, and site visitors.

    ![Screenshot of changing membership from details panel](sharepointonline/media/membership-details-panel.png)