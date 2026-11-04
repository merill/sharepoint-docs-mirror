---
layout: Conceptual
title: Use Microsoft Purview risk and compliance solutions instead of the older information management and records management features in SharePoint for Microsoft 365 - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/use-microsoft-purview-risk-and-compliance-solutions
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
f1.keywords:
- NOCSH
ms.author: kyrachurney
author: kyracatwork
manager: roygles
ms.date: 2023-10-25T00:00:00.0000000Z
audience: Admin
ms.topic: overview
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
search.appverid:
- WSU150
- SPO160
- OSU150
- MET150
ms.assetid: 63a0b501-ba59-44b7-a35c-999f3be057b2
ms.collection:
- purview-compliance
- Tier3
- M365-sam
ms.custom:
- seo-marvel-apr2020
description: Learn how to use Microsoft Purview risk and compliance solutions instead of the older information management and records management features in SharePoint for Microsoft 365.
locale: en-us
document_id: c343a416-7e4b-6a12-77a8-b31fdf94e4c1
document_version_independent_id: e4f9bc4e-ae9a-7948-d973-06605340ba8f
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/use-microsoft-purview-risk-and-compliance-solutions.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: use-microsoft-purview-risk-and-compliance-solutions
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/use-microsoft-purview-risk-and-compliance-solutions.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/e2560d35-6f40-44b4-a8f1-a6691f82061d
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/2e5e1bdc-5c79-4dc1-9c05-485e6e6ae0ce
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: fe440baf-2417-eb94-f5c5-fa9d56f1853f
---

# Use Microsoft Purview risk and compliance solutions instead of the older information management and records management features in SharePoint for Microsoft 365 - SharePoint in Microsoft 365 | Microsoft Learn

Important

Read the overview to get a summary of the plan to deprecate the applicable older features from SharePoint for Microsoft 365 records management. For more information and links to important articles and pages, see [migration strategies](migration-strategies).

Review the older information management and records management features in SharePoint for Microsoft 365 deprecation timeline for dates that have been announced and for updates on new deprecation announcements.

## Overview

If you need to retain or delete content in Microsoft 365, we recommend using Microsoft Purview Data Lifecycle Management and Microsoft Purview Records Management features instead of older information management and records management features in SharePoint for Microsoft 365.

We have a long-term deprecation plan for these older features. More information, including dates, is in the deprecation timeline. Feature deprecations are communicated in advance to give customers time to prepare and perform any applicable migration activities.

The following older information management and records management features in SharePoint for Microsoft 365 are under consideration for deprecation:

- Record Center

    - [Create a record center site](https://support.microsoft.com/en-us/office/create-a-records-center-6bf1488b-62a8-486c-90dd-54b6bcce4b3a#:%7E:text=You%20need%20to%20take%20the%20following%20steps%20to,on%20the%20Records%20Center%20site.%20...%20See%20More.)
    - [Submit records to the record center](https://support.microsoft.com/en-us/office/introduction-to-the-records-center-bae6ca5a-7b19-40e0-b433-e3613a747c2c) (commonly referred to as "send to" location)
    - [Content Organizer](https://support.microsoft.com/en-us/office/configure-the-content-organizer-to-route-documents-b0875658-69bc-4f48-addb-e3c5f01f2d9a#:%7E:text=Each%20time%20that%20a%20document,in%20a%20different%20site%20collection.)
- [Information management policies](intro-to-info-mgmt-policies)
- [In-place records management,](https://support.microsoft.com/en-us/office/configuring-in-place-records-management-7707a878-780c-4be6-9cb0-9718ecde050a?ui=en-us&amp;rs=en-us&amp;ad=us) including [vault abilities.](https://support.microsoft.com/en-us/office/introduction-to-the-records-center-bae6ca5a-7b19-40e0-b433-e3613a747c2c)
- [Document deletion policies (deletion only)](https://support.microsoft.com/en-us/office/create-a-document-deletion-policy-in-sharepoint-server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff?ui=en-us&amp;rs=en-us&amp;ad=us)
- [Policies for site closure and deletion (deletion only)](https://support.microsoft.com/en-us/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5)

## Deprecation summary

The following key points summarize how deprecation works:

- Microsoft won't automatically migrate your older information management and records management features in SharePoint for Microsoft 365. If you choose not to migrate to supported features, the older features might no longer be supported.
- Between now and the deprecation date of the feature, you have the flexibility to migrate your scenarios on your own schedule.
- If you have configured SharePoint sites for content type policies or information management policies, those policies continue to be ignored while a retention policy or retention label policy is in effect.
- Deprecation for features might include some or all the following outcomes:
    - Microsoft might not support the feature.
    - It might no longer be visible in the user interface.
    - Configurations might not be available through the user interface or programmatically, including enable and disable actions.
    - When fully deprecated, backend services supporting behaviors for the feature might no longer function as expected.

## Deprecation timeline

Note

Any future dates and timelines are approximate and might change as we develop our plans further.

### Worldwide service

#### Upcoming

November 2023 – Announcement of the first set of features in the deprecation plan and timelines.

January 2025 - The following features will no longer be supported by Microsoft and configurations will no longer be available:

- Record Center site template, used to create a new Record Center site.
- Configure systems to submit files to a site using the Record Center programmable interface (commonly referred to as "send to" location). ​
- Content Organizer.

April 2026 - The following features will no longer be supported by Microsoft:

- Information Management Policies for targeting policy to library, folders & content Types, Name & Admin Description, Policy Statement, Retention, Auditing, Barcodes, Labels.
- In-Place Records Management for Vault abilities, Record Restrictions, Record Declaration Availability, Declaration Roles.
- Document deletion policies, Policies for site closure and deletion.

### Government clouds (GCC, GCC-H, DoD)

#### Upcoming

November 2023 – Announcement of the first set of features in the deprecation plan and timelines.

January 2025 - The following features will no longer be supported by Microsoft and configurations will no longer be available:

- Record Center site template, used to create a new Record Center site.​
- Configure systems to submit files to a site using the Record Center programmable interface (commonly referred to as "send to" location). ​
- Content Organizer.

April 2026 - The following features will no longer be supported by Microsoft:

- Information Management Policies for targeting policy to library, folders & content Types, Name & Admin Description, Policy Statement, Retention, Auditing, Labels.
- In-Place Records Management for Vault abilities, Record Restrictions, Record Declaration Availability.
- Document deletion policies, Policies for site closure and deletion.

## Migrating from older features to modern features

Modern Microsoft Purview features have flexible configuration options to help meet your data lifecycle and records management needs. The specific configuration that works best for your organization depends on your organization's governance strategy and applicable requirements.

To identify what works best for your scenarios and understand options for migrating your organization's older features to modern Purview solutions, see [migration strategies](migration-strategies).