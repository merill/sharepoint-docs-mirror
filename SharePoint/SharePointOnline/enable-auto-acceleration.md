---
layout: Conceptual
title: Enable auto-acceleration in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/enable-auto-acceleration
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2018-07-11T00:00:00.0000000Z
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.collection: M365-collaboration
ms.localizationpriority: medium
search.appverid:
- SPO160
- BSA160
- MET150
ms.assetid: 74985ebf-39e1-4c59-a74a-dcdfd678ef83
description: Enable auto-acceleration to send users directly to your identity provider to sign in.
locale: en-us
document_id: 21bd120e-26c1-3a5a-499b-8dbd01a435e6
document_version_independent_id: 2ced3050-f8ce-a5c3-a292-e0d668e4a47a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/enable-auto-acceleration.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: enable-auto-acceleration
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/enable-auto-acceleration.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 5d93e83a-ef9f-1086-2566-13cfa7cfb2d4
---

# Enable auto-acceleration in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn

Auto-acceleration is a feature in SharePoint that lets you specify the default identity provider endpoint for your organization. When a user accesses a resource, instead of signing in to login.microsoftonline.com, the user is sent directly to the identity provider (IdP). When you set up Integrated Windows Authentication on Active Directory Federation Services (AD FS) and the user's computer belongs to the domain, the user can sign in without entering credentials, as if they were accessing a resource within the network.

## Requirements

To enable auto-acceleration, you must have a single identity provider (IdP). SharePoint must have a specific site to target when accelerating. Your organization can have multiple domains as long as there's a single IdP endpoint.

## Enable auto-acceleration

To enable auto-acceleration, you need to use Microsoft PowerShell.

1. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    Note

    If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell."
2. Connect to SharePoint as a [Global Administrator or SharePoint Administrator](sharepoint-admin-role) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
3. Run the following command to enable auto-acceleration on sites that aren't shared externally:

    ```PowerShell
    Set-SPOTenant -SignInAccelerationDomain "contoso.com"
    ```
4. If you configured your IdP to support guests, you can enable auto-acceleration on sites that have external sharing enabled by running:

    ```PowerShell
    Set-SPOTenant -EnableGuestSignInAcceleration $true
    ```

    Note

    You must run SignInAccelerationDomain before running this command.

    For more information, see [Set-SPOTenant](/en-us/powershell/module/sharepoint-online/Set-SPOTenant).

## Frequently asked questions about auto-acceleration

### What can I do to make the experience as smooth as possible for my users?

A: You can do two things. First, make sure your internal and external sites are clearly separated. Second, encourage users to access internal sites first as part of their daily workflow. Perhaps consider creating an internal-only site that serves as a welcome page. You can also modify your Group Policy so that users are directed to an internal home page whenever they open their browser. After the user signs in to one site (by using either method), they won't be prompted to sign to other sites.

### What do I need to do to take advantage of auto acceleration on externally shared sites?

A: Guests can potentially authenticate in one of three places:

- Microsoft Entra ID (if their organization is a "cloud" organization or they use a Microsoft account)
- The IdP of the user's organization
- Your IdP (if you use an on-premises extranet solution)

If you want to enable auto-acceleration for externally shared sites, your IdP needs to be able to support these use cases (or at least the ones that you want your guests to use). To support guests in Microsoft Entra ID, Microsoft account, or other IdPs, your IdP needs to be able to return the user to the Microsoft Entra sign-in screen for authentication.