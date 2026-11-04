---
layout: Conceptual
title: About user profile synchronization - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/user-profile-sync
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: amysim
ms.author: ruihu
author: maggierui
manager: jtremper
ms.date: 2025-01-15T00:00:00.0000000Z
audience: Admin
f1.keywords:
- NOCSH
ms.topic: concept-article
ms.service: sharepoint-online
ms.subservice: admin
ms.collection: M365-collaboration
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.assetid: 
description: This article describes the user profile sync process for SharePoint in Microsoft 365, and the properties that are synced into user profiles.
locale: en-us
document_id: 54ff426d-6bba-75ea-970b-03f16fe191b5
document_version_independent_id: 51db9ad2-9e46-4391-601a-062b640b00d2
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/user-profile-sync.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: user-profile-sync
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/user-profile-sync.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
- https://authoring-docs-microsoft.poolparty.biz/devrel/b1cfdec6-b0c3-4209-818c-736879856e0e
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
- https://authoring-docs-microsoft.poolparty.biz/devrel/2d0723c1-cf38-4c30-ab3d-5df787b33270
platformId: 4133c659-d7e9-7b2b-eff1-e3a7d27a8369
---

# About user profile synchronization - SharePoint in Microsoft 365 | Microsoft Learn

Microsoft SharePoint uses the Active Directory synchronization job to import user and group attribute information into the User Profile Application (UPA). When a new user is added to Microsoft Entra ID, the user account information is sent to the SharePoint directory store and the UPA sync process creates a profile in the User Profile Application based on a predetermined set of attributes. Once the profile has been created, any modifications to these attributes will be synced as part of regularly scheduled sync process.

Note

The profile properties that are synced by the UPA sync process aren't configurable. Synchronization times vary based on workloads.

## Sync process

There are four steps in the sync process.

| Step | Description |
| --- | --- |
| 1. Active Directory to Microsoft Entra ID | [Microsoft Entra Connect](/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis) syncs data from on-premises Active Directory to Microsoft Entra ID. For more info, see [What is hybrid identity with Microsoft Entra ID?](/en-us/azure/active-directory/hybrid/whatis-hybrid-identity) and [Attributes synchronized](/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized#sharepoint-online). |
| 2. Microsoft Entra ID to SharePoint | Microsoft Entra ID syncs data from Microsoft Entra ID to the SharePoint directory store. |
| 3. SharePoint to UPA | The UPA sync process syncs user account information in SharePoint directory store to the User Profile Application (UPA). |
| 4. UPA to sites | User account information from the UPA is synced to SharePoint sites (previously called "site collections"). |

Typically, user profiles are created automatically for all accounts that are created in Microsoft 365. For organizations that have a Microsoft 365 Education subscription, user profiles aren't created for new accounts by default. The user must access SharePoint once, at which time a basic stub profile will be created for the user account. The stub profile will be updated with all remaining data as part of the sync process.

If block sign-in is set on the user account in Microsoft Entra ID or disabled accounts are synced from Active Directory on premises, those user accounts won't be processed as part of the UPA sync process. The user must be enabled and licensed for changes to be processed.

## Properties that are synced into SharePoint user profiles

The following Microsoft Entra user attributes are synced to the UPA.

| Microsoft Entra attribute | User profile property display names | Notes | Sync to sites |
| --- | --- | --- | --- |
| UserPrincipalName | Account Name  User Name  User Principal Name | Example: `i:0#.f <|> membership <|>` gherrera@contoso.com  gherrera@contoso.com | Yes |
| DisplayName | Name |  | Yes |
| GivenName | FirstName |  | Yes |
| sn | LastName |  | Yes |
| telephoneNumber | Work phone | Example: (123) 456-7890 | Yes |
| proxyAddresses | Work Email  SIP Address | Work Email is set to the value prefixed with SMTP. (SMTP:gherrera@contoso.com)  Example: gherrera@contoso.com | Yes |
| PhysicalDeliveryOfficeName | Office |  | Yes |
| Title | Title  Job Title | Job Title contains the same value as Title and is connected to a term set. | Yes |
| Department | Department | Department is connected to a term set. | Yes |
| WWWHomePage | Public site redirect |  | No |
| PreferredLanguage | Language Preferences | Used by SharePoint to determine language for the user when the multilingual user interface (MUI) feature is enabled. | Yes |
| msExchHideFromAddressList | SPS-HideFromAddressLists |  | No |
| Manager | Manager | User Manager for organization hierarchy | Yes |

Note

To update more or custom properties, see [Bulk update custom user profile properties](/en-us/sharepoint/dev/solution-guidance/bulk-user-profile-update-api-for-sharepoint-online). Some property names could differ between Azure AD Graph and Microsoft Graph, see [Property differences between Azure AD Graph and Microsoft Graph](/en-us/graph/migrate-azure-ad-graph-property-differences).

## Frequently asked questions (FAQs)

### How often are changes synced into the User Profile Application?

User account attribute changes are collected in batches and processed for UPA synchronization. Times vary based on the amount of changes requested in a single batch. The UPA synchronization is schedule to run at regular intervals.

### Will UPA synchronization overwrite existing properties in SharePoint user profiles?

For the default properties that are synced by UPA synchronization, values are overwritten to align with Microsoft Entra ID.

### Does UPA synchronization update only properties that have changed?

UPA synchronization is driven primarily by changes that are made Microsoft Entra ID, including adding new users. A full import can occur under certain maintenance events.

### Why isn't it possible to map additional properties for UPA synchronization to sync from Microsoft Entra ID to the User Profile Application?

UPA synchronization is limited to a preconfigured set of properties to guarantee consistent performance across the service.