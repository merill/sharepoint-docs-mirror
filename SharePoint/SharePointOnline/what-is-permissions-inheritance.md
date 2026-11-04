---
layout: Conceptual
title: What is permissions inheritance? - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/what-is-permissions-inheritance
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
ROBOTS: NOINDEX
f1.keywords:
- NOCSH
ms.topic: reference
ms.service: sharepoint-online
ms.subservice: admin
ms.collection: M365-collaboration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 06bb1ed1-d150-42f4-9600-fb261d4b590c
description: What is permissions inheritance in SharePoint.
locale: en-us
document_id: 1a18d328-f487-b16c-11d7-07bd63d88eb7
document_version_independent_id: 15445bd1-b63a-6fa3-a605-72d3e906aaf5
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/what-is-permissions-inheritance.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: what-is-permissions-inheritance
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/what-is-permissions-inheritance.md
platformId: d7aeb918-a0e6-037e-2f09-bd67aaab820a
---

# What is permissions inheritance? - SharePoint in Microsoft 365 | Microsoft Learn

While SharePoint offers extensive customization options for site permissions, including changing inheritance, don't break inheritance. Use the built-in SharePoint groups for communication sites, and manage team site permissions through the associated Microsoft 365 group. Use sharing links to share individual files and folders with people outside the site. This approach makes administration much easier. For more information about managing permissions in the SharePoint modern experience, see [Sharing and permissions in the SharePoint modern experience](modern-experience-sharing-permissions).

## What is permissions inheritance?

Permissions inheritance means that the permission settings of an element in a site collection are passed on to the children of that element. In this way, sites inherit permissions from the top-level ("root") site of the site collection, libraries inherit from the site that contains the library, and so on. Permission inheritance enables you to make a permission assignment once, and have that permission apply to all sites, lists, libraries, folders, and items that inherit permissions. This behavior can reduce complexity and the amount of time site collection administrators and site owners spend on security management.

By default, SharePoint sites inherit permissions from a parent site. When you assign a user to the Members group, the user's permissions automatically cascade through all the sites, lists, libraries, folders, and items that inherit the permission level.

## What is a parent in SharePoint permissions?

The term parent, when used in SharePoint permissions, emphasizes inheritance. The parent passes down its permission settings to all its children. By default, the root site of a site collection is the first parent for all the sites and other objects that are below it in the site hierarchy.

The root site of a site collection isn't the only parent. Every securable object (sites, libraries, lists, and so on) in a site collection can be a parent. That is, the root site is the parent of its subsites, each site is the parent of its libraries and lists, and each list is the parent of the list items in it. In this terminology, an object with a parent is known as a child. So, a subsite is the child of its parent site, a list item is the child of its list parent, and so on.

Important

Create a site collection for each unit of work instead of using subsites to create a hierarchical structure. [Learn about using hub sites to organize your intranet](planning-hub-sites).

By default, permissions are inherited from parent to child. That is, if you don't change the permission structure, a list item inherits permissions (through its parent list) from the root site in the collection. However, even if you break inheritance for a list, that list is still a parent for its own list items. The list items for the list inherit the permissions that the list has, and if you change the permissions for the list, the list items inherit the changes.

When you break the chain of inheritance from parent to child, the child starts with a copy of the parent's permissions. Then, you edit these permissions to make them the way that you want. You can add permissions, remove permissions, create special groups, and so on. None of the changes affect the original parent. If you decide that breaking inheritance was the wrong decision, you can resume inheriting permissions at any time.

When a user shares or stops sharing an item that contains other items with broken inheritance, a one-time push down of that permission addition or removal is sent to all child items, even those with broken inheritance. This rule applies to both direct permissions and sharing links. When managing permissions for an item with broken inheritance, users can remove any direct permissions on it. If an item with broken inheritance is accessible by a sharing link that was created on one of its parent folders and a user doesn't want that link to grant access to the item, users can either remove the link entirely or move the file outside of the folder for which sharing link has permissions.

## More about permissions inheritance

Permission inheritance enables an administrator to assign permission levels at one time, and have the permissions apply throughout the site collection. Permissions pass from parent to child throughout the SharePoint hierarchy, from the top level of a site to the bottom. Permission inheritance can save time for site administrators, especially on large or complex site collections.

However, some scenarios have different requirements. In one scenario, you might have to restrict access to a site because it contains sensitive information that you must protect. In a different scenario, you might want to expand access and invite others to share information. If you want, you can break the inheritance behavior (stop inheriting permissions) at any level in the hierarchy.

Let's look at examples of these different scenarios.

Suppose that you have a company called Northwind Traders. You create a communication site called "Benefits" with the URL northwindtraders.sharepoint.com/sites/benefits. At the site collection root, you set up SharePoint groups, assign permission levels, and add users to the groups.

Suppose then that you create subsites for the "Benefits" site, such as "Health care" (northwindtraders.sharepoint.com/sites/benefits/healthcare) and "Retirement" (northwindtraders.sharepoint.com/sites/benefits/retirement). These subsites could even contain more subsites. For example, the "Health care" subsite could have a "Dental" subsite (northwindtraders.sharepoint.com/sites/benefits/healthcare/dental).

### A scenario that uses default behavior

By default, permissions pass directly to subsites. That is, the groups and permission levels that you assigned at the site collection root pass down automatically to the subsite for reuse.

### A scenario that restricts access to a site and its children

Suppose that your company offers special benefits only for executives. In this case, the administrators decide to separate the "Executive" subsite and break inheritance from the parent site, "Benefits."

The site owners for the "Executive" site change the permissions for the site, removing some groups and creating others. The subsites of the "Executive" site, "Bonuses" and "Company transportation," now inherit permissions only from the "Executive" subsite. Only the groups and users for "Executive" can access the lists and libraries that contain sensitive information.

For ease of maintenance, use a similar method to restrict access. Organize your site so that sensitive material is in the same place. If you organize the site this way, you only have to break inheritance one time, for that specific site or library. This approach is much less overhead. It requires much less work than creating separate permission structures in many locations for individual subsites and libraries.

### A scenario that shares access to a folder and its children

Suppose that an employee at Northwind Traders hires consultants and wants to collaborate with them on documents in SharePoint. The employee doesn't want to give the consultants access to anything else on the SharePoint site.

When the employee shares the folder with the consultants, SharePoint automatically handles all the details of permissions and access by breaking inheritance on the folder itself. The consultants can access all the documents in the folder but can't view or access any other information on the site. Even though inheritance is technically broken, if you later add people to the parent site collection, you automatically give them permission to the shared folder.