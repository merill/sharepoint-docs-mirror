---
layout: Conceptual
title: Use app-enforced restrictions - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/app-enforced-restrictions
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2020-10-07T00:00:00.0000000Z
ms.reviewer: samust
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords: NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Strat_SP_admin
- M365-collaboration
search.appverid:
- SPO160
- MET150
- BSA160
description: Learn how to set a conditional access policy in the Microsoft Entra admin center to use app-enforced restrictions in SharePoint.
locale: en-us
document_id: b03f90ae-ce47-fddb-bbd6-9c6310a6da44
document_version_independent_id: b06a11ec-975e-ae62-b0ad-c89e9bb50392
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/app-enforced-restrictions.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: app-enforced-restrictions
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/app-enforced-restrictions.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: e68b6dfc-affd-4162-1ec5-fef797057c2c
---

# Use app-enforced restrictions - SharePoint in Microsoft 365 | Microsoft Learn

These steps in the Microsoft Entra admin center tell Azure to use the SharePoint site-level access settings you specify.

1. On the [Conditional Access | Policies page](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) of the Microsoft Entra admin center, select **New policy**.

    ![Conditional access policies in the Microsoft Entra admin center](sharepointonline/media/azure-ca-new-policy.png)
2. In the **Name** box, type a name for the policy.
3. Select **Users and groups**, and then select whether you want the policy to apply to all users or only select users or groups.
4. Select **Cloud apps or actions**, select **Select apps**, search for **SharePoint**, select **Office 365 SharePoint Online**, and then select **Select**.

    ![Selecting the SharePoint app](sharepointonline/media/azure-ca-policy-cloud-app.png)
5. Select **Conditions**, select **Client apps**, switch **Configure** to **Yes**, keep all the clients selected, and then select **Done**.
6. Select **Session**, select **Use app enforced restrictions**, and then select **Select**.

    ![Selecting to control access using app enforced restrictions](sharepointonline/media/azure-ca-policy-session.png)
7. Enable the policy and select **Create**.