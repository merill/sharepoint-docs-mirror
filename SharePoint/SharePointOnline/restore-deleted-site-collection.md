---
layout: Conceptual
title: Restore deleted sites - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/restore-deleted-site-collection
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-05-29T00:00:00.0000000Z
ms.reviewer: trgreen
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
- m365initiative-spsitemanagement
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
search.appverid:
- SPO160
- MET150
ms.assetid: 91c18651-c017-47d1-9c27-3a22f325d6f1
description: Learn how to restore deleted sites in the SharePoint admin center.
locale: en-us
document_id: 7d19f5be-8567-336b-cc14-357b20278585
document_version_independent_id: f82afd3a-5e89-fbc2-564a-c49a507de22a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/restore-deleted-site-collection.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: restore-deleted-site-collection
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/restore-deleted-site-collection.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 3a53bbdc-042c-f28b-51fa-65f99fd65231
---

# Restore deleted sites - SharePoint in Microsoft 365 | Microsoft Learn

Deleted SharePoint sites are retained for 93 days. After 93 days, sites and all their content and settings are permanently deleted, including lists, libraries, pages, and any subsites.

Note

If you need to retain content for a minimum period of time to comply with industry regulations or internal policies, you can create a retention policy to keep a copy of it in the Preservation Hold library. For info, see [Overview of retention policies](/en-us/office365/securitycompliance/retention-policies).

For info about restoring items within a site, see [Restore items in the Recycle Bin of a SharePoint site](https://support.office.com/article/6df466b6-55f2-4898-8d6e-c0dff851a0be).

For info about restoring deleted sites in SharePoint Server, see [Restore deleted site collections using Microsoft PowerShell](/en-us/powershell/module/sharepoint-server/restore-spdeletedsite).

## Restore a deleted site in the new SharePoint admin center

In the new SharePoint admin center, you can delete and restore all the new types of sites with the permissions of a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [more](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365.

1. Go to [**Deleted sites** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185070), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the Deleted sites page.

    ![Screenshot that shows Deleted sites in the new SharePoint admin center](sharepointonline/media/b195b8c7-ee2b-4a02-92cb-ed61899edd24.png)

    Note

    You can sort and filter deleted sites the same way you sort and filter sites on the Active sites page. You can also sort and filter deleted sites by Time deleted.
2. Select the site you want to restore.
3. Select **Restore**. (If you don't see the **Restore** button, make sure only one site is selected. The button won't appear if multiple sites are selected.)

Note

Restoring a site that belongs to a Microsoft 365 group restores the Microsoft 365 group and all its resources. The other group resources are retained for only 30 days, whereas the site is retained for 93. If the other group resources have been deleted, you can use the PowerShell command [Remove-SPODeletedSite](/en-us/powershell/module/sharepoint-online/remove-spodeletedsite) to permanently delete the site. For info about permanently deleting sites from the Deleted sites page, see [Permanently delete a deleted site](delete-site-collection#permanently-delete-a-site).