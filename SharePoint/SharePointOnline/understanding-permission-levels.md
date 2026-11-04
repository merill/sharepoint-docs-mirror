---
layout: Conceptual
title: Understanding permission levels in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/understanding-permission-levels
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-04-30T00:00:00.0000000Z
ms.reviewer: srice
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: reference
ms.service: sharepoint-online
ms.subservice: admin
ms.collection: M365-collaboration
ms.localizationpriority: high
ms.assetid: 87ecbb0e-6550-491a-8826-c075e4859848
description: Learn about permission levels in SharePoint and about the permissions that are associated with each level.
locale: en-us
document_id: 2f072d4a-23e6-d73f-397e-4ffc000570a9
document_version_independent_id: 1ee08317-82cd-9f23-a1e9-d2380fb7ff78
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/understanding-permission-levels.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: understanding-permission-levels
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/understanding-permission-levels.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 8fda7a60-ed2e-98d5-2b0b-db8947221ff9
---

# Understanding permission levels in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn

While SharePoint offers various permission levels for sites, use the built-in SharePoint groups for communication sites and manage team site permissions through the associated Microsoft 365 group. This approach makes administration easier. For information about managing permissions in the SharePoint modern experience, see [Sharing and permissions in the SharePoint modern experience](modern-experience-sharing-permissions).

## Understanding permission levels

The easiest way to work with permissions is to use the default groups and permission levels, which cover most common scenarios. But, if you need to, you can set more fine-grained permissions beyond the default levels. This article describes the different permissions and permission levels, how SharePoint groups and permissions work together, and how permissions cascade through a site collection.

Note

Want to go straight to the steps for changing or setting permission levels? See [How to create and edit Permission Levels](how-to-create-and-edit-permission-levels).

## Overview and permissions inheritance

If you work on a site, you're working inside a site collection. Every site exists in a site collection, which is a group of sites under a single top-level site. The top-level site is the root site of the site collection.

The following illustration of a site collection shows a simple hierarchy of sites, lists, and list items. The permissions scopes are numbered, starting at the broadest level at which you can set permissions, and ending at the narrowest level (a single item in a list).

![A graphic that shows SharePoint Security scopes at site, subsite, list, and item.](sharepointonline/media/b7cf87f3-578c-4605-bb31-9d2ecf88877e.png)

**Inheritance**

An important concept to understand is permissions inheritance. By design, all the sites and site content in a collection inherit the permissions settings of the root or top-level site. When you assign unique permissions to sites, libraries, and items, those items no longer inherit permissions from their parent site. Here's more information on how permissions work within the hierarchy:

- A site collection administrator configures permissions for the top level site or root site for the whole collection.
- If you're a site owner, you can change permission settings for the site, which stops permission inheritance for the site.
- Lists and libraries inherit permissions from the site to which they belong. If you're a site owner, you can stop permissions inheritance and change the permission settings for the list or library.
- List items and library files inherit permissions from their parent list or library. If you have control of a list or library, you can stop permissions inheritance and change permissions settings directly on a specific item.

    It's important to know that a user can interrupt the default permission inheritance for a list or library item by sharing a document or item with someone who doesn't have access. In that case, SharePoint automatically stops inheritance on the document.

## Default permission levels

Default permission levels make it easy to give common levels of permissions to one user or groups of users.

You can change any of the default permission levels, except **Full Control** and **Limited Access**. The following table describes these two permission levels.

| **Permission Level** | **Description** |
| --- | --- |
| Full Control | Contains all available SharePoint permissions. By default, the Owners group has this permission level. You can't customize or delete it. |
| Design | Create lists and document libraries, edit pages, and apply themes, borders, and style sheets on the site. No SharePoint group is automatically assigned this permission level. |
| Edit | Add, edit, and delete lists; view, add, update, and delete list items and documents. By default, the Members group has this permission level. |
| Contribute | View, add, update, and delete list items and documents. |
| Read | View pages and items in existing lists and document libraries and download documents. |
| Limited Access | Enables a user or group to browse to a site page or library to access a specific content item when they don't have permissions to open or edit any other items in the site or library. SharePoint automatically assigns this permission level when you provide access to one specific item. You can't assign Limited Access permissions directly to a user or group. Instead, when you assign edit or open permissions to the single item, SharePoint automatically assigns Limited Access to other required locations, such as the site or library in which the single item is located. This permission level allows SharePoint to render the user interface correctly and show the user some context around their location in the site. Limited Access doesn't grant any additional permissions to the user, so they can't see or access any other content. |
| Web-Only Limited Access | Web-Only Limited Access is a variant of the Limited Access permission level that enables users' access to the web object only. |
| Approve | Edit and approve pages, list items, and documents. By default, the *Approvers* group has this permission. |
| Manage Hierarchy | Create sites and edit pages, list items, and documents. By default, this permission level is assigned to the *Hierarchy Managers* group. |
| Restricted Read | View pages and documents, but not historical versions or user permissions. |
| View Only | View pages, items, and documents. Any document that has a server-side file handler can be viewed in the browser but not downloaded. File types that don't have a server-side file handler (can't be opened in the browser), such as video files and .png files, can still be downloaded. |
|  |  |

