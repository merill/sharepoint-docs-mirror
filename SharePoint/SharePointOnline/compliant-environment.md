---
layout: Conceptual
title: Plan compliance requirements for SharePoint and OneDrive - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/compliant-environment
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-08-19T00:00:00.0000000Z
ms.reviewer: 
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
f1.keywords: NOCSH
ms.topic: concept-article
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection: essentials-compliance
ms.custom: intro-get-started
search.appverid: MET150
description: Learn what features are available in Microsoft 365 to help you plan your compliance requirements for SharePoint and OneDrive.
locale: en-us
document_id: 56a4c0bb-2d92-f01e-af15-39b40da512a3
document_version_independent_id: 82c1de24-7f29-3665-aec3-25c87d3f0821
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/compliant-environment.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: compliant-environment
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/compliant-environment.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: e3c72eb3-b9a4-148d-531d-1ae4caec72a7
---

# Plan compliance requirements for SharePoint and OneDrive - SharePoint in Microsoft 365 | Microsoft Learn

Most organizations have business or legal requirements that govern how data is used, shared, and retained. Some organizations also have data residency requirements or regulatory requirements that restrict communication between certain users and groups.

Microsoft 365 has a wide range of governance and compliance features to address these needs. This article provides an overview of features you may want to consider as part of your OneDrive and SharePoint rollout.

## Data lifecycle management

Use data lifecycle management capabilities in Microsoft Purview to govern your OneDrive and SharePoint content for compliance or regulatory requirements. The following table describes the capabilities to help you keep the content you need you and delete what you don't need.

| Capability | What problems does it solve? | Get started |
| --- | --- | --- |
| [Retention policies and retention labels](/en-us/purview/retention)[Learn about retention for SharePoint and OneDrive](/en-us/purview/retention-policies-sharepoint) | Retain or delete content with policy management for SharePoint and OneDrive documents | [Create and configure retention policies](/en-us/purview/create-retention-policies)[Create retention labels for exceptions to your retention policies](/en-us/purview/create-retention-labels-data-lifecycle-management) |

### Deleted users' data

When a user leaves your organization and you've deleted that user's account, what happens to the user's data? When considering data retention compliance, determine what needs to happen with the deleted user's data. For some organizations, retaining deleted user data could be important continuity and preventing critical data loss.

If a user's Microsoft 365 account is deleted, their OneDrive files are preserved for 30 days. To change this setting, [Set the OneDrive retention for deleted users](/en-us/onedrive/set-retention).

By default, when a user is deleted, the user's manager is automatically given access to the user's OneDrive. To change this, see [OneDrive retention and deletion](/en-us/onedrive/retention-and-deletion).

## Information protection

Microsoft Purview Information Protection capabilities help you discover, classify, and protect sensitive information in OneDrive and SharePoint. The following table describes these capabilities. Consider if you want to implement any of these capabilities as part of your OneDrive and SharePoint rollout.

| Capability | What problems does it solve? | Get started |
| --- | --- | --- |
| [Sensitive information types](/en-us/purview/sit-sensitive-information-type-learn-about) | Identifies sensitive data by using built-in or custom regular expressions or a function. Corroborative evidence includes keywords, confidence levels, and proximity. | [Customize a built-in sensitive information type](/en-us/purview/sit-customize-a-built-in-sensitive-information-type) |
| Trainable classifiers | Identifies sensitive data by using examples of the data you're interested in rather than identifying elements in the item (pattern matching). You can use built-in classifiers or train a classifier with your own content. | [Get started with trainable classifiers](/en-us/purview/trainable-classifiers-learn-about) |
| [Sensitivity labels](/en-us/purview/sensitivity-labels) | A single solution across apps, services, and devices to label and protect your data as it travels inside and outside your organization.  Sensitivity labels can be used to protect files themselves or individual SharePoint sites and teams. | [Enable sensitivity labels for Office files in SharePoint and OneDrive](/en-us/purview/sensitivity-labels-sharepoint-onedrive-files)[Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 Groups, and SharePoint sites](/en-us/purview/sensitivity-labels-teams-groups-sites) |
| [Data loss prevention](/en-us/purview/dlp-learn-about-dlp) | Helps prevent unintentional sharing of sensitive items. | [Get started with the default DLP policy](/en-us/purview/get-started-with-the-default-dlp-policy) |

