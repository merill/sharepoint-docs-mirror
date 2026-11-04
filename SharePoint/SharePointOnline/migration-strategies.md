---
layout: Conceptual
title: Migration strategies for moving to Microsoft Purview risk and compliance solutions from older information management and records management for SharePoint for Microsoft 365 - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/migration-strategies
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
ms.date: 2025-01-29T00:00:00.0000000Z
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
ms.custom:
- seo-marvel-apr2020
description: This article explains how to plan your migration, understand the modern solution, and decide which modern solution to use.
locale: en-us
document_id: 0e5bc573-0d64-c3b8-a4bb-39debf82889f
document_version_independent_id: 1fe5cbc4-70ab-f362-5cf7-c53c6c13a94b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/migration-strategies.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: migration-strategies
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/migration-strategies.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://authoring-docs-microsoft.poolparty.biz/devrel/57eae111-0f3b-497e-be07-450fd1409dea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ac8bf8ab-8134-4c9a-9f2e-58b31575b492
platformId: fe412891-98e1-d253-91d3-57d3d1ac9ad7
---

# Migration strategies for moving to Microsoft Purview risk and compliance solutions from older information management and records management for SharePoint for Microsoft 365 - SharePoint in Microsoft 365 | Microsoft Learn

Before you begin, it's important to plan your migration. You might need to interact with multiple stakeholders within your organization depending on the use case. It's important for you to carefully design your migration strategy. We've provided a few examples to help guide your next steps.

## Prepare for using Purview risk and compliance solutions

1. Review your existing older policies and decide which ones you need to recreate in the modern features. Confirm your goals for compliance and which of the features you’re using today to meet those needs. For example, you might have a business requirement to keep your content in some SharePoint sites for one year and are using information management policies today to accomplish this requirement. This review can also be an opportunity to audit your retention schedule and identify if there are any duplicate, outdated, or conflicting policies that you might not want to recreate.
2. Use this guide to understand what you need to do, identify the older feature and behavior you’re migrating from, and decide which modern feature to use. It's also recommended to confirm that you have the applicable licenses for the modern features. Learn more about [licensing for Purview Data Lifecycle Management and Purview Records Management.](/en-us/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-purview-data-lifecycle-management--microsoft-purview-records-management)

    You might be eligible for a free trial of Microsoft Purview risk and compliance solutions, including premium Purview Data Lifecycle Management and Purview Records Management features. See [free trial.](/en-us/purview/purview-trial)
