---
layout: Conceptual
title: Assign roles and permissions to manage term sets - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/assign-roles-and-permissions-to-manage-term-sets
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2018-07-11T00:00:00.0000000Z
ms.reviewer: shrganguly
ms.author: ruihu
author: maggierui
manager: jtremper
audience: End User
f1.keywords: NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: admindeeplinkSPO
search.appverid:
- SPO160
- OSU150
- MET150
ms.assetid: 951216b9-81ac-4850-9ea0-7ad4c45eb231
description: Learn about the roles for managing metadata term sets on a SharePoint site, and how to assign people to those roles
locale: en-us
document_id: b5356ce0-3900-09a4-c9e7-5d9804302f71
document_version_independent_id: 7136f8c3-11d7-1bec-9355-26e42787e0b2
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/assign-roles-and-permissions-to-manage-term-sets.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: assign-roles-and-permissions-to-manage-term-sets
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/assign-roles-and-permissions-to-manage-term-sets.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: b975e402-34b2-5e6e-a3f2-c4ae2e03bc54
---

# Assign roles and permissions to manage term sets - SharePoint in Microsoft 365 | Microsoft Learn

The tasks that you can do in the term store are determined by the specific role that you're assigned.

To be able to create or change a term, you must have one of three specific roles: term store admin, group manager, or contributor.

A term store admin can do these tasks:

- Create or delete term set groups.
- Add or remove group managers or contributors, or other term store admins
- Change the working languages for the term store.
- Any task that a group manager or contributor can do.

When you set up a term set, you can designate a group or a person as an Owner, Contact, or Stakeholders for the term set. These labels do not grant any specific permission to work with the term set. Instead, they provide a useful way to track the business owners or stakeholders for a term set.

## Add term store admins

1. In the SharePoint admin center, under **Content services**, select [**Term store**](https://go.microsoft.com/fwlink/?linkid=2185073).
2. In the tree view pane on the left, select the taxonomy.
3. In the **Term store** page, for **Admins**, select **Edit**. The **Edit term store admin** panel appears. Enter the names or email addresses of the people who you want to add as term store admins. Select **Save**.

## Add group managers

A group manager can do these tasks:

- Add or remove contributors.
- Any task that a contributor can do.

Important

You must be a term store admin to add new Group Managers.

To add a group manager:

1. In the SharePoint admin center, under **Content services**, select [**Term store**](https://go.microsoft.com/fwlink/?linkid=2185073).
2. In the tree view pane on the left, select the Group for which you want to add a Group Manager.
3. From the **People** page, select **Edit**. The **Edit name and description** panel appears. Add a term group name and description to help users understand the purpose of this term group. Select **Save**.
4. For **Group Managers**, to add people who can create new term groups, set and assign users to the group manager and contributor role, select **Edit**. The **Edit admins** panel appears. Enter the names or email addresses of the people who you want to add as Group Managers. Select **Save**.

## Add contributors

A contributor can create or change a term set.

You must be either a term store admin or a group manager of a specific group to add contributors to that group.

1. In the SharePoint admin center, under **Content services**, select [**Term store**](https://go.microsoft.com/fwlink/?linkid=2185073).
2. In the tree view pane on the left, select the Group to which you want to add a Contributor.
3. For **Contributors**, set and assign users to the group manager and contributor role, select **Edit**. The **Edit contributors** panel appears. Enter the names or email addresses of the people who you want to add as Contributors. Select **Save**.

## Metadata tasks that site users can perform

Site users who do not have an assigned role in the term store can use terms and terms sets in other ways.

Site members can do the following tasks with managed metadata:

- Update values in managed metadata columns (if terms sets associated with the columns are open and if the column lets fill-in choices).
- Add new terms to a term set when they update the value for a managed metadata column.
- Create new enterprise keywords when they update the enterprise keywords column for a list or library.
- Use metadata navigation in lists or libraries to filter the display of items.
- Use managed terms or enterprise keywords in search queries, and then refine search results based on these terms.

In addition, site users who have appropriate permissions (such as site owners) can create new managed metadata columns for lists, libraries, or content types. When site users create these columns, they can create new term sets that apply only to the site (previously called "site collection"), and they can manage the terms within these term sets.