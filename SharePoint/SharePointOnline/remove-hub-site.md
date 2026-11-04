---
layout: Conceptual
title: Remove a hub site - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/remove-hub-site
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2018-07-11T00:00:00.0000000Z
ms.reviewer: metorres
ms.author: ruihu
author: maggierui
manager: jtremper
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
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
search.appverid:
- SPO160
- MET150
ms.assetid: 8b1f8b6b-09c6-41c9-b1ca-88cbeee86ba2
description: In this article, you learn about how to remove (unregister) a hub site so that it no longer remains a hub site.
locale: en-us
document_id: 96fc2661-679c-dff4-7e87-651f0b154513
document_version_independent_id: 9a0a4a29-c1e9-572a-9009-ed3c320a070d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/remove-hub-site.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: remove-hub-site
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/remove-hub-site.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 1e7ef931-3571-6532-5366-be53cac86688
---

# Remove a hub site - SharePoint in Microsoft 365 | Microsoft Learn

If you're a user who has [SharePoint administrator](/en-us/sharepoint/site-permissions#site-admins) or [above](/en-us/sharepoint/site-permissions) permissions in Microsoft 365, you can make a hub site no longer a hub site (unregister it as a hub site). Make sure you do this before you delete the hub site. When you unregister a hub site, the associated sites won't automatically disassociate from the hub site. Disassociating a site removes the hub site navigation bar from the top of the site. The look that the site inherited from the hub site stays the same and features such as additional navigation links, applications, or custom lists with specific columns that were added as part of the inherited hub site design will remain. Any hub-site-related web parts added to the home page will only show information from the site instead of from sites associated with the hub.

## Unregister a hub site in the new SharePoint admin center

1. Go to [**Active sites** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185220), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the Active sites page.
2. Select the site, select **Hub** on the command bar, and then select **Unregister as hub site**.

    ![Unregistering a hub site](sharepointonline/media/unregister-hub-site.png)
3. Select **OK**.