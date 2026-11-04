---
layout: Conceptual
title: Manage access to Microsoft Entra ID-secured APIs - SharePoint - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/api-access
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2024-09-25T00:00:00.0000000Z
ms.reviewer: lucaband
ms.author: deniseb
author: denisebmsft
manager: dansimp
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
- M365-sam
search.appverid:
- SPO160
- BSA160
- MET150
ms.assetid: 0b6ab336-8b83-423f-a06b-bcc52861cba0
ms.custom: admindeeplinkSPO
description: Learn how to manage permission requests to Microsoft Entra ID-secured APIs from SharePoint Framework components and scripts.
locale: en-us
document_id: b28adf02-7572-f60e-7b06-bb83c558166c
document_version_independent_id: 08d0f581-9739-12b6-fa27-1fcf2d74ebdf
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/api-access.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: api-access
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/api-access.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/6b286e9d-72ab-4d74-be7d-8c3e084f9187
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/75913493-3233-4b36-adc7-7cc633de096a
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
platformId: accf0732-b6db-ae08-9967-2929f9ec5144
---

# Manage access to Microsoft Entra ID-secured APIs - SharePoint - SharePoint in Microsoft 365 | Microsoft Learn

When developers build SharePoint Framework solutions, they might need to connect to an API that's secured through Microsoft Entra ID. Developers can specify which Microsoft Entra applications and permissions their solution requires, and an administrator can manage the permission request from [**API access** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185223).

[Learn more about building SharePoint Framework solutions that connect to Azure-AD secured APIs](/en-us/sharepoint/dev/spfx/use-aadhttpclient#manage-permission-requests).

![The API access page in the modern SharePoint admin center](sharepointonline/media/api-access-page.png)

The API access page shows pending and approved requests. It also shows which requests apply to any SharePoint Framework component or custom script in your organization (organization-wide) and which requests apply to only the specific component (isolated).

Note

The admin role that's required to approve permissions depends on the API. To approve permissions to any of the third-party APIs registered in the tenant, the [application administrator](/en-us/azure/active-directory/roles/permissions-reference#application-administrator) role is sufficient. To approve permissions for Microsoft Graph or any other Microsoft API, the Global Administrator role is required. The API access page is not available for people signed in with the global reader role.

## Approve a pending request

1. Select the request, and then select **Approve** to see details about the request.
2. In the **Approve access** panel, select **Approve**.

    ![The Approve access panel](sharepointonline/media/approve-access.png)

    After you approve a request, it moves to the Approved requests list.

    Note

    Permissions of type delegated are added to the *SharePoint Online Client Extensibility Web Application Principal* in Microsoft Entra ID.

    If you try to approve a permission request for a resource that already has some permissions granted (for example, granting additional permissions to the Microsoft Graph), the requested scopes are added to the previously granted permissions.

## Reject a pending request

1. Select the request, and select **Reject**.
2. Select **Reject** again to confirm.

    Rejecting access doesn't remove the app from the Apps site. If the app is used on any sites, it might not work as expected. After you reject the request, it's removed from the page and the developer will need to issue a new request with the same resource and scope.

## Remove access to a previously approved request

1. Select the request, and then select **Remove access**.
2. Select **Remove** again to confirm.

    When you remove access, solutions and custom scripts that rely on the permission might not work as expected. After you remove access, the request is removed from the page and the developer will need to issue a new request with the same resource and scope.

## Manage access by using Microsoft PowerShell

You can also use PowerShell to manage permission requests.

- To view pending requests, use the cmdlet [Get-SPOTenantServicePrincipalPermissionRequests](/en-us/powershell/module/sharepoint-online/get-spotenantserviceprincipalpermissionrequests?view=sharepoint-ps&amp;preserve-view=true).
- To approve a request, use the cmdlet [Approve-SPOTenantServicePrincipalPermissionRequest](/en-us/powershell/module/sharepoint-online/Approve-SPOTenantServicePrincipalPermissionRequest?view=sharepoint-ps&amp;preserve-view=true).
- To reject a request, use the cmdlet [Deny-SPOTenantServicePrincipalPermissionRequest](/en-us/powershell/module/sharepoint-online/deny-spotenantserviceprincipalpermissionrequest?view=sharepoint-ps&amp;preserve-view=true).
- To remove access to a previously approved request, use the cmdlet [Revoke-SPOTenantServicePrincipalPermission](/en-us/powershell/module/sharepoint-online/revoke-spotenantserviceprincipalpermission?view=sharepoint-ps&amp;preserve-view=true).