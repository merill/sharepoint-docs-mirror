---
layout: Conceptual
title: Microsoft Entra B2B integration for SharePoint & OneDrive - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/sharepoint-azureb2b-integration
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-09-18T00:00:00.0000000Z
ms.reviewer: srice
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
f1.keywords:
- CSH
ms.topic: integration
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-collaboration
ms.custom:
- Adm_O365
- seo-marvel-apr2020
description: In this article, you learn about the SharePoint and OneDrive integration with Microsoft Entra B2B.
ai-usage: ai-assisted
locale: en-us
document_id: 71747405-a38b-c475-7915-bb10242b689f
document_version_independent_id: ccf67a68-63d7-9d04-69c7-728fabb3be24
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/sharepoint-azureb2b-integration.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: sharepoint-azureb2b-integration
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/sharepoint-azureb2b-integration.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
platformId: 41c775cb-3a6f-3017-7539-b3873c96f4c7
---

# Microsoft Entra B2B integration for SharePoint & OneDrive - SharePoint in Microsoft 365 | Microsoft Learn

Important

Between May and July 2026, Microsoft enabled SharePoint and OneDrive integration with Microsoft Entra B2B for new external sharing in commercial tenants. The `EnableAzureADB2BIntegration` setting no longer controls sharing behavior for these tenants, and the integration can't be disabled.

Starting in October 2026, Microsoft will retire SharePoint Online one-time passcode (OTP) authentication for commercial tenants. Microsoft Entra B2B email one-time passcode authentication remains supported.

When SharePoint OTP retirement reaches your tenant, external users need a matching Microsoft Entra B2B guest account in your directory to access previously shared **Specific people** links. Users with a matching guest account retain access. If a guest account is missing, an administrator can create one, or a user with sharing permissions can share or reshare at least one file, folder, or site to create it and restore access to previously shared content.

For more information, see [FAQ on improvements to external sharing in OneDrive and SharePoint](faqs-odspintegrationwithentrab2b).

This article describes how to enable Microsoft SharePoint and Microsoft OneDrive integration with [Microsoft Entra B2B](/en-us/entra/external-id/what-is-b2b).

Microsoft Entra B2B provides authentication and management of guests. When enabled, [email one-time passcode](/en-us/entra/external-id/one-time-passcode) is a fallback for guests who can't sign in through another supported authentication method.

When you integrate SharePoint and OneDrive with Microsoft Entra B2B Invitation Manager, you can share files, folders, list items, document libraries, and sites with external people. This feature provides an upgraded experience from the existing secure external sharing recipient experience. Additionally, Microsoft Entra B2B Invitation Manager offers a one-time passcode feature. This feature allows users without work, school, or Microsoft accounts to authenticate by using a code, instead of creating a new account.

Enabling this integration doesn't change your sharing settings. For example, if you have site collections where external sharing is turned off, it remains off.

SharePoint and OneDrive integration with the Microsoft Entra B2B one-time passcode feature is enabled by default for new tenants.

Advantages of Microsoft Entra B2B include:

- Invited people outside your organization each get an account in the directory and are subject to Microsoft Entra ID access policies such as multifactor authentication.
- Invitations to a SharePoint site use Microsoft Entra B2B and no longer require users to have or create a Microsoft account.
- If you have Google federation in Microsoft Entra ID, federated users can now access SharePoint and OneDrive resources that you shared with them.
- SharePoint and OneDrive sharing is subject to the Microsoft Entra organizational relationships settings, such as **Members can invite** and **Guests can invite**. As with Microsoft 365 Groups and Teams, if a Microsoft Entra organizational relationship setting is more restrictive than a SharePoint or OneDrive setting, the Microsoft Entra setting prevails.

Note

Microsoft Entra B2B doesn't support Microsoft accounts in Microsoft 365 operated by 21Vianet.

## Enabling the integration

For commercial tenants, Microsoft Entra B2B integration is already enabled for new external sharing. You don't need to run the command below. The following procedure applies only to tenants where the `EnableAzureADB2BIntegration` setting still controls the integration.

Note

