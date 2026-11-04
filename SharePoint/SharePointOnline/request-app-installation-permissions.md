---
layout: Conceptual
title: Overview of apps in SharePoint in Microsoft 365 - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/request-app-installation-permissions
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: 
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 2018-05-22T00:00:00.0000000Z
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
- MET150
ms.assetid: 5a25c5b0-bdfb-49f8-8ca3-046edc9cf598
description: Learn how app requests work in SharePoint in Microsoft 365.
locale: en-us
document_id: e34e2be9-4d0a-49ee-eeff-a8b1888e9e82
document_version_independent_id: abb054f7-f998-9d0c-9e3e-7e464a522131
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/request-app-installation-permissions.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: request-app-installation-permissions
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/request-app-installation-permissions.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 470c18a9-8fcb-ac4f-6c3d-2bbe44909a2d
---

# Overview of apps in SharePoint in Microsoft 365 - SharePoint in Microsoft 365 | Microsoft Learn

Apps are small, easy-to-use web applications that add functionality to SharePoint sites. They offer unlimited possibilities for customizing your sites in ways that are specific to your organization. For example, you can add apps that perform general tasks such as time and expense tracking, or apps that make it easy for customers to contact you, or productivity apps that enable you to establish data connections and develop reports for your stakeholders.

Some apps are included with SharePoint, others might be developed by your organization, and still others are created by third-party developers and available for purchase from the SharePoint Store.

Only those users who have the appropriate permission level can add apps to a site. Typically, Full Control permission (or membership in the Site Owners group) is the minimum requirement. But some apps require access to data sources or web services to read data required for the app. This kind of app has permissions associated with it.

When the app requires organization-level permissions, the requestor will need approval from a Microsoft 365 admin to continue with the installation. The approval process includes a workflow, called the permission request flow, which ensures installation requests are directed to the right person.

This article is intended for [SharePoint Administrators](/en-us/sharepoint/sharepoint-admin-role) and [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365 at the organization level who receive requests for app installation.

## Make the application available

Once the status has been changed to **Approved**, go to the SharePoint Store and acquire the app. This is done by clicking the link next to **View App Details** on the App Request entry.

At this point, site owners can check the **Your Requests** list to view the status of their request. After the application has been acquired and approved, it will show up in the **Apps you've requested** list.

## Delegate approval authority

As a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365 in your organization, you can delegate app approval authority as a way of spreading the approval workaround, or alleviating approval bottlenecks. Remember that apps are stored and managed in the Apps site. To grant app approval permission to select users, you can add them as site admins on the Apps site.

Caution

When you add users as site admins on the Apps site, you are giving them the ability to approve the installation of apps that have organization-wide impact. Consider this decision carefully.

To add site collection admins to the Apps site:

1. Go to the [Active sites page of the new SharePoint admin center](https://admin.microsoft.com/sharepoint?page=siteManagement&amp;modern=true), and sign in with an account that has [admin permissions](/en-us/sharepoint/sharepoint-admin-role) for your organization.
2. Select the Apps site, and then select **Membership** on the command bar to open the details panel.
3. Make the appropriate selection based on the type of member and provide input and select the name of the person who you want to manage apps, and then select **Save**.