## File sync

The OneDrive sync app has policies that you can use to help you maintain a compliant environment. Consider configuring these policies before you roll out SharePoint and OneDrive.

| Policy | Windows GPO | Mac |
| --- | --- | --- |
| Allow syncing OneDrive accounts for only specific organizations | [AllowTenantList](/en-us/onedrive/use-group-policy#allow-syncing-onedrive-accounts-for-only-specific-organizations) | [AllowTenantList](/en-us/onedrive/deploy-and-configure-on-macos#allowtenantlist) |
| Block syncing OneDrive accounts for specific organizations | [BlockTenantList](/en-us/onedrive/use-group-policy#block-syncing-onedrive-accounts-for-specific-organizations) | [BlockTenantList](/en-us/onedrive/deploy-and-configure-on-macos#blocktenantlist) |
| Prevent users from syncing libraries and folders shared from other organizations | [BlockExternalSync](/en-us/onedrive/use-group-policy#prevent-users-from-syncing-libraries-and-folders-shared-from-other-organizations) | [BlockExternalSync](/en-us/onedrive/deploy-and-configure-on-macos#blockexternalsync) |
| Prevent users from syncing personal OneDrive accounts | [DisablePersonalSync](/en-us/onedrive/use-group-policy#prevent-users-from-syncing-personal-onedrive-accounts) | [DisablePersonalSync](/en-us/onedrive/deploy-and-configure-on-macos#disablepersonalsync) |
| Exclude specific kinds of files from being uploaded | [EnableODIgnoreListFromGPO](/en-us/onedrive/use-group-policy#exclude-specific-kinds-of-files-from-being-uploaded) | [EnableODIgnore](/en-us/onedrive/deploy-and-configure-on-macos#enableodignore) |
| Exclude specific kinds of folders from being uploaded | [EnableODIgnoreFolderListFromGPO](/en-us/onedrive/use-group-policy#exclude-specific-kinds-of-folders-from-being-uploaded) | [EnableODIgnoreFolders](/en-us/onedrive/deploy-and-configure-on-macos#enableodignorefolders) |

## Data residency

Multi-Geo is Microsoft 365 feature that allows organizations to span their storage over multiple geo locations and specify where to store users' data. For multinational customers with data residency requirements, you can use this feature to ensure that each user's data is stored in the geo location necessary for compliance. For more info about this feature, see [Multi-Geo Capabilities in OneDrive and SharePoint](/en-us/office365/enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-office-365/).

Features such as file sync and mobile device management work normally in a multi-geo environment. There's no special configuration or management needed. The multi-geo experience for your users has minimal difference from a single-geo configuration. For details, see [User experience in a multi-geo environment](/en-us/office365/enterprise/multi-geo-user-experience/).

For more information about Microsoft 365 Multi-Geo, see [Microsoft 365 Multi-Geo](/en-us/microsoft-365/enterprise/microsoft-365-multi-geo).

## Information barriers

Microsoft Purview Information Barriers is a compliance solution that allows you to restrict two-way communication and collaboration between groups and users in Microsoft Teams, SharePoint, and OneDrive. Often used in highly regulated industries, information barriers can help to avoid conflicts of interest and safeguard internal information between users and organizational areas.

When information barrier policies are in place, users who shouldn't communicate or share files with other specific users won't be able to find, select, chat, or call those users. Information barrier policies automatically put checks in place to detect and prevent unauthorized communication and collaboration among defined groups and users.

If your business requires information barriers, see [Learn about information barriers](/en-us/purview/information-barriers) and [Use information barriers with SharePoint](/en-us/sharepoint/information-barriers) to get started.