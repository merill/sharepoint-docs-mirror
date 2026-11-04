---
layout: Conceptual
title: Default SharePoint groups - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/default-sharepoint-groups
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-05-07T00:00:00.0000000Z
ms.reviewer: 
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
f1.keywords:
- NOCSH
ms.topic: reference
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Strat_OD_share
- M365-collaboration
ms.custom: admindeeplinkSPO
search.appverid:
- SPO160
- BSA160
- MET150
ms.assetid: 13bb2b6b-dd8c-447e-b71b-0e4bb9efe1d3
description: Learn what the default SharePoint groups are available for SharePoint sites in Microsoft 365.
locale: en-us
document_id: 815ec832-b81d-d057-27e6-a73ddf5a6632
document_version_independent_id: 7062cc8d-9769-3463-6b75-226679d720d1
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/default-sharepoint-groups.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: default-sharepoint-groups
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/default-sharepoint-groups.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 85ed1867-48ba-ad58-9b0e-3e0bcc96284e
---

# Default SharePoint groups - SharePoint in Microsoft 365 | Microsoft Learn

When you create a site (previously called a "site collection"), SharePoint automatically creates the default SharePoint groups. These default groups use SharePoint's default permission levels, which are sometimes called SharePoint roles, to grant users rights and access. The permission levels that these groups have represent common levels of access that users need. They're a good starting point when you add users to a SharePoint site.

Administrators can create extra groups to better align with specific business needs. How you design and populate your SharePoint groups affects security for your site and site content.

For more information about permissions, see the following articles:

- [Understanding permission levels in SharePoint](understanding-permission-levels)
- [Edit and manage permissions for a SharePoint list or library](https://support.office.com/article/02D770F3-59EB-4910-A608-5F84CC297782)

## Permission levels for default SharePoint groups

Use SharePoint groups to control access for sets of users instead of individual users. SharePoint groups usually consist of many individual users. They can also hold Microsoft Entra security groups (created in Microsoft 365 or Microsoft Entra ID), or they can be a combination of individual users and security groups.

Each SharePoint group has a permission level. A permission level is simply a collection of individual permissions, such as Open, View, Edit, or Delete. All the users in a group automatically have the permission level of the group. You can organize users into any number of groups, depending on the complexity of your organization or your needs.

Each site template has a set of SharePoint groups associated with it. When you create a site, you use a site template, and SharePoint automatically creates the correct set of SharePoint groups for the site. The specific collection of groups depends on the type of template that you choose.

For example, the following table shows the groups and permission levels that are created for team sites:

| SharePoint groups | Default permission level | Applies to team sites |
| --- | --- | --- |
| Approvers | Approve | No |
| Designers | Design, Limited Access | No |
| Hierarchy Managers | Manage Hierarchy | No |
| &lt;site name&gt; Members | Edit | Yes |
| &lt;site name&gt; Owners | Full Control | Yes |
| &lt;site name&gt; Visitors | Read | Yes |
| Restricted Readers | Restricted Read | No |
| Style Resource Readers | Limited Access | No |
| Quick Deploy Users | Contribute | No |
| Translation Managers | Limited Access | No |

## Suggested uses for SharePoint groups

The following table describes the SharePoint groups that are created when you use a standard site template to create a site. The table also provides suggested uses for each group.

| Group Name | Permission level | Use this group for |
| --- | --- | --- |
| Approvers | Approve | Members of this group can edit and approve pages, list items, and documents. |
| Designers | Design | Members of this group can edit lists, document libraries, and pages in the site. Designers can create Master Pages and Page Layouts in the Master Page Gallery and can change the behavior and appearance of each subsite by using master pages and CSS files. |
| Hierarchy Managers | Manage Hierarchy | Members of this group can create sites, lists, list items, and documents. |
| Owners | Full Control | People who must be able to manage site permissions, settings, and appearance. |
| Members | Edit or Contribute | People who must be able to edit site content. Permission level depends on the site template that was used to create the site |
| Visitors | Read | People who must be able to see site content, but not edit it. |
| Restricted Readers | Restricted Read | People who should be able to view pages and documents but not view versions or permissions. |
| Style Resource Readers | Restricted Read | People in this group have Limited Access to the Style Library and Master Page Gallery. |
| Quick Deploy Users | Contribute | These users can schedule Quick Deploy jobs (Content Deployment). |
| Viewers | View Only | These users see content, but can't edit or download it. |

## Special SharePoint Groups

"Everyone except external users" is a special group that doesn't appear in the Microsoft 365 admin center, and "Company Administrator" acts like a group but is a role in Microsoft Entra ID.

**Everyone except external users** All users added to your organization automatically become members of "Everyone except external users." You can't change default permissions granted to "Everyone except external users" on Microsoft 365 group-connected team sites. If a group-connected team site is set to "Public," then "Everyone except external users" has a default permission level of "Edit."

When a group-connected team site is set to "Private," then "Everyone except external users" can be manually added to the site through "Site permissions." To change the privacy setting for a group-connected team site, select the Settings icon, and then select **Site information**.

**Company Administrator** This group contains all users who are assigned the global admin role. For more info about this role and its permissions in Microsoft Entra ID, see [Company administrator](/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles#company-administrator). The root site for your organization is created with "Company Administrator" as the primary admin.

## Site administrators

| Description | SharePoint in Microsoft 365 | SharePoint Server |
| --- | --- | --- |
| Who can use this group? | Yes | Yes |

A site can have several site admins, but it must have one primary administrator. Any site admin can add or remove other admins. Site admins have full control of the site root and any subsites in the site, and can audit all site content.

In SharePoint Server, you designate a site collection administrator when you create a site.

## SharePoint admins

| Description | SharePoint in Microsoft 365 | SharePoint Server |
| --- | --- | --- |
| Who can use this group? | Yes | No, by default.  Requires special installation. |

In SharePoint in Microsoft 365, there's also a SharePoint admin. A SharePoint admin can use the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219) or PowerShell to manage settings for all sites. Any global admin in Microsoft 365 also has the permissions of a SharePoint admin. For more info about the SharePoint admin role, see [About the SharePoint admin role in Microsoft 365](sharepoint-admin-role).

If you're using SharePoint Server, you don't have a SharePoint admin or SharePoint admin center.