Note

Microsoft 365 subscriptions create a security group called "Everyone except external users" that contains every person you add into the Microsoft 365 directory (except people who you add explicitly as External Users). This security group is added to the Members group automatically on Modern Team sites with *Public* privacy settings, so that users in Microsoft 365 can access and edit the SharePoint site. Also, for Modern Team sites created as *Private*, "Everyone except external users" can't be granted any permissions and people must be explicitly granted permissions. In addition, Microsoft 365 subscriptions create a security group called "Company Administrators", which contains Microsoft 365 Admins (such as Global and Billing Admins). This security group is added to the Site Collection Administrators group. For more info, see [Default SharePoint groups](default-sharepoint-groups).

By default, site owners and members can add new users to the site.

To learn more about "Everyone except external users" permission, see [Special SharePoint Groups](default-sharepoint-groups#special-sharepoint-groups).

## Permission levels and SharePoint groups

Permission levels work together with SharePoint groups. A SharePoint group is a set of users who all have the same permission level.

The way this works is that you put related permissions together into a permission level. Then you assign that permission level to a SharePoint group.

![Site permission dialog under Site Settings/Users and Permissions/Site Permissions](sharepointonline/media/0ba0a6f9-4787-4088-bb53-6e8ff098cd42.png)

By default, each kind of SharePoint site includes certain SharePoint groups. For example, a Team Site automatically includes the Owners, Members, and Visitors group. A Publishing Portal site includes those groups and several more, such as Approvers, Designers, Hierarchy Managers, and so on. When you create a site, SharePoint automatically creates a pre-defined set of SharePoint groups for that site. In addition, a SharePoint admin can define custom groups and permission levels.

To learn more about SharePoint groups, see [Understanding SharePoint groups](default-sharepoint-groups).

The SharePoint groups and permission levels that are included by default in your site might differ, depending on:

- The template that you choose for the site
- Whether a SharePoint admin created a unique permissions set on the site that has a specific purpose, such as Search

The following table describes the default permission levels and associated permissions for three standard groups: Visitors, Members, and Owners.

| **Group** | **Permission level** |
| --- | --- |
| **Visitors** | **Read** This level includes these permissions:  Open  View Items, Versions, pages, and Application pages  Browse User Information  Create Alerts  Use Self-Service Site Creation  Use Remote Interfaces  Use Client Integration Features |
| **Members** | **Edit** This level includes all permissions in Read, plus:  View, add, update, and delete Items  Add, Edit, and Delete Lists  Delete Versions  Browse Directories  Edit Personal User Information  Manage Personal Views  Add, Update, or Remove Personal Web Parts |
| **Owners** | **Full Control** This level includes all available SharePoint permissions. |

## Site permissions and permission levels

Site permissions apply generally across a SharePoint site. The following table describes the permissions that apply to sites, and shows the permission levels that use them.

| **Permission** | **Full Control** | **Design** | **Edit** | **Contribute** | **Read** | **Limited Access** | **Approve** | **Manage Hierarchy** | **Restricted Read** | **View Only** |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Manage Permissions | X |  |  |  |  |  |  | X |  |  |
| View Web Analytics Data | X |  |  |  |  |  |  | X |  |  |
| Create Subsites | X |  |  |  |  |  |  | X |  |  |
| Manage Web Site | X |  |  |  |  |  |  | X |  |  |
| Add and Customize Pages | X | X |  |  |  |  |  | X |  |  |
| Apply Themes and Borders | X | X |  |  |  |  |  |  |  |  |
| Apply Style Sheets | X | X |  |  |  |  |  |  |  |  |
| Create Groups | X |  |  |  |  |  |  |  |  |  |
| Browse Directories | X | X | X | X |  |  | X | X |  |  |
| Use Self-Service Site Creation | X | X | X | X | X |  | X | X |  | X |
| View Pages | X | X | X | X | X |  | X | X | X | X |
| Enumerate Permissions | X |  |  |  |  |  |  | X |  |  |
| Browse User Information | X | X | X | X | X | X | X | X |  | X |
| Manage Alerts | X |  |  |  |  |  |  | X |  |  |
| Use Remote Interfaces | X | X | X | X | X |  | X | X |  | X |
| Use Client Integration Features | X | X | X | X | X | X | X | X |  | X |
| Open | X | X | X | X | X | X | X | X | X | X |
| Edit Personal User Information | X | X | X | X |  |  | X | X |  |  |

## List permissions and permission levels

List permissions apply to content in lists and libraries. The following table describes the permissions that apply to lists and libraries, and shows the permission levels that use them.

| **Permission** | **Full Control** | **Design** | **Edit** | **Contribute** | **Read** | **Limited Access** | **Approve** | **Manage Hierarchy** | **Restricted Read** | **View Only** |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Manage Lists | X | X | X |  |  |  |  | X |  |  |
| Override Check-Out | X | X |  |  |  |  | X | X |  |  |
| Add Items | X | X | X | X |  |  | X | X |  |  |
| Edit Items | X | X | X | X |  |  | X | X |  |  |
| Delete Items | X | X | X | X |  |  | X | X |  |  |
| View Items | X | X | X | X | X |  | X | X | X | X |
| Approve Items | X | X |  |  |  |  | X |  |  |  |
| Open Items | X | X | X | X | X |  | X | X | X |  |
| View Versions | X | X | X | X | X |  | X | X |  | X |
| Delete Versions | X | X | X | X |  |  | X | X |  |  |
| Create Alerts | X | X | X | X | X |  | X | X |  | X |
| View Application Pages | X | X | X | X | X |  | X | X |  | X |

## Personal permissions and permission levels

Personal permissions apply to content that belongs to a single user. The following table describes the permissions that apply to personal views and web parts, and shows the permission levels that use them.

| **Permission** | **Full Control** | **Design** | **Edit** | **Contribute** | **Read** | **Limited Access** | **Approve** | **Manage Hierarchy** | **Restricted Read** | **View Only** |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Manage Personal Views | X | X | X | X |  |  | X | X |  |  |
| Add/Remove Private Web Parts | X | X | X | X |  |  | X | X |  |  |
| Update Personal Web Parts | X | X | X | X |  |  | X | X |  |  |

## Permissions and dependent permissions

SharePoint permissions can depend on other SharePoint permissions. For example, you must be able to open an item to view it. In this way, View Items permission depends on Open permission.

When you select a SharePoint permission that depends on another, SharePoint automatically selects the associated permission. Similarly, when you clear SharePoint permission, SharePoint automatically clears any SharePoint permission that depends on it. For example, when you clear View Items, SharePoint automatically clears Manage Lists (you can't manage a list if you can't view an item).

Tip

The only SharePoint permission without a dependency is Open. All other SharePoint permissions depend on it. To test a custom permission level, you can just clear "Open". This action automatically clears all other permissions.

The following sections contain tables that describe SharePoint permissions for each permission category. For each permission, the table shows the dependent permissions.

- [Site permissions and dependent permissions](understanding-permission-levels#BKMK_Site_Dependent)
- [List permissions and dependent permissions](understanding-permission-levels#BKMK_listdependent)
- [Personal permissions and dependent permissions](understanding-permission-levels#BKMK_personaldependent)

**Site permissions and dependent permissions**

The following table describes the permissions that apply to sites, and shows the permissions that depend on them.

| **Permission** | **Description** | **Dependent permissions** |
| --- | --- | --- |
| Manage Permissions | Create and change permission levels on the website and assign permissions to users and groups. | View Items, Open Items, View Versions, View Pages, Browse Directories, Enumerate Permissions, Browse User Information, Open |
| View Web Analytics Data | View reports on website usage. | View Pages, Open |
| Create Subsites | Create subsites such as team sites, Meeting Workspace sites, and Document Workspace sites. | View Pages, Browse User Information, Open |
| Manage website | Perform all administration tasks for the website, which includes managing content. | View Pages, Add and Customize Pages, Browse Directories, Enumerate Permissions, Browse User Information, Open |
| Add and Customize Pages | Add, change, or delete HTML pages or Web Part pages, and edit the website by using a Windows SharePoint Services-compatible editor. | View Items, Browse Directories, View Pages, Open |
| Apply Themes and Borders | Apply a theme or borders to the whole website. | View Pages, Open |
| Apply Style Sheets | Apply a style sheet (.css file) to the website. | View Pages, Open |
| Create Groups | Create a group of users who can be used anywhere within the site collection. | View Pages, Browse User Information, Open |
| Browse Directories | Enumerate files and folders in a website, by using an interface such as SharePoint Designer or web-based Distributed Authoring and Versioning (Web DAV). | View Pages, Open |
| Use Self-Service Site Creation | Create a website by using Self-Service Site Creation. | View Pages, Browse User Information, Open |
| View Pages | View pages in a website. | Open |
| Enumerate Permissions | Enumerate permissions on the website, list, folder, document, or list item. | View Items, Open Items, View Versions, Browse Directories, View Pages, Browse User Information, Open |
| Browse User Information | View information about users of the website. | Open |
| Manage Alerts | Manage alerts for all users of the website | View Items, Create Alerts, View Pages, Open |
| Use Remote Interfaces | Use Simple Object Access Protocol (SOAP), Web DAV, or SharePoint Designer interfaces to access the website. | Open |
| Use Client Integration Features | Use features that launch client applications. | Use Remote Interfaces, Open |
| Open\* | Open a website, list, or folder to access items inside that container. | No dependent permissions |
| Edit Personal User Information | Allow a user to change personal information, such as adding a picture. | Browse User Information, Open |

**List permissions and dependent permissions**

The following table describes the permissions that apply to lists and libraries, and shows the permissions that depend on them.

| **Permission** | **Description** | **Dependent permissions** |
| --- | --- | --- |
| Manage Lists | Create and delete lists, add or remove columns in a list, and add or remove public views of a list. | View Items, View Pages, Open, Manage Personal Views |
| Override Check-Out | Discard or check in a document that is checked out to another user. | View Items, View Pages, Open |
| Add Items | Add items to lists, add documents to document libraries, and add web discussion comments. | View Items, View Pages, Open |
| Edit Items | Edit items in lists, edit documents in document libraries, edit web discussion comments in documents, and customize Web Part Pages in document libraries. | View Items, View Pages, Open |
| Delete Items | Delete items from a list, documents from a document library, and web discussion comments in documents. | View Items, View Pages, Open |
| View Items | View items in lists, documents in document libraries, and web discussion comments. | View Pages, Open |
| Approve Items | Approve a minor version of a list item or document. | Edit Items, View Items, View Pages, Open |
| Open Items | View the source of documents that use server-side file handlers. | View Items, View Pages, Open |
| View Versions | View past versions of a list item or document. | View Items, View Pages, Open |
| Delete Versions | Delete past versions of a list item or document. | View Items, View Versions, View Pages, Open |
| Create Alerts | Create e-mail alerts. | View Items, View Pages, Open |
| View Application Pages | View documents and views in a list or document library. | Open |

**Personal permissions and dependent permissions**

The following table describes the permissions that apply to personal views and web parts, and shows the permissions that depend on them.

| **Permission** | **Description** | **Dependent permissions** |
| --- | --- | --- |
| Manage Personal Views | Create, change, and delete personal views of lists. | View Items, View Pages, Open |
| Add/Remove Private Web Parts | Add or remove private Web Parts on a Web Part Page. | View Items, View Pages, Open, Update Personal Web Parts |
| Update Personal Web Parts | Update Web Parts to display personalized information. | View Items, View Pages, Open |

## Lockdown mode

*Limited-access user permission lockdown mode* is a [site collection feature](https://support.office.com/article/A2F2A5C2-093D-4897-8B7F-37F86D83DF04) that you can use to secure published sites. When you turn on lockdown mode, it reduces fine-grain permissions for the limited access permission level. The following table details the default permissions of the limited access permission level and the reduced permissions when the lockdown mode feature is turned on.

| **Permission** | **Limited access - default** | **Limited access - lockdown mode** |
| --- | --- | --- |
| List permissions: View Application Pages | X |  |
| Site permissions: Browse User Information | X | X |
| Site permissions: Use Remote Interfaces | X |  |
| Site permissions: Use Client Integration Features | X | X |
| Site permissions: Open | X | X |

Lockdown mode is on by default for all publishing sites, including if a legacy publishing site template is applied to the site collection. Lockdown mode is the recommended configuration if greater security on your sites is a requirement.

If you disable the limited-access user permission lockdown mode site collection feature, users in the "limited access" permissions level (such as Anonymous Users) can gain access to certain areas of your site.

## Plan your permission strategy

Now that you understand permissions, inheritance, and permission levels, plan your strategy. Set guidelines for your users, minimize maintenance, and ensure compliance with your organization's data governance policies. For tips on planning your strategy, see [Plan your permissions strategy](default-sharepoint-groups).