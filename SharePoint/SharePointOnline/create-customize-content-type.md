---
layout: Conceptual
title: Create or customize a content type - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/create-customize-content-type
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-01-13T00:00:00.0000000Z
ms.reviewer: anfra
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
description: Learn how to create or customize a content type in the SharePoint admin center.
locale: en-us
document_id: 96aaa197-d69d-0cc1-aa52-7c1519442fc2
document_version_independent_id: a60ef9d8-b49f-c983-e4b6-0c30b388116c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/create-customize-content-type.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: create-customize-content-type
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/create-customize-content-type.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 2c225472-a66e-f838-9877-910186467359
---

# Create or customize a content type - SharePoint in Microsoft 365 | Microsoft Learn

Content types help make it easy to provide consistency across a site. You create or customize a content type with the characteristics that you want, such as a certain template, specific metadata, and so on. For example, when a user chooses an item from the **New Item** or **New Document** menu, you can ensure that customized content is used.

![New Document Menu](sharepointonline/media/new-document-menu.png)

Content types created in the SharePoint admin center are saved to the SharePoint content type hub located at /sites/ContentTypeHub.

To learn more about content types, see [Introduction to content types and content type publishing](https://support.microsoft.com/office/e1277a2e-a1e8-4473-9126-91a0647766e5).

To understand how the built-in content types relate to each other, see [SharePoint in Microsoft 365 default content type hierarchy](https://download.microsoft.com/download/0/b/b/0bb74648-212a-4c5d-b8a4-1b991dcf0a7d/sharepoint-default-content-types-hierarchy.pdf).

## Create a content type

1. Go to the [**Content type gallery** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185074), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization. The Content type gallery page isn't available if you have the global reader role.
2. Select **Create content type**. The **Create content type** panel appears.
3. On the **Create content type** panel, provide a name and description for the new content type.

    ![Create content type](sharepointonline/media/create-content-type.png)
4. In the **Category** section, you have two choices:

    - To put the new content type in an existing category, select **Use an existing category**, and from the **Name** dropdown, select a category.
    - To put the content in a new category, select **Create a new category**, and in the **Category name** box, provide a name.
5. In the **Parent content type** section, from the **Parent category** and **Content type** dropdowns, select the content type that you want to base this content type on.
6. Select **Create**.

The new content type appears in the **Content type gallery**.

## Change the name of a content type

1. Go to the [**Content type gallery** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185074), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization. The Content type gallery page isn't available if you have the global reader role.
2. Under the **Site content type** column, select the name of the site content type that you want to change.
3. On the content type page, on the menu bar, select **Edit**. The **Edit content type** panel appears.
4. In the **Name** text box, change the name of the content type.
5. Select **Save**.

## Associate a document template with a content type

To make sure that documents have consistent content across a site, you can associate a Word, Excel, or PowerPoint template with a site content type.

For example, you might want employees to use a standard Excel template when they create a weekly time sheet. If you associate the template with a Timesheet content type, every time someone uses the Timesheet content type, the correct template is automatically loaded in the worksheet.

You can make it even easier for users by adding the Timesheet content type to a library. Then, users can open the correct timesheet just by selecting **Timesheet** on the **New Documents** menu. To learn how to do this, see [Add a content type to a list or library](https://support.microsoft.com/office/917366ae-f7a2-47ad-87a5-9689a1884e60).

**To associate a template with a content type**

1. Go to the [**Content type gallery** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185074), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization. The Content type gallery page isn't available if you have the global reader role.
2. Under the **Site content type** column, select the name of the document-based content type that you want to change by associating a Word, Excel, or PowerPoint template.
3. In the menu bar, under **Settings**, select **Advanced Settings**. The **Advanced Settings** panel appears.
4. Enter the location of the template:

    - If the template is stored on your site, select **Use an existing template**, and then enter the URL for the template that you want to use. To edit the template, select **Edit template**.
    - If the document template is stored on your local computer, select **Upload a new document template**, and then select **Upload**. From the explorer page, locate the file that you want to use, select it, and then select **Open**.
5. Under **Permissions**, to select whether the content type can be modified, select either **Read** or **Edit**. You can change this setting later from this page by anyone with permissions to edit this content type.
6. Under **Update site and lists**, if you want to update all site and list content types that inherit from this content type with the settings on this page, select **Enable**.
7. Select **Save**.