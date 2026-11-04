---
layout: Conceptual
title: Secure Store Service (SSS) retirement in Microsoft 365 - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/secure-store-service-retirement-in-microsoft-365
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-04-08T00:00:00.0000000Z
ms.reviewer: troys
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: article
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.custom: admindeeplinkSPO
ms.collection:
- Tier3
search.appverid:
- SPO160
- MET150
description: Microsoft is announcing its plan to retire Secure Store Service (SSS) in Microsoft 365 and focus on Azure Key Vault as its replacement technology.
locale: en-us
document_id: 16411647-fdfe-d78a-d76a-3a159819af65
document_version_independent_id: e138e8cb-3c2f-dd21-2adf-7aeea1fbae0a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/secure-store-service-retirement-in-microsoft-365.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: secure-store-service-retirement-in-microsoft-365
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/secure-store-service-retirement-in-microsoft-365.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/dc29fde7-b949-4135-9273-ad8e4a53d516
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/25d6050c-71f5-4b48-8bc7-575debd6530a
platformId: 342f6c32-007d-db55-5f1d-dbf07c46e3af
---

# Secure Store Service (SSS) retirement in Microsoft 365 - SharePoint in Microsoft 365 | Microsoft Learn

SharePoint has a long history of helping users securely work with external data inside the SharePoint user experience, starting with the Business Data Catalog feature in SharePoint Server 2007. SharePoint has been evolving into a cloud-first service and along with it the options for managing credentials and secrets for external data access have also evolved. To simplify these options and provide the best experience for these scenarios going forward, Microsoft is announcing its plan to retire Secure Store Service (SSS) in Microsoft 365 and focus on Azure Key Vault as its replacement technology.

This announcement follows the discontinuation of [Business Connectivity Services](/en-us/sharepoint/business-connectivity-services-retirement) (BCS), which was the primary use case for Secure Store Service.

## Impact on SharePoint Server

This announcement has no immediate impact on Secure Store Service in SharePoint Server 2016, 2019, and Subscription Edition.

Until SharePoint Server 2016 and SharePoint Server 2019 reach their end of support date of July 14, 2026, SSS will be supported. For SharePoint Server Subscription Edition, there are no current and immediate plans to retire SSS. For any deprecation or feature support removal announcements, see [What's deprecated or removed from SharePoint Server Subscription Edition](/en-us/sharepoint/what-s-new/what-s-deprecated-or-removed-from-sharepoint-server-subscription-edition)

## Impacted features and scenarios

All Secure Store Service features will be retired in SharePoint in Microsoft 365. This includes features such as:

- Secure Store Target Applications
- Credential storage
- Mapping for external data sources

## Retirement schedule

| Date | Milestone |
| --- | --- |
| **April 10, 2025** | Retirement is announced and transition period begins. |
| **May 31, 2025** | Adding new Target Applications or credentials in Secure Store Service is restricted. |
| **September 30, 2025** | Secure Store Service is fully retired in Microsoft 365. |

## Automatic retirement

Microsoft will manage the retirement process automatically. Administrators don't need to take any manual steps to disable Secure Store Service. Once retired, the service will no longer be available, and any existing configurations will be removed.

## Recommended replacement technology: Azure Key Vault

We encourage you to explore using Azure Key Vault to replace Secure Store Service solutions in SharePoint in Microsoft 365. Although there's no direct migration from Secure Store Service to Azure Key Vault, it supports a modern, cloud-first credential and secret management experience. Azure Key Vault can integrate with various Microsoft 365 services and external data sources through its secure and scalable architecture.

To learn more about Azure Key Vault, see the links in the More information section.

## More Information about Azure Key Vault

For more information about Azure Key Vault and its capabilities, see:

- [Azure Key Vault (AKV) Documentation](/en-us/azure/key-vault/keys/)