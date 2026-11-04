---
layout: Conceptual
title: Overview of crawled and managed properties in SharePoint Online - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/crawled-and-managed-properties-overview
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: misvenso
ms.author: ruihu
author: maggierui
manager: jtremper
ms.date: 2023-03-10T00:00:00.0000000Z
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: concept-article
ms.service: sharepoint-online
ms.subservice: platform
ms.localizationpriority: medium
description: Learn about the default managed properties for SharePoint Online, their settings, and the default mapping between crawled and managed properties.
locale: en-us
document_id: adb6ad45-00c5-d3bc-8db1-d707f2fa7f4e
document_version_independent_id: b8cabb67-95e9-fe03-f8ab-cc760a0a5014
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/crawled-and-managed-properties-overview.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: crawled-and-managed-properties-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/crawled-and-managed-properties-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
- https://authoring-docs-microsoft.poolparty.biz/devrel/dc29fde7-b949-4135-9273-ad8e4a53d516
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
- https://authoring-docs-microsoft.poolparty.biz/devrel/25d6050c-71f5-4b48-8bc7-575debd6530a
platformId: afdc164e-1716-05c7-b692-1b677f41e257
---

# Overview of crawled and managed properties in SharePoint Online - SharePoint in Microsoft 365 | Microsoft Learn

A *crawled property* is content and metadata that is extracted from an item, such as a document or a URL, during a crawl. A crawled property can be an author, title, or subject. To include the content and metadata of crawled properties in the search index, you map crawled properties to managed properties. Managed properties can have a large number of settings, or attributes. These attributes determine how the contents are shown in search results. The search schema contains the attributes on managed properties and the mapping between crawled properties and managed properties. For more information, see [Overview of the search schema in SharePoint Server](search/search-schema-overview) and [Manage the search schema in SharePoint Online](manage-search-schema).

## Managed properties overview

For a list of default managed properties and their attributes inherited from SharePoint Server see [Overview of crawled and managed properties in SharePoint Server](technical-reference/crawled-and-managed-properties-overview).

The following table lists the default managed properties and their attributes specific to SharePoint Online. For each managed property that by default is mapped to one or several crawled properties, these crawled properties are listed in the **Mapped Crawled Properties** column.

### Managed properties for SharePoint in Microsoft 365.

| Property name | Type | Multi-valued | Queryable | Searchable | Retrievable | Refinable | Sortable | Mapped crawled properties | Comment |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| DepartmentId | Text | No | Yes | No | Yes | Yes | No | ows\_DepartmentId | Site ID of the hub of the immediate hub. Applies to all items in the hub/associated sites. |
| RelatedHubSites | Text | Yes | Yes | No | Yes | No | No | ows\_RelatedHubSites | Site IDs of associated hubs including hub hierarchies. Can be used instead of DepartmentId for most scenarios. Applies to all items in the hub/associated sites. |
| IsHubSite | Yes/No | No | Yes | No | Yes | No | No | ows\_IsHubSite | Applies to the site result of a hub (contentclass=STS\_Site) |
| ModifierAADIDs | Text | Yes | Yes | No | Yes | Yes | Yes |  | Semi-colon separated list of AADIDs for modifiers of a file or page ordered in date descending order. (\*) |
| ModifierDates | Date and Time | Yes | No | No | Yes | No | No |  | Semi-colon separated list of modification dates for modifiers of a file or page ordered in date descending order. (\*) |
| ModifierNames | Text | Yes | Yes | No | Yes | No | No |  | Semi-colon separated list of the names for modifiers of a file or page ordered in date descending order. (\*) |
| ModifierUPNs | Text | Yes | No | No | Yes | No | No |  | Semi-colon separated list of UPNs for modifiers of a file or page ordered in date descending order. (\*) |
| ChapterTitle | Text | Yes | Yes | Yes | Yes | No | No | ChapterTitle | Semi-colon separated list of [auto-generated chapters on Teams meeting videos](https://support.microsoft.com/en-us/office/auto-generated-chapters-on-teams-meeting-videos-7af781d3-ed33-4aae-bb66-0abd4c6c4c98). (\*) |
| ChapterOffset | Text | Yes | No | No | Yes | No | No | ChapterOffset | Semi-colon separated list of time codes matching the chapter titles for [auto-generated chapters on Teams meeting videos](https://support.microsoft.com/office/auto-generated-chapters-on-teams-meeting-videos-7af781d3-ed33-4aae-bb66-0abd4c6c4c98). (\*) |

\* Property is not guaranteed to contain data.

See [Manage search schema - Default unused managed properties](manage-search-schema#default-unused-managed-properties) for a list of the reusable managed properties available in SharePoint Online.