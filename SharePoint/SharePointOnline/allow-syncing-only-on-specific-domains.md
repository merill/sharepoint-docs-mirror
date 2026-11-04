---
layout: Conceptual
title: Allow syncing only on computers joined to specific domains - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/allow-syncing-only-on-specific-domains
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-12-19T00:00:00.0000000Z
ms.reviewer: gacarini
ms.author: v-mactran
author: MachelleTranMSFT
manager: jtremper
audience: Admin
customer-intent: As a SharePoint Administrator, I want to restrict OneDrive syncing to domain-joined computers so that I can ensure data security on managed devices.
f1.keywords:
- CSH
ms.topic: how-to
ms.service: onedrive
ms.localizationpriority: medium
ms.collection:
- Strat_OD_admin
- M365-collaboration
search.appverid:
- ODB160
- ODB150
- MET150
ms.assetid: a3b03efd-ccd0-4d3c-b9ae-7f8f3f9485bc
ms.custom:
- admindeeplinkSPO
- onedrive-toc
description: Learn how to restrict OneDrive syncing to only devices on specific domains.
locale: en-us
document_id: aff608fe-1f13-ad08-df3e-d2db050b87f8
document_version_independent_id: 32325172-804d-fac1-5deb-9e51ccc6dd75
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/allow-syncing-only-on-specific-domains.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: allow-syncing-only-on-specific-domains
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/allow-syncing-only-on-specific-domains.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 3fa21246-cef5-e41c-3e82-153deecadf73
---

# Allow syncing only on computers joined to specific domains - SharePoint in Microsoft 365 | Microsoft Learn

To ensure users sync OneDrive files only on managed computers, you can configure OneDrive to sync only on PCs joined to specific domains.

## How do I allow syncing only on PCs joined to specific domains?

Note

These settings apply to SharePoint sites and OneDrive. In a multi-geo environment, this setting can be configured separately for each geo location to apply to users with that preferred data location.

1. Go to [Settings in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185072){:target="\_blank"}, and sign in with an account that has [admin permissions](/en-us/sharepoint/sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the Sharing page.
2. Select **Sync**.

    ![Sync settings in the SharePoint admin center](sharepointonline/media/sp-sync-settings.png)
3. Select the **Allow syncing only on computers joined to specific domains** check box.
4. Enter the [GUID of each domain](/en-us/powershell/module/activedirectory/get-addomain) for the member computers that you want to be able to sync.

    Note

    Make sure to add the domain GUID of the computer domain membership. If users are in a separate domain, the only requirement is adding the domain GUID the computer account is joined to.

    Important

    This setting is only applicable to Active Directory domains. It doesn't apply to Microsoft Entra domains. If you have devices that are only Microsoft Entra joined, consider using a [Conditional Access Policy](/en-us/azure/active-directory/conditional-access/overview) instead. For details, see [Enable conditional access support in the OneDrive sync app](enable-conditional-access).
5. Select **Save**.

For info about setting this sync app restriction by using PowerShell, see [Set-SPOTenantSyncClientRestriction](/en-us/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction).

For information about blocking or limiting access to SharePoint and OneDrive content from unmanaged devices, see [SharePoint and OneDrive unmanaged device access controls for administrators](control-access-from-unmanaged-devices).