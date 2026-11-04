---
layout: Conceptual
title: Domain restrictions when sharing SharePoint & OneDrive content - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/restricted-domains-sharing
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
audience: End User
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- Strat_OD_share
- M365-collaboration
ms.custom:
- seo-marvel-mar2020
- admindeeplinkSPO
search.appverid: MET150
ms.assetid: 5d7589cd-0997-4a00-a2ba-2320ec49c4e9
description: Allow sharing only with guests on specific domains, or block sharing with guests on specific domains.
locale: en-us
document_id: f3e6adf5-c322-b7f1-9359-1f9e0723374b
document_version_independent_id: 0071fb22-d32b-da3f-aec1-60772b341bd0
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/restricted-domains-sharing.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: restricted-domains-sharing
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/restricted-domains-sharing.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
platformId: 42b50687-3825-df4e-3ac9-eff4d764addb
---

# Domain restrictions when sharing SharePoint & OneDrive content - SharePoint in Microsoft 365 | Microsoft Learn

To restrict sharing with other organizations, either at the organization level or site level, limit sharing by domain.

Note

If you enroll in the [SharePoint and OneDrive integration with Microsoft Entra B2B](sharepoint-azureb2b-integration), SharePoint invitations also follow any [domain restrictions configured in Microsoft Entra ID](/en-us/azure/active-directory/b2b/allow-deny-list).

## Limiting domains

You can limit domains by allowing only the domains you specify or by allowing all domains except those you block.

### Limit domains at the organization level

1. Go to [**Sharing** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185222), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the Sharing page.
2. Under **More external sharing settings**, select the **Limit external sharing by domain** check box, and then select **Add domains**.
3. To create an allow list (most restrictive), select **Allow only specific domains**; to block only the domains you specify, select **Block specific domains**.
4. List the domains (maximum of 5,000) in the box provided, using the format *domain.com.* If you list more than one domain, enter each domain on a new line.

    Wildcards aren't supported for domain entries.
5. Select **Save**.

You can also configure the organization-wide setting by using the [Set-SPOTenant](/en-us/powershell/module/sharepoint-online/Set-SPOTenant) PowerShell cmdlet.

### Limit domains at the site level

You can also limit domains at the site level. Keep the following considerations in mind:

- In there are conflicts, the organization-wide configuration takes precedence over the site configuration.
- If you set up an organization-wide allow list and you want to set up a site-level allow list, the site-level allow list must be a subset of the organization's allow list.
- If you set up an organization-wide block list, you can set up either an allow list or a block list at the site collection level.
- For individual OneDrive site collections, you can only set up limit domains by using the [Set-SPOSite](/en-us/powershell/module/sharepoint-online/Set-SPOSite) Windows PowerShell cmdlet.

### Limit the domains for a site

1. Go to [**Active sites** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185220), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.
2. Select the site name that you want to restrict domains to open the details panel.
3. On the panel, select the **Settings** tab and select **More sharing settings** under **External sharing**.
4. Under **Advanced settings for external sharing**, select the **Limit external sharing by domain** check box, and then select **Add domains**.
5. Select **Allow only specific domains** to create an allow list (must be a subset of the organization's allow list), or to block only the domains you specify, select **Block specific domains**. You can't use the **Block specific domains** feature if your organization already set up an allow list.
6. List the domains (maximum of 500) in the box provided, using the format *domain.com.* If listing more than one domain, enter each domain on a new line.

    Wildcards aren't supported for domain entries.
7. Select **Save**, and then select **Save** again.

Note

To configure the site collection setting for site collections that don't appear in this list (such as Group-connected sites or individual OneDrive site collections), you must use the [Set-SPOSite](/en-us/powershell/module/sharepoint-online/Set-SPOSite) PowerShell cmdlet.

## Sharing experience

After you limit sharing by domain, here's what you see when you share a document:

- **Sharing content with email domains that aren't allowed.** If you attempt to share content with a guest whose email address domain isn't allowed, an error message displays, and sharing isn't allowed.

    (If the user is already in your directory, you don't see the error, but they're blocked if they attempt to access the site.)

    ![Screenshot of sharing error message when sharing with blocked user.](sharepointonline/media/fb280460-388d-4596-9938-6b69101d11fb.png)
- **Sharing OneDrive files with guests on domains that aren't allowed.** If a user tries to share a OneDrive file with a guest whose email domain isn't allowed, an error message displays, and sharing isn't allowed.

    ![Screenshot of error message when sharing OneDrive files with blocked users.](sharepointonline/media/992f367d-1caa-4019-8fd8-af84c172319c.png)
- **Sharing content with email domains that are allowed.** Users can successfully share the content with the guest. A tooltip appears to let them know that the guest is outside of their organization.

    ![Screenshot of successfully sharing content with restricted users.](sharepointonline/media/4e5ff064-a1d4-4a7d-bc7b-0541312e9383.png)

## User auditing and lifecycle management

As with any extranet sharing scenario, it's important to consider the lifecycle of your guests, how to audit their activity, and eventually how to archive the site. As a site owner or admistrator, you can [create a CSV file](/en-us/sharepoint/sharing-reports) of every unique file, user, permission, and link on a given SharePoint site or OneDrive. As a SharePoint admin or other administrator, with [SharePoint advanced management](/en-us/sharepoint/advanced-management), you can run [Data access governance reports](/en-us/sharepoint/advanced-management#data-access-governance-insights) to audit shared links. See [Planning SharePoint business-to-business (B2B) extranet sites](create-b2b-extranet) for more information.