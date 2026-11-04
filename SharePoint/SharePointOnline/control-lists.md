---
layout: Conceptual
title: Control Microsoft Lists - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/control-lists
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-04-22T00:00:00.0000000Z
ms.reviewer: hasaladi
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.collection:
- M365-collaboration
description: Control settings in the Lists app.
locale: en-us
document_id: cf2d4570-0024-e5c0-035a-8827759aeabc
document_version_independent_id: 42e2105b-5ede-3d22-139d-96cc61cf4ec5
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/control-lists.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: control-lists
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/control-lists.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 473e532e-9ed6-cd76-ee9e-198e1e2807cc
---

# Control Microsoft Lists - SharePoint in Microsoft 365 | Microsoft Learn

As at least a [SharePoint Administrator](sharepoint-admin-role) in Microsoft 365, you can control settings for Microsoft Lists. You can:

- Disable the creation of personal lists (prevent users from saving new lists to "My lists").
- Disable built-in list templates that aren't relevant for your organization.

You control both of these settings by using Microsoft PowerShell.

## Disable creation of personal lists

If you change this setting, when users create a list, they must select a SharePoint site for saving the list. The "Save to" setting doesn't include the "My lists" option.

| Default | Personal list creation disabled |
| --- | --- |
| ![The Save to setting includes the My lists option](sharepointonline/media/save-my-lists.png) | ![The Save to setting requires users to select a site](sharepointonline/media/save-list-site.png) |

1. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    Note

    If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell."
2. Connect to SharePoint as at least a [SharePoint Administrator](sharepoint-admin-role) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
3. Run the following command:

    ```PowerShell
    Set-SPOTenant -DisablePersonalListCreation $true
    ```

To re-enable the creation of personal lists, set the parameter to `$false`.

## Disable built-in list templates

Disabling these templates removes them from all places users create lists (the Lists app, Microsoft Teams, and SharePoint sites).

| Default | Built-in list templates disabled |
| --- | --- |
| ![All built-in templates are available to users](sharepointonline/media/list-templates-all.png) | Some templates disabled![Some templates are still available to users](sharepointonline/media/list-templates-some.png) All templates disabled![Users see a message that templates have been turned off by the admin](sharepointonline/media/list-templates-none.png) |

1. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    Note

    If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell."
2. Connect to SharePoint as at least a [SharePoint Administrator](sharepoint-admin-role) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
3. Run the following command:

    ```PowerShell
    Set-SPOTenant -DisableModernListTemplateIds '<template ID>'
    ```

Where the template ID is:

- Issue tracker: 'C147E310-FFB3-0CDF-B9A3-F427EE0FF1CE'
- Employee onboarding: 'D4C4DAA7-1A90-00C6-8D20-242ACB0FF1CE'
- Event itinerary: '3465A758-99E6-048B-AB94-7E24CA0FF1CE'
- Asset manager: 'D2EDA86E-6F3C-0700-BE3B-A408F10FF1CE'
- Recruitment tracker: '3A7C53BE-A128-0FF9-9F97-7B6F700FF1CE'
- Travel requests: 'C51CF376-87CF-0E8F-97FF-546BC60FF1CE'
- Work progress tracker: 'B117A022-9F8B-002D-BDA8-FA266F0FF1CE'
- Content scheduler: '9A429811-2AB5-07BC-B5A0-2DE9590FF1CE'
- Incidents: 'E3BEEF0B-B3B5-0698-ABB2-6A8E910FF1CE'
- Patient care coordination: '0134C13D-E537-065B-97D1-6BC46D0FF1CE'
- Loans: '7C920B56-2D7A-02DA-94B2-57B46E0FF1CE'
- Gift ideas: '008F8143-9644-0238-B4B5-C03E4F0FF1CE'
- Recipe tracker: 'A1755E7D-8E3A-4141-89FC-6C77EB0FF1CE'
- Expense tracker: '96D6DBE5-D7C3-030A-867A-0B72EB0FF1CE'
- Travel requests with approvals: '4EB20749-6360-417C-83DD-06135C0FF1CE'
- Content scheduler with approvals: 'C381BD64-C1A1-4D9E-BE9C-0571900FF1CE'
- Playlist: '3A867B4A-7429-0E1A-B02E-BF4B240FF1CE'
- Resume repository: 'F6AEF3EE-EC97-433C-A662-E9170B0FF1CE'

To re-enable a built-in template, use the parameter `EnableModernListTemplateIds`.

## Disable extra features on a built-in template

Some built-in list templates include extra features such as automations and custom formatting. If you wish to keep only the base schema of a built-in list template but not the rest of its features included in that template:

1. Create a list from the built-in list template.
2. [Create a custom list template](lists-custom-template) based off of that list. The custom list template doesn't include any extra features by default.
3. Disable the original built-in list template.

    Note

    Users in your organization see the custom list template on the **From your organization** tab rather than on the **From Microsoft** tab.