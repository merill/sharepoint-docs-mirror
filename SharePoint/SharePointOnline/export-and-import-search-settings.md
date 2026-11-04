---
layout: Conceptual
title: Export and import customized search configuration settings - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/export-and-import-search-settings
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
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.collection: M365-collaboration
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.assetid: b136a278-d302-4dc4-84b9-80287c59afdf
description: Learn how to export and import customized search configuration settings between tenants, site collections, and sites.
locale: en-us
document_id: 7a6d5348-0b97-842d-cc4d-e50c04bd8bd4
document_version_independent_id: 1a9d4b68-d4cb-ff62-cd2d-32c0e7e73298
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/export-and-import-search-settings.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: export-and-import-search-settings
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/export-and-import-search-settings.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
platformId: 6591550c-5ebb-8d9a-9ed9-6e62b627c20e
---

# Export and import customized search configuration settings - SharePoint in Microsoft 365 | Microsoft Learn

As a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) and [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365, you can export and import customized search configuration settings between tenants, site collections, and sites. The settings that you export and import include all customized query rules, result sources, result types, ranking models and site search settings. It's also possible to export customized search configuration settings from a Search service application and import the settings to tenants, site collections, or sites. You can't export the default configuration settings.

## Overview

When you export customized search configuration settings, SharePoint creates a search configuration file in XML format. This search configuration file includes all exportable customized search configuration settings at the tenant, site collection, or site level from where you start the export. A search configuration file for a site collection doesn't contain search configuration settings from the individual sites within the site collection.

When you import a search configuration file, SharePoint creates and enables each customized search configuration setting in the tenant, site collection or site from where you start the import.

This table shows the settings that you can export or import. For each setting, you'll find dependencies on other customized search configuration settings. If the customized search configuration settings depend on a customized search configuration setting at a different level, for example, if a site query rule depends on a result source at site collection level, you must export and import settings at all of the relevant levels.

| Customized search configuration setting | Dependency on other customized search configuration settings |
| --- | --- |
| Query rules. These include result blocks, promoted results, and user segments. | Result sources, result types, search schema, ranking model. |
| Result sources | Search schema |
| Result types | Search schema, result sources, display templates |
| Search schema | None |
| Ranking model | Search schema |

### Conditions that can cause the import to fail

If the search configuration file and the target for your import have settings with the same name, the import of the search configuration file fails when it encounters this setting. There are exceptions however:

- If you reimport a search configuration file, the settings that have the same name in the search configuration file and on the target do not cause the import to fail.
- Managed properties with the same name do not cause an import to fail if the individual managed property settings are the same on the property in the search configuration file and on the target property.
- Managed properties with the same name do not cause an import to fail if the aliases and mappings to crawled properties are different on the managed property in the search configuration file and on the target managed property. The import adds the aliases and mappings on the managed property in the search configuration file to the aliases and mappings on the target managed property.

If the search configuration file contains managed property names or aliases that contain invalid characters, the import fails when it encounters that managed property name or alias.

The managed property names and aliases of a search schema must be unique for a site and its parent site collection. This means:

- If your search configuration file has a managed property that has the same name as an alias for a managed property on your target site or the parent site collection of your target site, then the import fails.
- If your search configuration file has a managed property with an alias that has the same name as a managed property on your target site or the parent site collection of your target site, then the import fails.

Note

Any customized search settings that were created and enabled by SharePoint before the import failed, remain enabled.

If the import fails, remove the condition that caused the failure and reimport the search configuration file. For example, if the Notes column states that there is already a query rule with the same name as the query rule that you are trying to import, then you should remove that query rule either from the target or from the import file, and then reimport the file. See [Invalid characters causing your import to fail](export-and-import-search-settings#__toc351540665) later in this article.

## Export customized search configuration settings from a tenant

1. Go to [**More features** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185077), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.
2. Under **Search**, select Open.
3. Select **Export Search Configuration**.
4. In the dialog, select **Save**.

## Export customized search configuration settings from a site

1. On the site, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and then select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**.
2. On the **Site Settings** page, in the **Search** section, select **Configuration Export**.
3. In the dialog, select **Save**.

## Export customized search configuration settings from a site collection

1. On the site, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and then select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**.
2. On the **Site Settings** page, in the **Site Collection Administration** section, select **Search Configuration Export**.
3. In the dialog, select **Save**.

## Import customized search configuration settings to a tenant

1. Go to [**More features** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185077), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.
2. Under **Search**, select **Open**.
3. On the **Import Search Configuration** page, browse to the file you want to import.
4. Select **Import**.
5. On the **Search Config List** page, verify that:
6. The search configuration file you imported is in the list, and that its status is **Imported Successfully**.

    If the file hasn't been imported successfully, then the **Notes** column provides more details about what happened.
7. The **Scope** column shows that the settings you imported are at the right level, that is, at the level you meant to import the file to. For example, if you imported your settings at the site collection level instead of at the site level, you'd see this information in the **Scope** column. The **Scope** column shows at which level the search configuration settings were enabled. The levels are: tenant (Tenant), site collection (SPSite), or site level (SPWeb).

## Import customized search configuration settings to a site

1. On the site, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and then select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**.
2. On the **Site Settings** page, in the **Search** section, select **Configuration Import**.
3. On the **Import Search Configuration** page, browse to the file you want to import.
4. Select **Import**.
5. On the **Search Config List** page, verify that:
6. The search configuration file you imported is in the list, and that its status is **Imported Successfully**.

    If the file hasn't imported successfully, then the **Notes** column provides more details about what happened.
7. The **Scope** column shows that the settings you imported are at the right level, that is, at the level you meant to import the file to. For example, if you imported your settings at the site collection level instead of at the site level, you'd see this information in the **Scope** column. The **Scope** column shows at which level the search configuration settings were enabled. The levels are: tenant (Tenant), site collection (SPSite), or site level (SPWeb).

## Import customized search configuration settings to a site collection

1. On the site, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and then select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**.
2. On the **Site Settings** page, in the **Site Collection Administration** section, select **Search Configuration Import**.
3. On the **Import Search Configuration** page, browse to the file you want to import.
4. Select **Import**.
5. On the **Search Config List** page, verify that:
6. The search configuration file you imported is in the list, and its status is **Imported Successfully**.

    If the file hasn't imported successfully, then the **Notes** column provides more details about what happened.
7. The **Scope** column shows that the settings you imported are at the right level, that is, at the level you meant to import the file to. For example, if you imported your settings at the site collection level instead of at the site level, you'd see this information in the **Scope** column. The **Scope** column shows at which level the search configuration settings were enabled. The levels are: tenant (Tenant), site collection (SPSite), or site level (SPWeb).

## Invalid characters causing your import to fail

If managed properties or aliases contain any of the listed characters, the import of the customized search schema that contains these properties will fail.

| Character | Name |
| --- | --- |
|  | space |
| : | colon |
| ; | semicolon |
| , | comma |
| ( | opening parenthesis |
| ) | closing parenthesis |
| [ | opening bracket |
| ] | closing bracket |
| { | opening brace |
| } | closing brace |
| % | percent |
| $ | dollar sign |
| \_ | underscore |
| + | plus sign |
| ! | exclamation point |
| \* | asterisk |
| = | equal sign |
| & | ampersand |
| ? | question mark |
| @ | at sign |
| # | number sign |
| \ | backslash |
| ~ | tilde |
| &lt; | opening angle bracket |
| &gt; | closing angle bracket |
| | | pipe |
| ` | grave accent |
| ^ | caret |
| ' | escape sequence |
| " | escape sequence |

## Known issue

**Unable to load Search Configuration List**

When you import search configuration files into the tenant admin search settings page, you might encounter an issue that the **Search Configuration List** could not display properly and you might receive a "File not found" error.

This issue only blocks the UI from displaying the list of search configuration files you imported and would not break the **Import** functionality. Your search configuration will be imported properly.

Since you are unable to check the status of the search configuration file you imported from the UI, you could choose an alternative way to access the list, like [SharePoint CSOM API](/en-us/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-client-library-code) or [SharePoint Online REST API](/en-us/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-rest-endpoints).

**Unable to import stale search configuration XML file**

If the search configuration file was exported a long time ago, the import might fail.

If the exported search configuration file is stale, you should export a new search configuration first and then use it to import the list of search configuration files.