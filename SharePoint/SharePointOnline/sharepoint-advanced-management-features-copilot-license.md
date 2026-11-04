---
layout: Conceptual
title: SharePoint Advanced Management features in Microsoft Copilot licenses - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/sharepoint-advanced-management-features-copilot-license
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
customer-intent: As an IT admin, I want to understand what SharePoint Advanced Management capabilities are included with Microsoft Copilot licenses.
f1.keywords:
- NOCSH
ms.topic: concept-article
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Highpri
- Tier2
- M365-sam
- M365-collaboration
search.appverid:
- MET150
description: Get the details about SharePoint Advanced Management features that are included with Microsoft Copilot licenses.
locale: en-us
document_id: 26912410-ef1d-3409-ac82-3421da850b21
document_version_independent_id: 718474d3-8790-d3c5-1ba2-d57678fdbf89
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/sharepoint-advanced-management-features-copilot-license.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: sharepoint-advanced-management-features-copilot-license
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/sharepoint-advanced-management-features-copilot-license.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
platformId: f6361738-7a2f-a26b-af71-34faf61c9448
---

# SharePoint Advanced Management features in Microsoft Copilot licenses - SharePoint in Microsoft 365 | Microsoft Learn

If your organization assigns at least one Microsoft Copilot license to a user, SharePoint administrators get access to the [SharePoint Advanced Management](advanced-management) (SAM) features that support your Copilot deployment. This article summarizes those features and availability across business and government cloud environments.

## SAM features in Copilot environments

The following table lists the SharePoint Advanced Management features that are included in Microsoft Copilot licenses for:

- Enterprise and business commercial customers, denoted as *Microsoft Copilot (WW)*
- Government Community Cloud customers, denoted as *Microsoft Copilot (GCC)*
- Government Community Cloud High customers, denoted as *Microsoft Copilot (GCC-H)*
- Department of Defense customers, denoted as *Microsoft Copilot (DoD)*

