---
layout: Conceptual
title: Security considerations of allowing custom script - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/security-considerations-of-allowing-custom-script
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: lucaband
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 2024-09-23T00:00:00.0000000Z
audience: Admin
f1.keywords:
- NOCSH
ms.topic: article
ms.service: sharepoint-online
ms.subservice: admin
ms.collection:
- M365-collaboration
- M365-sam
ms.localizationpriority: medium
search.appverid:
- SPO160
- SPB160
- BSA160
- MET150
ms.assetid: b0420ab0-aff2-4bbc-bf5e-03de9719627c
description: 'Learn about security factors to consider before you allow users to run custom script on SharePoint sites or OneDrive. '
locale: en-us
document_id: 2bdc8c01-4004-138d-87fa-4f02d90ab7b9
document_version_independent_id: fa05c817-1441-39d3-5cda-103df2a1d0d1
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/security-considerations-of-allowing-custom-script.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: security-considerations-of-allowing-custom-script
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/security-considerations-of-allowing-custom-script.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: e620b7f3-96ea-12ec-54f5-5644f3c55582
---

# Security considerations of allowing custom script - SharePoint in Microsoft 365 | Microsoft Learn

Allowing users to customize sites and pages in SharePoint by inserting script can give them the flexibility to address different needs in your organization. However, you should be aware of the security implications of custom script.

When you allow users to run custom script, you can no longer enforce governance, scope the capabilities of inserted code, block specific parts of code, or block all custom code that has been deployed. Instead of allowing custom script, we recommend using the SharePoint Framework. For more info, see [An alternative to custom script](security-considerations-of-allowing-custom-script#spframework).

## What custom script can do

Every script that runs in a SharePoint page (whether it's an HTML page in a document library or a JavaScript in a Script Editor Web Part) always runs in the context of the user visiting the page and the SharePoint application. This means:

- Scripts have access to everything the user has access to.
- Scripts can access content across several Microsoft 365 services and even beyond with Microsoft Graph integration.

## You can't audit the insertion of script

As a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [above](/en-us/microsoft-365/admin/add-users/about-admin-roles), you can allow or block custom script capabilities for the whole organization or for specific site collections. (For info on how to do this, see [Allow or prevent custom script](allow-or-prevent-custom-script).) However, once you allow scripting, you can't identify:

- What code has been inserted
- Where the code has been inserted
- Who inserted the code

Any user who has "Add and Customize Pages" permission (part of the Design and Full Control permission levels) to any page or document library can insert code that can potentially have a powerful effect on all users and resources in the organization.

The script has access to more than just the page or site - it can access content across all site collections and other Microsoft 365 services in the organization. There are no boundaries for executing script. For info about site activity you can audit, see [Configure audit settings for a site collection](https://support.office.com/article/a9920c97-38c0-44f2-8bcb-4cf1e2ae22d2).

## You can't block or remove inserted script

If you've allowed custom script, you can change the setting to later prevent users from adding custom script, but you can't block the execution of script that has already been inserted. If dangerous or malicious script is inserted, the only way you can stop it is to delete the page that hosts it. This might result in data loss.

## An alternative to custom script

The [SharePoint Framework](/en-us/sharepoint/dev/spfx/sharepoint-framework-overview) is a page and web part model that provides a governed and fully supported way to build solutions using scripting technologies with support for open-source tooling. Key features of the SharePoint Framework:

- The framework runs in the context of the current user and connection in the browser.
- The controls are rendered in the normal page Document Object Model (DOM).
- The controls are responsive and accessible.
- Developers can access the lifecycle. Also to render, they can access load, serialize and deserialize, configuration changes, and more.
- You can use any browser framework you like: React, Handlebars, Knockout, Angular, and more.
- The toolchain is based on common open source client development tools like npm, TypeScript, Yeoman, webpack, and gulp.
- Admins have governance tools to immediately disable solutions regardless of the number of instances that have been used and the number of pages or sites across which they've been used.
- Solutions can be deployed in web parts and pages that use the classic experience or the new experience.
- Only Global Administrators, SharePoint Administrators, and people who have been given permission to manage the Apps site can add solutions. For info about giving users permission to manage the Apps site, see [Request app installation permissions](request-app-installation-permissions).