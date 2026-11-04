---
layout: Conceptual
title: Allow only members in specific security groups to share SharePoint and OneDrive files and folders externally - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/manage-security-groups
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
f1.keywords: CSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Strat_OD_share
- M365-collaboration
ms.custom: admindeeplinkSPO
search.appverid:
- SPO160
- MET150
description: Learn how to manage security groups for sharing files and folders in SharePoint and OneDrive.
locale: en-us
document_id: ab9f7bfd-4962-7f83-b09c-6ee338296ec3
document_version_independent_id: d0fc2b43-93e7-a8c0-f541-557a65cc9256
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/manage-security-groups.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-security-groups
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/manage-security-groups.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
platformId: 7d3260f5-1f8f-bc9a-54b9-60b0fcb6fc8f
---

# Allow only members in specific security groups to share SharePoint and OneDrive files and folders externally - SharePoint in Microsoft 365 | Microsoft Learn

As a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [other administrator](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365, you can restrict external sharing of SharePoint and OneDrive content so that only users in specific security groups can share externally. The users in these security groups must be allowed to invite guests in the [Microsoft Entra guest invite settings](/en-us/azure/active-directory/external-identities/external-collaboration-settings-configure).

1. Go to [**Sharing** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185222), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.
2. Under **External sharing**, expand **More external sharing settings**.
3. Select **Allow only users in specific security groups to share externally**, and then select **Manage security groups**.

    ![Manage security groups](sharepointonline/media/manage-security-groups.png)
4. In the **Add a security group** box, search for and select the security groups you want to use (up to 12).
5. Next to the security group name, from the **Can share with** dropdown, select either:

    - **Authenticated guests only** (default)
    - **Anyone**
6. Select **Save**.

By selecting **Anyone**, users in that security group can share links to files and folders externally that don't require users to authenticate by using the **Anyone link** in the **Share** dialog box. Forwarded **Anyone links** work internally or externally, but you can't track who has access to shared items or who has accessed shared items. Users in this group can also share to authenticated guests. This option is best for friction-free sharing, provided files and folders in SharePoint and OneDrive aren't considered sensitive.

By selecting **Authenticated guests only**, sharing externally is limited to those guests who authenticate. This option is best for sharing sensitive or proprietary information because it requires guests to verify their identity before they can access the file or folder.