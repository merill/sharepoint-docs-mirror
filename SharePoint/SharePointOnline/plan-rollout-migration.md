---
layout: Conceptual
title: Migration planning for SharePoint and OneDrive rollout - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/plan-rollout-migration
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
ms.topic: upgrade-and-migration-article
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection: 
ms.custom: intro-get-started
search.appverid: MET150
description: Plan your migration of sites and files as part of your OneDrive and SharePoint rollout.
locale: en-us
document_id: 90f09394-e676-dd4a-f38a-1af5ce0be47a
document_version_independent_id: ab3cab7b-750b-fcaa-8ca0-52b5d04517fa
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/plan-rollout-migration.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: plan-rollout-migration
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/plan-rollout-migration.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/e2560d35-6f40-44b4-a8f1-a6691f82061d
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/2e5e1bdc-5c79-4dc1-9c05-485e6e6ae0ce
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: f75e2427-af70-832d-bca6-af9b682b8626
---

# Migration planning for SharePoint and OneDrive rollout - SharePoint in Microsoft 365 | Microsoft Learn

A key task in deploying SharePoint and OneDrive for your organization is a plan to migrate your users' existing files. Depending on where these files are kept, there are several options, discussed below. You can choose one or more of these options depending on the number and location of files that you need to migrate.

The following types of data can be migrated with Microsoft tools:

- Files and folders (from on-premises or other cloud providers)
- SharePoint Server sites and content
- SharePoint Server 2010 workflows

We recommend that you have the people in your organization review the content that they're planing to migrate to SharePoint and OneDrive. There may be old content that isn't needed anymore and can be deleted or archived. This can help you save migration time and storage space in Microsoft 365.

Keep in mind that migrating content may result in a surge of network activity as large amounts of data is moved to SharePoint and OneDrive.

For complete information on migrating content to SharePoint and OneDrive, see [Migrate your content to Microsoft 365](/en-us/sharepointmigration/migrate-to-sharepoint-online).

#### Automation and workflows

If you have automated processes or workflows around files or other content, you may need to consider how to integrate those processes with Microsoft 365 or migrate them there entirely. Consider using [SharePoint Framework solutions](/en-us/sharepoint/dev/) or [Microsoft Power Platform](/en-us/power-platform).

If you have SharePoint Server 2010 workflows, you can migrate them to Power Automate by using the SharePoint Migration Tool. See [Overview: Migrate SharePoint Server 2010 workflows to Power Automate](/en-us/sharepointmigration/spmt-workflow-overview) for more information.

#### Hybrid

If you use SharePoint Server on-premises, you may want to set up a hybrid environment with SharePoint in Microsoft 365 while you migrate or as a long term solution. See [Hybrid OneDrive and SharePoint in Microsoft 365](hybrid) for more information.

## Migrating users' personal work files to OneDrive

As part of your rollout, you may be migrating your users' personal work files to OneDrive. As part of this process, you may need to pre-provision users' OneDrive libraries.

Normally, a user's OneDrive is created the first time they access OneDrive. If you will be migrating your users' files on their behalf before they begin using OneDrive, you'll need to pre-provision OneDrive for each of them. See [Pre-provision OneDrive for users in your organization](/en-us/onedrive/pre-provision-accounts) for details.

### Files in on-premises OneDrive or MySites libraries

If users' existing files are in on-premises SharePoint Server, OneDrive, or MySites, you can use the SharePoint Migration Tool to migrate the files to Microsoft 365. For info, see [Overview of the SharePoint Migration Tool (SPMT)](/en-us/sharepointmigration/introducing-the-sharepoint-migration-tool).

### Files in users' commonly used folders

If user files are located in their Windows or Mac Desktop or Documents folders, you can move and redirect these locations to OneDrive. You can enable this feature during the initial rollout of OneDrive or sometime later. For more info, see [Redirect and move Windows known folders to OneDrive](/en-us/onedrive/redirect-known-folders) and [Redirect and move macOS Desktop and Documents folders to OneDrive](/en-us/onedrive/redirect-known-folders-macos).

### Files in other local disk folders

If users have other work files in various locations on their computers, it's often easiest for them to manually move the files to OneDrive. After you deploy the OneDrive sync app to your users' computers, you can instruct them to move their work files to the OneDrive folder on their computer. For more information, see [Move files from OneDrive to OneDrive for work or school](https://support.microsoft.com/office/7fb28cad-7e25-451f-8b4b-2d1a71e5c0e9).

## Migrating sites from SharePoint Server to SharePoint in Microsoft 365

If you have sites in SharePoint Server, you can migrate them to SharePoint in Microsoft 365 by using the SharePoint Migration Tool. You can do this as part of your SharePoint and OneDrive rollout, or you can do it later. For details, see [Overview of the SharePoint Migration Tool (SPMT)](/en-us/sharepointmigration/introducing-the-sharepoint-migration-tool).

## Migrating files in file shares or hosted on other cloud providers

For files located in file shares or other cloud providers, you can use Migration Manager to migrate them to SharePoint and OneDrive. For details, see [Migrate files shares to Microsoft 365 with Migration Manager](/en-us/sharepointmigration/mm-get-started).

See these references for specific instructions on how to migrate from different locations:

- [Migrate from file shares](/en-us/sharepointmigration/mm-get-started)
- [Migrate from Box](/en-us/sharepointmigration/mm-box-overview)
- [Migrate from Google Workspace](/en-us/sharepointmigration/mm-google-overview)
- [Migrate from Dropbox](/en-us/sharepointmigration/mm-dropbox-overview)
- [Migrate from Egnyte](/en-us/sharepointmigration/mm-egnyte-overview)
- [Migrate SharePoint Server sites and content](/en-us/sharepointmigration/introducing-the-sharepoint-migration-tool)
- [Migrate SharePoint Server workflows](/en-us/sharepointmigration/spmt-workflow-overview)