---
layout: Conceptual
title: Publish a content type - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/publish-content-type
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2020-06-19T00:00:00.0000000Z
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
description: Learn how to publish a content type from the SharePoint admin center.
locale: en-us
document_id: b52f3c87-422d-70ad-8b29-673b3913bfdd
document_version_independent_id: 35b68646-fd17-b7a7-524d-9385b1187382
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/publish-content-type.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: publish-content-type
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/publish-content-type.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: d866009a-cbc0-cfe3-c6c2-f9ab4ccc53aa
---

# Publish a content type - SharePoint in Microsoft 365 | Microsoft Learn

You can publish, unpublish, or republish content types in the content type hub at /sites/ContentTypeHub or from the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219).

**To publish, republish, or unpublish a content type**

1. Go to the [**Content type gallery** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185074), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization. The Content type gallery page isn't available if you have the global reader role.
2. Under the **Site content type** column, select the name of the site content type for which you want to manage updates. That site content type page appears.
3. In the menu bar, select **Publish**. The **Manage Publishing** panel appears.

    ![Manage publishing](sharepointonline/media/manage-publishing.png)
4. On the **Manage Publishing** page, do one of the following:

    - To make this content type available for download to all sites in the organization, select **Publish**.
    - To publish updates to this content type, select **Republish**.
    - To make this content type unavailable for download to sites in the organization, select **Unpublish**. Any copies of this content type being used in other sites will be converted to a local content type.
5. Select **Save**.