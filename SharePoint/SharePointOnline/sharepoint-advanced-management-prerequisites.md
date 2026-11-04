---
layout: Conceptual
title: Prerequisites for SharePoint Advanced Management - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/sharepoint-advanced-management-prerequisites
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: false
ms.date: 2026-06-30T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.reviewer: daminasy
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
customer-intent: As an IT admin, I want to understand how prerequisites for SharePoint Advanced Management.
f1.keywords:
- NOCSH
ms.topic: concept-article
ms.service: sharepoint-online
ms.localizationpriority: medium
ms.collection:
- Highpri
- Tier2
- M365-sam
- M365-collaboration
search.appverid:
- MET150
description: Understand the prerequisites for SharePoint Advanced Management, including licensing and PowerShell requirements.
locale: en-us
document_id: 8bd493c8-731e-272f-7f6b-4678978a7d47
document_version_independent_id: da549774-0c71-e4fa-aa79-52138cfa5a99
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/sharepoint-advanced-management-prerequisites.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: sharepoint-advanced-management-prerequisites
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/sharepoint-advanced-management-prerequisites.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 0162f877-e36b-28c3-560c-e13183950845
---

# Prerequisites for SharePoint Advanced Management - SharePoint in Microsoft 365 | Microsoft Learn

To use SharePoint Advanced Management capabilities, make sure your organization meets specific licensing, role, and setup requirements. SharePoint Advanced Management helps your organization strengthen how you observe content and permissions, govern access and lifecycle policies, and secure your environment against risks like oversharing, especially in environments using Microsoft Copilot.

For a full list of features, see [SharePoint Advanced Management service description](/en-us/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description#sharepoint-advanced-management).

This article outlines the foundational requirements, including supported base subscriptions, add-on licensing, required administrative roles, and PowerShell setup. These prerequisites ensure that your team has the appropriate access, tools, and permissions needed to manage governance features effectively and support these scenarios.

## Microsoft 365 base subscription

Your organization must have one of the following base licenses:

- Office 365 E3, E5, or A5
- Microsoft 365 E1, E3, E5, or A5
- Microsoft 365 GCC, GCC-High, or DoD

## Microsoft Copilot or the SharePoint Advanced Management Plan 1 add-on

You get SharePoint Advanced Management capabilities to support your Microsoft Copilot deployment when at least one of the following conditions is met:

- **At least one user in your organization is assigned a Microsoft Copilot license**. (The user doesn't need to be a SharePoint administrator.)

    --- or ---
- **Your subscription includes SharePoint K, P1, or P2, and your organization purchases the *SharePoint Advanced Management Plan 1* add-on**. (This add-on is sometimes referred to as *SharePoint Advanced Management standalone*.)

    --- or ---
- **Your organization has Microsoft 365 E7**, also known as The Frontier Suite. It includes:

    - Microsoft 365 E5
    - Microsoft Copilot
    - Microsoft Entra Suite
    - Microsoft Agent 365

If your organization has at least one Microsoft Copilot license assigned to a user, your SharePoint administrators automatically receive access to [SharePoint Advanced Management capabilities to support your Copilot deployment](sharepoint-advanced-management-features-copilot-license).

**Some features, such as [restricted site creation](/en-us/sharepoint/restricted-site-creation-by-apps), require the SharePoint Advanced Management Plan 1 add-on**. You can purchase this add-on through:

- The Microsoft 365 admin center
- A Cloud Solution Provider (CSP)
- Volume licensing enrollment

External users don't require a license.

For more information about Microsoft licensing, see [Understand, choose, and manage your Microsoft licenses](https://www.microsoft.com/en-us/Licensing/).

## Role-based access control (RBAC) role assignments

To access the SharePoint admin center and use SharePoint Advanced Management capabilities, you must have an appropriate role assigned in Microsoft Entra ID. Assign these roles in either the Microsoft Entra admin center or the Microsoft 365 admin center.

- **[SharePoint Administrator](/en-us/entra/identity/role-based-access-control/permissions-reference#sharepoint-administrator)**: Provides full administrative control over the SharePoint Online service, including sites, policies, groups, and operational tasks, such as service health and support.
- **[SharePoint Advanced Management Administrator](/en-us/entra/identity/role-based-access-control/permissions-reference#sharepoint-advanced-management-administrator)**: Includes all SharePoint Administrator capabilities, plus advanced governance capabilities such as:

    - Viewing metadata (names, paths, URLs) across SharePoint content
    - Removing permissions from content at scale
    - Managing SharePoint Advanced Management features

## SharePoint Online PowerShell module

The SharePoint Online Management Shell is a Windows PowerShell module that you can use to manage SharePoint settings at the organization and site level. To use SharePoint Online PowerShell commands, you need to install the SharePoint Online Management Shell module and connect it to the SharePoint Online service.

1. Always [download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251) before running any of the commands.
2. In your PowerShell console, connect to SharePoint. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

Note

If you installed a previous version of the SharePoint Online Management Shell, see [SharePoint Online PowerShell command doesn't work correctly](/en-us/troubleshoot/sharepoint/administration/sharepoint-online-powershell-command-does-not-work-correctly) for instructions on removing older versions.