3. Configure your modern features. Implement the strategies defined in your plan and set up the modern features that meet your requirements.
4. Verify that your new features are working as expected:

    - Wait for the [applicable time period for your new features to take effect](/en-us/purview/retention?branch=main&amp;branchFallbackFrom=pr-en-us-5917&amp;tabs=table-overriden#how-long-it-takes-for-retention-settings-to-apply)
    - [Confirm policies applied to a location using policy lookup](/en-us/purview/retention?tabs=table-overriden&amp;branch=main#policy-lookup)
    - [Use activity explorer to review actions related to labeling content](/en-us/purview/data-classification-activity-explorer?branch=main#activity-types)
    - [Use content explorer to review labeled items](/en-us/purview/data-classification-content-explorer?branch=main#retention-labels)
    - [Check the policy status for errors](/en-us/microsoft-365/troubleshoot/retention/identify-errors-in-retention-and-retention-label-policies#how-to-check-for-policy-errors)

## Older features and using Purview features instead

### Record center site

| Older feature | Purview feature suggestion |
| --- | --- |
| [Record Center site templates](https://support.microsoft.com/en-us/office/create-a-records-center-6bf1488b-62a8-486c-90dd-54b6bcce4b3a#:%7E:text=You%20need%20to%20take%20the%20following%20steps%20to,on%20the%20Records%20Center%20site.%20...%20See%20More.) helps organizations implement their records management and retention programs. | - [Create a communication site to replace the records center.](https://support.microsoft.com/en-us/office/create-a-team-or-communication-site-551e190a-8fbe-47ae-a88a-798b443c46b1)<br>- Use Purview Data Lifecycle Management for [retention policies that retain or delete content.](/en-us/purview/create-retention-policies?tabs=teams-retention)<br>- Use Purview Records Management for retention labels that:<br>    - [Apply by default](/en-us/purview/create-apply-retention-labels?tabs=manual-outlook%2Cdefault-label-for-sharepoint#default-labels-for-sharepoint-and-outlook) to items within a library, folder, or document set.<br>    - [Auto-apply to content](/en-us/purview/apply-retention-labels-automatically)<br>    - [Classify contents as records](/en-us/purview/declare-records) |

### Submit records to the record center

| Older feature | Purview feature suggestion |
| --- | --- |
| [The record collection programmable interface](https://support.microsoft.com/en-us/office/introduction-to-the-records-center-bae6ca5a-7b19-40e0-b433-e3613a747c2c) (commonly referred to as “send to” location) enables organizations to automatically submit files to a SharePoint site. | Configure [PowerAutomate](/en-us/power-automate/getting-started) to [route records automatically to your new communication site.](/en-us/dynamics365/customer-service/routing-trigger-automatic) |

### Content Organizer

| Older feature | Purview feature suggestion |
| --- | --- |
| [Content Organizer](https://support.microsoft.com/en-us/office/configure-the-content-organizer-to-route-documents-b0875658-69bc-4f48-addb-e3c5f01f2d9a) automatically routes content to a location in a SharePoint site. | To route content, including records, to locations within your sites:<br>- Configure [PowerAutomate](/en-us/power-automate/getting-started) to route content automatically to your sites.<br>- [Create a rule in Microsoft Syntex that moves or copies files in document libraries.](/en-us/microsoft-365/syntex/content-processing-create-rules)<br>- Use [Audit (Standard)](/en-us/purview/audit-solutions-overview?view=o365-worldwide&amp;preserve-view=true) to maintain logs. |

### Information Management policies

| Older feature | Purview feature suggestion |
| --- | --- |
| [Information Management policies](intro-to-info-mgmt-policies) allow for schedules to be defined on a library and its folders, or to site content types. | - Use Purview Data Lifecycle Management for [retention policies that retain or delete content.](/en-us/purview/create-retention-policies?tabs=teams-retention%22%20%5Ct%20%22_blank)<br>- Use Purview Data Lifecycle Management or Purview Records Management for:<br>    - [Retention labels](/en-us/purview/create-retention-labels-data-lifecycle-management) that are [applied by default to content in a folder or library.](/en-us/purview/create-apply-retention-labels?tabs=manual-outlook%2Cdefault-label-for-sharepoint)<br>    - [Automatically apply](/en-us/purview/apply-retention-labels-automatically) to specified [content types](/en-us/microsoft-365/community/auto-apply-retention-labels-in-office-365-using-content-types-and-metadata).<br>    - [Customizing what happens at the end of the retention period.](/en-us/purview/retention-label-flow)<br>    - [Managing single and multi-stage disposition of content.](/en-us/purview/disposition?view=o365-worldwide&amp;preserve-view=true)<br>- Use [PowerAutomate](/en-us/power-automate/getting-started) to [route content automatically using custom flow.](/en-us/dynamics365/customer-service/routing-trigger-automatic)<br>- Use [Audit (Standard).](/en-us/purview/audit-solutions-overview?view=o365-worldwide%22%20%5Cl%20%22audit-standard%22%20%5Ct%20%22_blank&amp;preserve-view=true) to maintain logs of events and operations performed.<br>- To include information on a file (policy labels), [create and publish sensitivity labels](/en-us/purview/create-sensitivity-labels?view=o365-worldwide&amp;preserve-view=true) that apply [content marking](/en-us/purview/sensitivity-labels-office-apps#dynamic-markings-with-variables). |

### Document deletion policies

| Older feature | Purview feature suggestion |
| --- | --- |
| [Document deletion policies](https://support.microsoft.com/en-us/office/create-a-document-deletion-policy-in-sharepoint-server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff?ui=en-us&amp;rs=en-us&amp;ad=us) permanently delete content from a site after a specified period of time. | Use Purview Data Lifecycle Management for [retention policies that retain or delete content.](/en-us/purview/create-retention-policies?tabs=teams-retention%22%20%5Ct%20%22_blank) |

### In-place records management

| Older feature | Purview feature suggestion |
| --- | --- |
| [In-place records management](https://support.microsoft.com/en-us/office/configuring-in-place-records-management-7707a878-780c-4be6-9cb0-9718ecde050a#:%7E:text=If%20not%20already%20done%2C%20you%20need%20to%20activate,features%20%2C%20find%20In%20Place%20...%20See%20More) specifies restrictions on documents declared as records. [Vault abilities](https://support.microsoft.com/en-us/office/introduction-to-the-records-center-bae6ca5a-7b19-40e0-b433-e3613a747c2c) allow administrators to prevent the direct tampering with records, track version changes, and audit actions. | - Use Purview Records Management for retention labels that:<br>    - Are [published for users to manually apply.](/en-us/purview/create-apply-retention-labels?tabs=manual-outlook%2Cdefault-label-for-sharepoint&amp;branch=main)<br>    - [Auto-apply to content.](/en-us/purview/apply-retention-labels-automatically?branch=main)<br>    - [Classify contents as records to prevent tampering and add more audit activities.](/en-us/purview/declare-records?branch=main)<br>    - [Take action during and at the end of the content lifecycle.](/en-us/purview/file-plan-manager?branch=main)<br>- Use [Audit (Standard)](/en-us/purview/audit-solutions-overview?view=o365-worldwide&amp;preserve-view=true&amp;branch=main) to maintain logs. |