---
layout: Conceptual
title: Custom list templates - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/lists-custom-template
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-06-25T00:00:00.0000000Z
ms.reviewer: hasaladi
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: article
ms.service: sharepoint-online
ms.subservice: lists
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.collection:
- M365-collaboration
description: Add and remove custom templates and change who has permission to access them.
locale: en-us
document_id: 6665386e-1ad4-e9d3-565b-4b3cb3c3ea99
document_version_independent_id: 870237f7-66ec-270e-1372-c993e8dedbe9
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/lists-custom-template.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: lists-custom-template
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/lists-custom-template.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: dd16bda4-d8bb-c6e6-fad6-b0b1303c9f96
---

# Custom list templates - SharePoint in Microsoft 365 | Microsoft Learn

As a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) and [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365, you can provide custom list templates for users in your organization. When users create new lists, they can select from these templates alongside the built-in templates from Microsoft. This feature enables your organization to create repeatable list solutions (in SharePoint, Teams, and within the Lists app itself).

You can create and manage custom list templates using Microsoft PowerShell:

1. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    Note

    If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell."
2. Connect to SharePoint as a [Global Administrator or SharePoint Administrator](sharepoint-admin-role) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

## Add a custom template

Follow these steps to create a custom list template.

1. Run the following command to extract the site script output from an existing list and write it to a variable:

    ```PowerShell
    $extracted = Get-SPOSiteScriptFromList -ListUrl "https://contoso.sharepoint.com/sites/strategy/customer-contacts" 
    ```
2. Reference the variable in the following command to upload a site script that can be used with a list design.

    ```PowerShell
    Add-SPOSiteScript 
      -Title "Contoso Customer Tracker" 
      -Description "This creates a customer contact list" 
      -Content $extracted 
    ```
3. Create your list design using the site script ID returned from the step above:

    ```PowerShell
    Add-SPOListDesign 
      -Title "Contoso customer tracking" 
      -Description "Tracks key customer data in a list" 
      -SiteScripts "<ID from previous step>" 
      -ListColor Orange 
      -ListIcon BullseyeTarget 
      -Thumbnail "https://contoso.sharepoint.com/SiteAssets/site-thumbnail.png" 
    ```

When users in your organization create a list (in SharePoint, Teams, or the Lists app), they see the template on the "From your organization" tab.

![The &quot;Contoso customer tracking&quot; template on the &quot;From your organization&quot; tab of the Create a list dialog box.](sharepointonline/media/contoso-customer-tracking.png)

Note

List templates can't be updated after you add them. Instead, remove the existing template and add the updated version.

## Scope the permissions to a custom template

By default, the custom list template is available to everyone in your organization. If you want, you can limit access to specific users or a security group. The following example shows how to grant an individual user view rights to a template.

```PowerShell
Grant-SPOSiteDesignRights 
  -Identity <List design ID to apply rights to> 
  -Principals "nestorw@contoso.onmicrosoft.com" 
  -Rights View 
```

## Get templates

The following example retrieves all custom list templates.

```PowerShell
Get-SPOListDesign <List design ID> 
```

## Remove a custom template

The following example shows how to remove a custom list template so that it's no longer available to users when they create lists.

```PowerShell
Remove-SPOListDesign <List design ID> 
```

You can also remove the associated site scripts that the list design is referencing using:

```PowerShell
Remove-SPOSiteScript <Site script ID> 
```