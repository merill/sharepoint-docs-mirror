---
layout: Conceptual
title: Enable conditional access support in the OneDrive sync app - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/enable-conditional-access
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-01-26T00:00:00.0000000Z
ms.reviewer: william.sproule
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: onedrive
ms.localizationpriority: medium
search.appverid:
- ODB160
- ODB150
- MET150
ms.collection:
- Strat_OD_admin
- M365-collaboration
- essentials-compliance
- essentials-security
- M365-sam
ms.custom:
- seo-marvel-apr2020
- onedrive-toc
ms.assetid: 028d73d7-4b86-4ee0-8fb7-9a209434b04e
description: In this article, you'll learn how to enable conditional access in the new OneDrive sync app.
locale: en-us
document_id: 21c6bfdb-03aa-803d-a96b-9c9fd9a45572
document_version_independent_id: 18425f39-d2af-21a2-2868-d218673a736e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/enable-conditional-access.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: enable-conditional-access
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/enable-conditional-access.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
platformId: 4bc927c0-63cf-f79f-ab8d-80554b1948fe
---

# Enable conditional access support in the OneDrive sync app - SharePoint in Microsoft 365 | Microsoft Learn

Conditional access control capabilities in Microsoft Entra ID offer simple ways for you to secure resources in the cloud. The new OneDrive sync app works with the conditional access control policies to ensure syncing is only done with compliant devices. For example, you might require sync to be available only on domain-joined devices or devices that meet compliance as defined by the Mobile Device Management system (like Intune).

For information about how conditional access works, see:

- [Microsoft Entra Conditional Access](/en-us/azure/active-directory/conditional-access/)
- [Require managed devices for cloud app access with conditional access](/en-us/azure/active-directory/conditional-access/require-managed-devices)
- [Configure Microsoft Entra hybrid join for managed domains](/en-us/azure/active-directory/devices/hybrid-azuread-join-managed-domains)
- [Control access from unmanaged devices](/en-us/sharepoint/control-access-from-unmanaged-devices#block-or-limit-access-to-a-specific-sharepoint-site-or-onedrive)

## Recommendations for Windows

We recommend using this feature on Windows together with [silent account configuration](use-silent-account-configuration) for the best experience. The OneDrive sync app supports both device-based and location-based conditional access policies.

## Known issues

The following are known issues with this release:

- If you create a new access policy after the device has authenticated, it may take up to 24 hours for the policy to take effect.
- In some cases, the user may be prompted for credentials twice. We're working on a fix for this issue.
- Certain AD FS configurations may require additional setup to work with this release. Run the following command on your AD FS server to ensure FormsAuthentication is added to the list of PrimaryIntranetAuthenticationProvider:

    `Set-AdfsGlobalAuthenticationPolicy -PrimaryIntranetAuthenticationProvider @('WindowsAuthentication', 'FormsAuthentication')`
- If you enable location-based conditional access, users get a prompt about every 90 to 120 minutes by default when they leave the set of approved IP address ranges. The exact timing depends on the access token expiry duration (60 minutes by default), when their computer last obtained a new access token, and any specific conditional access timeouts put in place.