---
layout: Conceptual
title: Add columns to a content type - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/add-columns-content-type
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2020-06-18T00:00:00.0000000Z
ms.reviewer: shrganguly
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords: NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.collection:
- M365-collaboration
ms.custom: admindeeplinkSPO
description: Learn how to add columns to a content type in the SharePoint admin center.
locale: en-us
document_id: 53ec2e16-d8d6-f2a4-b248-824b263ca5dd
document_version_independent_id: a1150243-2a49-cc7c-0f7b-0a9f72f6f65d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/add-columns-content-type.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: add-columns-content-type
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/add-columns-content-type.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: bc0a7abe-aa55-0de0-0a63-10d34dfb0cf2
---

# Add columns to a content type - SharePoint in Microsoft 365 | Microsoft Learn

The columns for a content type represent metadata. To add a metadata element, add a new column.

For example, your organization might want to track specific metadata for purchase orders, such as account number, project number, and project manager. If you add columns for this information to the purchase order content type, SharePoint prompts users to provide the information when they save their work. In addition, if you add the content type to a list or library, you can define a view to display the columns.

You can customize content types by adding columns of the types you need. You can also change the order of columns and specify if they are required fields.

## Add a column to a content type

To add a column to a content type, follow these steps:

1. Go to [Content type gallery in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185074), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization. The Content type gallery page isn't available if you have the global reader role.
2. Under the **Site content type** column, select the name of the site content type to which you want to add a column.
3. Under **Site columns**, from the **Add site column** dropdown, select **Add from existing site columns**. The **Add from existing site columns** panel appears.
4. In the **Select site columns from existing category** section, select **Add** or **Remove** to add or remove columns from the choices that appear. You can choose a category to narrow the list of available columns.
5. In the **Update List and Site Content Types** section, decide whether you want to update all site and content types that inherit from this content type with the settings on this page.
6. Select **Save**.

## Change column order

To change column order for a content type, follow these steps.

**To change column order on a content type**

1. Go to [Content type gallery in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185074), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization. The Content type gallery page isn't available if you have the global reader role.
2. Under the **Site content type** column, select the name of the site content type to which you want to change a column's order. That site content type page appears.
3. Under **Site columns**, in the **Name** column, select the column that you want to change its order.
4. Select the vertical ellipsis to the right of the site column name you selected, and from the dropdown, select **Reorder site columns** and then select from the following four choices:

    - **Move to top**
    - **Move up**
    - **Move down**
    - **Move to bottom**

## Make a column required, optional, or hidden

To make a column required, optional, or hidden, follow these steps.

**To make a column required, optional, or hidden**

1. Go to [Content type gallery in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185074), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization. The Content type gallery page isn't available if you have the global reader role.
2. Under the **Site content type** column, select the name of the site content type that you want to change a site content type by adding a column. That site content type page appears.
3. Under **Site columns**, in the **Name** column, select the name of the column that you want to make optional, required, or hidden.
4. Select **Edit site column settings**. The **Edit site column settings** panel appears.
5. In the **Show or hide site column** section, do one of the following:

    - To show or hide this column in lists, check or clear **Show this column in lists**, respectively.
    - To make it optional for users to specify information for a column, select **Optional (may contain information)**.
    - To require users to specify information for a column, select **Required (must contain information)**.
6. Under **Update sites and lists**, if you want to update all site and list content types that inherit from this content type with the settings on this page, check the box.
7. Select **Save**.

Note

When you update the column name of an existing site column that is part of a published content type from the content type hub, ensure that the language of the target site and the language of the browser are the same for the latest site column name to appear correctly after the sync completes.