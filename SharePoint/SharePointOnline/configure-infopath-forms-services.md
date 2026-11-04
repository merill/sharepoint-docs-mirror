---
layout: Conceptual
title: Configure InfoPath Forms Services - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/configure-infopath-forms-services
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2018-07-11T00:00:00.0000000Z
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords:
- CSH
ms.topic: how-to
ms.custom:
- SPOTACfgInfoPathWebSrvcPrx
- SPOTACfgInfoPathSrvc
- admindeeplinkSPO
ms.service: sharepoint-online
ms.subservice: admin
ms.collection: M365-collaboration
ms.localizationpriority: medium
search.appverid:
- SPO160
- BSA160
- MET150
ms.assetid: a8609546-c0d7-4956-81b6-08e93eb4b290
description: How to configure Infopath in SharePoint.
locale: en-us
document_id: 450f9bd7-cf8a-779b-368a-41187574834d
document_version_independent_id: 76da0413-17e0-94fa-e59b-e667b459cce5
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/configure-infopath-forms-services.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: configure-infopath-forms-services
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/configure-infopath-forms-services.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/97159432-14a9-4307-a469-d2f2c75f0e33
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/50565c62-5f6b-4687-be38-323113c72c2e
platformId: e7e836e8-5291-09c4-3ec5-c879021f7814
---

# Configure InfoPath Forms Services - SharePoint in Microsoft 365 | Microsoft Learn

InfoPath Forms Services in SharePoint lets you deploy your organization's forms to your sites, enabling users fill out these forms in a web browser. You can configure InfoPath Forms Services in any of several ways, depending on the needs of your organization.

Note

InfoPath Forms Services 2013 is the last release of InfoPath Forms Services. Microsoft Power Apps is the recommended solution for creating and delivering custom forms for SharePoint lists. Create new forms with Power Apps from the command bar or the **Customize** button on SharePoint list forms. Support for InfoPath Forms Services will match the support lifecycle for SharePoint Server 2016.

## Overview

This article discusses settings that apply only to user form templates, which are form templates that are not deployed by a developer. User form templates don't require Full Trust, and they don't contain code or other business logic.

Form designers can publish user form templates to a list or a form library in a SharePoint site collection. Because user form templates can be deployed by many users, a server can potentially host thousands of user form templates. In large numbers, even form templates that contain no business logic can put a heavy load on the server.

## Configure browser-enabled user form templates

When form templates are published to a server that is running InfoPath Forms Services, the designer of the form template can choose to make the form template browser-enabled. This allows a user to fill out the form in a web browser.

As an administrator, you can configure the following template settings for browser-enabled user form templates:

- **Enable or disable publishing of browser-enabled form templates.** If you disable publishing, form designers can publish only form templates that are not browser-enabled. In this case, all browser-compatible features are disabled in the form template.
- **Enable or disable rendering of browser-enabled form templates.** If you disable rendering, users cannot use a web browser to fill out the form and must use Microsoft InfoPath Filler 2013 to open the form.

By default, browser-enabled user form templates can be published and rendered.

To configure browser-enabled user form templates:

1. Go to [**More features** in the new SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185077), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

Note

If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.

1. Under **InfoPath**, select **Open**.
2. In the **User Browser-enabled Form Templates** section, specify how you want user form templates to be processed by InfoPath Forms Services by completing the following steps:

    Note

    These settings apply only to form templates published to form libraries. Workflow form templates and list forms are not affected.

    1. Select the **Allow users to browser-enable form templates** check box to allow users to publish browser-enabled form templates.

    Note

    Clearing this check box disables browser-enabled form templates across the entire site collection.

    1. Select the **Render form templates that are browser-enabled by users** check box to allow browser-enabled form templates that users publish to be rendered in a web browser.

    Note

    If this option is not selected, users can still publish browser-compatible form templates to form libraries, but these form templates cannot be filled out in a web browser.
3. Select **OK**.

## Configure exempt user agents

To make indexing InfoPath forms faster and easier, you can specify which user agents to exempt from receiving an entire webpage to index. This means that when a user agent you've specified as exempt encounters an InfoPath form, the form will be returned as an XML file (which looks like a hierarchical text file) instead of an entire webpage. You can use the procedure below to select this option and populate the agent list.

1. Go to [**More features** in the new SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185077), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

Note

If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.

1. Under **InfoPath**, select **Open**.
2. In the **Exempt User Agents** section, select the **Customize the list of exempt user agents** check box, and then do one of the following:
3. To add a user agent to the exempt list, in the **Name** box, enter a name, and then select **Add**.
4. To remove a user agent from the list, select the name, and then select **Remove**.
5. Select **OK**.