When you enable the integration, people outside the organization are invited through the Azure B2B platform when sharing from SharePoint. They sign in based on the [Microsoft Entra B2B redemption policy](/en-us/azure/active-directory/external-identities/redemption-experience#invitation-redemption-flow). When you don't enable the integration, people outside the organization continue to use their existing accounts created when previously invited to the tenant. Any sharing to new people outside the organization may result in either Microsoft Entra ID-backed accounts or SharePoint-only email auth guests that use a SharePoint One Time Passcode experience to sign in.

To enable SharePoint and OneDrive integration with Microsoft Entra B2B

1. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).
2. Connect to SharePoint with permissions of a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [more](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
3. Run the following cmdlets:

    ```PowerShell
    Set-SPOTenant -EnableAzureADB2BIntegration $true
    ```

Note

Review any custom [domain sharing restrictions in SharePoint and OneDrive](/en-us/sharepoint/restricted-domains-sharing) and decide if they should be moved to the [Microsoft Entra B2B Allow/Deny list](/en-us/azure/active-directory/external-identities/allow-deny-list). The Microsoft Entra ID Allow/Deny list also affects other Microsoft 365 services like Teams and Microsoft 365 Groups.

## Disabling the integration

Microsoft Entra B2B integration can't be disabled in commercial tenants. The following procedure applies only to tenants where the `EnableAzureADB2BIntegration` setting still controls the integration.

You can disable the integration by running [`Set-SPOTenant`](/en-us/powershell/module/sharepoint-online/Set-SPOTenant)`-EnableAzureADB2BIntegration $false`.

Important

When you disable the integration, previously shared users remain Microsoft Entra Guest Users for future shares. To convert a user from a Microsoft Entra Guest User back to a SharePoint OTP user, you need to [delete the guest](/en-us/sharepoint/remove-users#delete-a-guest-from-the-microsoft-365-admin-center) in Microsoft Entra ID and remove all SPUser objects in your organization that reference that guest user.

## Frequently asked questions

The following questions address SharePoint OTP retirement and access to content shared with external users.

**1. How can I check if my tenant has enabled SharePoint and OneDrive integration with Entra B2B?**

**Answer:** In commercial tenants, integration is already enabled for new external sharing, regardless of the `EnableAzureADB2BIntegration` value. For tenants where the setting still controls the integration, run `Get-SPOTenant` in the SharePoint Online Management Shell and check the `EnableAzureADB2BIntegration` property. A value of `True` means the integration is enabled; `False` means it isn't enabled.

**2. Which tenants are affected by the October 2026 SharePoint OTP retirement?**

**Answer:** The October 2026 retirement applies to commercial tenants. It affects external users who access previously shared **Specific people** links through SharePoint OTP and don't have a matching Microsoft Entra B2B guest account in your directory.

**3. What happens to previously shared links when SharePoint OTP is retired?**

**Answer:** External users with a matching Microsoft Entra B2B guest account retain access to previously shared links. Once retirement reaches your commercial tenant during October 2026, users without a matching guest account receive access denied on previously shared **Specific people** links. To restore access, create a guest account matching the email address used for the original sharing link, or share or reshare at least one file, folder, or site with that user. You don't need to reshare each item individually.

**4. Is there a way to report which previously shared links and external users are affected?**

**Answer:** Yes. You can use audit logs to assess the impact. For more information, see [Use sharing auditing in the audit log](/en-us/purview/audit-log-sharing?tabs=microsoft-purview-portal). Additionally, site sharing reports available through Microsoft Graph Data Connect can help identify affected content and users. Details are provided in the [Microsoft Graph Data Connect for SharePoint Blog](https://techcommunity.microsoft.com/blog/microsoft_graph_data_connect_for_sharepo/mgdc-for-sharepoint-faq-what-is-in-the-permissions-dataset/4075447). You can also report on file and folder sharing in a SharePoint site using [this sharing report](/en-us/sharepoint/sharing-reports?WT.mc_id=M365-MVP-9501).

**5. Can I proactively invite existing users to join via Entra B2B before this change takes effect?**

**Answer:** Yes. You can create a Microsoft Entra B2B guest account in advance using the email address associated with the original sharing link. A matching guest account lets the user retain access to previously shared content without resharing. For more information, see [Add and manage B2B collaboration users](/en-us/entra/external-id/add-users-administrator).

**6. Can exceptions be made to this change?**

**Answer:** No. This update is part of Microsoft's ongoing efforts to enhance security.

**7. Can this change be applied at the site level?**

**Answer:** No. The change applies at the tenant level and can't be scoped to individual sites.