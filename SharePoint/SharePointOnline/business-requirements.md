---
layout: Conceptual
title: Identify business requirements for SharePoint and OneDrive - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/business-requirements
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2022-06-10T00:00:00.0000000Z
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords: NOCSH
ms.topic: concept-article
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- essentials-get-started
ms.custom: intro-get-started
search.appverid: MET150
description: Identify your business requirements for SharePoint and OneDrive as you plan your rollout.
locale: en-us
document_id: 99586930-f93d-1f12-ad8c-88ee025eb890
document_version_independent_id: 82da90b8-a5a4-46ac-8879-65c533b8cfd2
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/business-requirements.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: business-requirements
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/business-requirements.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 71da5cf4-587f-1c11-1ca9-c09508268e5a
---

# Identify business requirements for SharePoint and OneDrive - SharePoint in Microsoft 365 | Microsoft Learn

This article provides an overview of SharePoint and OneDrive capabilities that can help you determine how to best take advantage of these services for your organization. Use this information to help you plan your rollout and also to find new capabilities that your current solutions might not offer.

## Best practices for requirements gathering

**Define user journeys and core use cases.** How do people in your organization collaborate now? Where do they store files? How do they share news and other information? An important part of planning for SharePoint and OneDrive is documenting how your organization does collaboration tasks today. You can then map those tasks to new processes using SharePoint and OneDrive. These tasks can then become test cases for your initial pilot rollout. **Evaluate your migration needs.** Most organizations have files and other content that they want to move to Microsoft 365. Some of this content may be in use every day by the people in your organization. Moving it all can take time. As you plan your rollout, plan for how you can migrate content while keeping the people in your organization productive. See [Migration planning for SharePoint and OneDrive rollout](plan-rollout-migration) for more information. If you use SharePoint Server on-premises, see [Hybrid OneDrive and SharePoint in Microsoft 365](hybrid). If you have paper records to import, see [Overview of optical character recognition](/en-us/microsoft-365/documentprocessing/ocr-overview).

**Involve legal and compliance teams early.** Most organizations have legal or compliance requirements around how they handle various kinds of data. Microsoft 365 offers many options to help you maintain compliance in your organization. As you plan your rollout, involve your legal or compliance team early in the process to help maintain your compliance requirements as you transition to SharePoint and OneDrive. See [Create a compliant SharePoint and OneDrive environment](compliant-environment) for more information.

**Drive agreement across stakeholders.** Securing the participation and buy-in of key people within your organization is critical to successful user adoption. This support can come from business-focused leaders, IT leadership, or anyone else who has a vested interest in seeing Microsoft 365 succeed in the organization. It is important to have both executive or business leader support and product champions to help carry the knowledge to their peers. Whether you're formally delegating the product champion role or allowing it to grow organically, champions are mission critical to user adoption.

## Core SharePoint and OneDrive use cases

Core use cases for SharePoint and OneDrive include:

- File storage
- File collaboration
- Sites for team collaboration
- Sites for news and intranet

If you're currently using other software or services to enable these use cases in your organization, we recommend mapping each of your current use cases with the capabilities of SharePoint and OneDrive. This will help ensure a smooth transition as you roll SharePoint and OneDrive out and provide you with a list of process changes to communicate with your users. ([Training and change management for rolling out SharePoint and OneDrive](training-change-management) provides a list of resources that you can share with your users to help them get started with SharePoint and OneDrive.)

The sections below provide an overview of these use cases with links to more in-depth information.

### File storage

The file storage options in Microsoft 365 are SharePoint and OneDrive.

**Personal work files are stored in OneDrive.** With OneDrive, each user has a location where they can store their personal work files. These files are not shared with anyone by default, but can be easily shared with others for collaboration.

**Shared files are stored in SharePoint.** SharePoint sites can be used to store files that will be accessed by multiple people. People who have access to the site have access to the files.

Microsoft Teams uses SharePoint sites to store files. When you upload a file to the Teams **Files** tab, it's stored in a SharePoint site. (For more information about how Teams and SharePoint interact, see [Overview of Teams and SharePoint integration](teams-connected-sites))

### File collaboration

In SharePoint and OneDrive, user can use [Microsoft 365 Apps](/en-us/deployoffice/about-microsoft-365-apps) (a version of Office that's available through many Microsoft 365 plans) to create and edit documents. Other applications can be used to create and edit other file types. These files can easily be shared with others - including people outside your organization (if you allow it).

**Share OneDrive files using sharable links.** In OneDrive, a user's files are private by default. Users can share OneDrive files with others by using *sharable links* which give others access to the file. Links can be created that grant access to particular people or to anyone in your organization. The person who shared the file can remove others' access by editing or deleting the link.

**Collaborate in a site or team.** In a SharePoint site or a Microsoft Teams team, all the members of the site or team have access to - and can easily collaborate on - the files stored there.

**Share SharePoint files using sharable links.** If a user needs to share a SharePoint file with someone outside the site or team, they can use sharable links in the same way that they do in OneDrive.

**Sync files for offline access.** With the OneDrive sync app, users can sync files between their computer and the Microsoft 365 cloud. When users add, change, or delete a file or folder locally, the file or folder is added, changed, or deleted in the cloud and vice versa. Users can work with synced files directly in File Explorer or Finder and the apps they use. Whenever the user is online, any changes that they or other users make will sync automatically.

For more details on file collaboration in SharePoint and OneDrive, see [Intro to file collaboration in Microsoft 365, powered by SharePoint](intro-to-file-collaboration) and [File collaboration in SharePoint with Microsoft 365](deploy-file-collaboration).

### Intranet

One of the core capabilities of SharePoint is a wide variety of options and tools to create intranet sites for your organization. Your intranet might include your organization's main landing page, portals for corporate communications, and individual sites for departments or divisions (like IT or HR).

Moving your intranet to SharePoint in Microsoft 365 might take a while, particularly if you already have extensive intranet content. We recommend undertaking this task after you've completed your rollout of SharePoint and OneDrive.

For details about how to create an intranet using SharePoint, see [Intelligent intranet introduction and roadmap](intranet-team-overview) and [Plan an intelligent SharePoint intranet](plan-intranet).

## Governance and compliance

Governance and compliance are key for many organizations. As part of planning for SharePoint and OneDrive, consider which compliance features you want to roll out ahead of time. By having compliance features in place ahead of time, you can reduce the risk of compliance incidents. See [Create a compliant SharePoint and OneDrive environment](compliant-environment) for details on which compliance features to consider as part of your SharePoint and OneDrive rollout.

## Keys to successful user adoption

User adoption is important to the overall success of any new application or service. Ideally, to feel that you have maximized your investment in SharePoint and OneDrive, you need to maximize user engagement with them.

Creating awareness through awareness campaigns such as announcements, launch events, newsletters, town hall meetings, contests, and giveaways is a critical path to maximizing adoption. In addition, providing users with knowledge through classroom-style sessions and self-help guides helps them feel empowered to use OneDrive and SharePoint.

For more information about user adoption and change management when rolling out SharePoint and OneDrive, see [Training and change management for rolling out SharePoint and OneDrive](training-change-management)