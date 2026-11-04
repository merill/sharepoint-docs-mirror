---
layout: Conceptual
title: About the SharePoint Administrator role in Microsoft 365 - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/sharepoint-admin-role
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-05-29T00:00:00.0000000Z
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords:
- CSH
ms.topic: overview
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.custom:
- Adm_O365
- seo-marvel-apr2020
- admindeeplinkSPO
ms.collection:
- Strat_SP_admin
- M365-collaboration
- m365initiative-spsitemanagement
- essentials-manage
search.appverid:
- SPO160
- MOE150
- GEA150
- BSA160
- BCS160
- GSP150
- MET150
ms.assetid: f08144d5-9d50-4922-8e77-4e1a27b40705
description: Learn about the SharePoint Administrator role in Microsoft 365. SharePoint Administrators administer SharePoint and OneDrive in your organization.
locale: en-us
document_id: 7461c2ef-3439-2c86-4dde-8992b62bf9a7
document_version_independent_id: faa4e3aa-8ec4-f1f1-d4bd-4058999545f3
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/sharepoint-admin-role.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: sharepoint-admin-role
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/sharepoint-admin-role.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 63c626b9-6dea-8e26-3d40-e1a1dc5dfabc
---

# About the SharePoint Administrator role in Microsoft 365 - SharePoint in Microsoft 365 | Microsoft Learn

Users assigned the SharePoint Administrator role have access to the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219) and can create and manage sites, designate site admins, manage sharing settings, and manage Microsoft 365 groups, including creating, deleting, and restoring groups, and changing group owners.

Global Administrators in Microsoft 365 can assign users the SharePoint Administrator. The Global Administrator role already has all the permissions of the SharePoint Administrator role.

For info about assigning a user the SharePoint administrator role, see [Assign admin roles in the Microsoft 365 admin center](/en-us/microsoft-365/admin/add-users/assign-admin-roles). If a user's role is changed so they gain or lose access to the SharePoint admin center, it takes about an hour for the change to take effect.

Important

Microsoft recommends that you use roles with the fewest permissions. Using lower permissioned accounts helps improve security for your organization. Global Administrator is a highly privileged role that should be limited to emergency scenarios when you can't use an existing role.

#### Site management

Global Administrators and SharePoint Administrators don't have automatic access to all sites and each user's OneDrive, but they can give themselves access to any site or OneDrive. They can also use Microsoft PowerShell to manage SharePoint and OneDrive. See more about this role's [Key tasks of the SharePoint admin](sharepoint-admin-role#BK_KeyTasks).

Site admins have permission to manage sites, but they don't need to have an admin role in Microsoft 365, and don't have access to the SharePoint admin center.

For info about adding or removing a site admin, see [Manage site admins](manage-site-collection-administrators).

#### Term store administration

There's a separate role within SharePoint called the Term Store administrator. Users assigned to this role can add or change terms in the term store (a directory of common terms you want to use across your organization). To learn more, see [Assign roles and permissions to manage term sets](assign-roles-and-permissions-to-manage-term-sets).

#### API access

To manage API access in the SharePoint admin center, you need at least a [application administrator role](/en-us/entra/identity/role-based-access-control/permissions-reference#application-administrator). For more information, see [Manage access to Microsoft Entra ID-secured APIs](api-access).

## Key tasks of the SharePoint admin

Here are some of the key tasks users can do when they're assigned to the SharePoint Administrator role:

- [Create sites](create-site-collection)
- [Delete sites](delete-site-collection)
- [Manage sharing settings at the organization level](turn-external-sharing-on-or-off)
- [Add and remove site admins](manage-site-collection-administrators)
- [Manage site storage limits](manage-site-collection-storage-limits)