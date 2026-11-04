---
layout: Conceptual
title: Find your Microsoft 365 tenant ID - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/find-your-office-365-tenant-id
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2024-11-05T00:00:00.0000000Z
ms.reviewer: jmcdowe
ms.author: v-mactran
author: MachelleTranMSFT
manager: jtremper
audience: Admin
f1.keywords:
- CSH
ms.topic: article
ms.service: onedrive
ms.localizationpriority: medium
ms.custom:
- Adm_O365
- onedrive-toc
- has-azure-ad-ps-ref
- azure-ad-ref-level-one-done
search.appverid:
- MET150
- BCS160
ms.collection:
- Strat_OD_admin
- M365-collaboration
ms.assetid: 6891b561-a52d-4ade-9f39-b492285e2c9b
description: Learn how to find the Microsoft 365 tenant ID using the Microsoft Entra admin center.
locale: en-us
document_id: cb41528c-2c8e-a58f-1439-e727faee3220
document_version_independent_id: d90aa109-379e-fa17-7b6a-b45911c99b35
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/find-your-office-365-tenant-id.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: find-your-office-365-tenant-id
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/find-your-office-365-tenant-id.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: a5553050-c8bc-fd68-b25f-46ee45c98f67
---

# Find your Microsoft 365 tenant ID - SharePoint in Microsoft 365 | Microsoft Learn

Your Microsoft 365 tenant ID is a globally unique identifier (GUID) that is different than your organization name or domain. You can use this identifier when configuring OneDrive policies.

## Find your Microsoft 365 tenant ID in the Microsoft Entra admin center

Your tenant ID can be found in the **Tenant ID** box on the [Overview page](https://entra.microsoft.com/#view/Microsoft_AAD_IAM/TenantOverview.ReactView).

[![Screenshot that shows the Directory Properties pane in the Entra Admin Center dashboard.](sharepointonline/media/find-m365-tenant-id-dashboard.png)](sharepointonline/media/find-m365-tenant-id-dashboard.png#lightbox)

Note

For info about finding your tenant ID by using PowerShell instead, first read [Microsoft Graph PowerShell](/en-us/powershell/microsoftgraph/installation?view=graph-powershell-1.0&amp;preserve-view=true) and then use [Get-MgOrganization](/en-us/powershell/module/microsoft.graph.identity.directorymanagement/get-mgorganization?view=graph-powershell-1.0&amp;preserve-view=true).