| Feature | Microsoft Copilot (WW)​ | Microsoft Copilot (GCC)​ | Microsoft Copilot (GCC-H)​ | Microsoft Copilot (DoD)​ |
| --- | --- | --- | --- | --- |
| [Compare SharePoint site policies](/en-us/sharepoint/site-policy-comparison): Easily identify sites with similar content but different security policies. This feature helps you review and adjust site policies and settings, ensuring consistent security across your organization. | Yes | Yes | Yes | Yes |
| **Sprawl control** |  |  |  |  |
| [Site ownership policy (simulation mode​)](/en-us/sharepoint/site-ownership-policy): Define who should be responsible for each site, set minimum owner or admin counts, and automate notifications when sites don't meet your criteria. | Yes | Yes | Yes | Yes |
| [Site ownership policy (active mode)](/en-us/sharepoint/site-ownership-policy) | Yes | Yes | Yes | Yes |
| [Inactive SharePoint sites policy (simulation mode)](/en-us/sharepoint/inactive-site-policy): Detect inactive sites and notify site owners via email. | Yes | Yes | Yes | Yes |
| [Inactive SharePoint sites policy (active mode)](/en-us/sharepoint/inactive-site-policy) | Yes | Yes | Yes | Yes |
| [Site attestation policy (simulation mode)](/en-us/sharepoint/request-site-attestations): Request regular reviews by site owners or admins to check and confirm the accuracy of site information, including the site's necessity, its owners, members, permissions, and sharing settings. | Yes | Yes | Yes | Yes |
| [Site attestation policy (active mode)](/en-us/sharepoint/request-site-attestations) | Yes | Yes | Yes | Yes |
| **Oversharing control** |  |  |  |  |
| [Content management assessment](/en-us/sharepoint/content-management-assessment): The hub for a comprehensive set of tools for assessing and improving your organization's content management practices with actionable insights and recommendations. | Yes | Yes | Yes | Yes |
| [Block download policy](/en-us/sharepoint/block-download-from-sites): Create and manage block download policies to block downloads for: - Files in SharePoint and OneDrive sites - Teams meeting recording files specifically | Yes | Yes | Yes | Yes |
| [Enterprise app insights](/en-us/sharepoint/app-insights): Gain insights on the various non-Microsoft applications registered to your Microsoft Entra admin center and how they access your SharePoint content. | Yes | Yes | Yes | Yes |
| [SharePoint agent insights](/en-us/sharepoint/ai-insights): Find the **Get AI insights** button next to various reports in the SharePoint admin center. Once selected, the AI insights feature extracts patterns from the report and offers a list of potential actions. | Yes | Yes | Yes | Yes |
| [Conditional Access policies](/en-us/sharepoint/authentication-context-example): Use authentication contexts to connect a Microsoft Entra Conditional Access policy to a SharePoint site. | Yes | Yes | Yes | Yes |
| [Restricted access control (RAC)](/en-us/sharepoint/restricted-access-control): Restrict access to: - [SharePoint sites by security groups](/en-us/sharepoint/restricted-access-control)- [OneDrive sites by security groups](/en-us/sharepoint/limit-access)- [Specific OneDrive sites](/en-us/sharepoint/onedrive-site-access-restriction) | Yes | Yes | Yes | Yes |
| [Restricted content discovery (RCD)](/en-us/sharepoint/restricted-content-discovery): Limit the ability of end users to search for files from specific SharePoint sites and prevent the sites from surfacing in Microsoft Copilot Business Chat, unless a user had a recent interaction. | Yes | Yes | Yes | Yes |
| [Sharing links](/en-us/sharepoint/data-access-governance-reports#what-is-the-sharing-links-report) | Yes | Yes | Yes | Yes |
| [Sensitivity labels](/en-us/sharepoint/data-access-governance-reports#what-is-the-sensitivity-labels-for-files-report) (Requires E5 or G5) | Yes | Yes | Yes | Yes |
| [Everyone except external users (EEEU) insights](data-access-governance-everyone-except-external-user-report)​ | Yes | Yes | Yes | Yes |
| [Permission state reports for sites, OneDrive sites, and files](/en-us/sharepoint/data-access-governance-site-permissions-report) | Yes | Yes | Yes | Yes |
| [Site access review for all reports](/en-us/sharepoint/site-access-review): Delegate the process of reviewing data access governance reports to site owners of overshared sites. | Yes | Yes | Yes | Yes |
| **Content lifecycle control** |  |  |  |  |
| [Catalog management](/en-us/sharepoint/catalog-management): Organize and govern SharePoint sites by grouping them into logical categories based on regions, departments, users, information barriers, and custom properties. | Yes | Yes | Yes | Yes |
| [Change history - site settings](/en-us/sharepoint/change-history-report): Create change history reports to track changes made to: - Individual SharePoint sites - Organization settings in the SharePoint admin center | Yes | Yes | Yes | Yes |
| [Recent admin actions](/en-us/sharepoint/recent-actions-panel): Review and monitor the last 30 changes you made to a SharePoint site's properties (such as renaming a site, deleting a site, changing storage quota) within the last 30 days in the SharePoint admin center. | Yes | Yes | Yes | Yes |

Note

[Restricted site creation by apps](/en-us/sharepoint/restricted-site-creation-by-apps) isn't included with your Microsoft Copilot license. This feature requires the [SharePoint Advanced Management Plan 1 add-on](sharepoint-advanced-management-prerequisites#microsoft-copilot-or-the-sharepoint-advanced-management-plan-1-add-on). Restricted site creation enables you to specify the non-Microsoft applications that can create SharePoint sites in your organization.

[Advanced tenant renaming](change-your-sharepoint-domain-name#what-is-advanced-tenant-rename) is not available in GCC, GCC-High, or DoD tenants.

Advanced tenant renaming is available in enterprise and business tenants. If there are more than 10,000 sites in these environments, SharePoint Advanced Management is required.