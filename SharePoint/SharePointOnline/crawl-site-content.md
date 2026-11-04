---
layout: Conceptual
title: Manually request crawling and reindexing of a site, a library or a list - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/crawl-site-content
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
ms.date: 2025-04-15T00:00:00.0000000Z
audience: End User
f1.keywords:
- NOCSH
ms.topic: article
ms.service: sharepoint-online
ms.subservice: admin
ms.collection: M365-collaboration
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.assetid: 9afa977d-39de-4321-b4ca-8c7c7e6d264e
description: Manually request crawling and full reindexing of a site by clicking the Reindex site button. All of the site content is marked as changed and will be picked up during the next crawl and reindexed.
locale: en-us
document_id: d18cdf74-1e86-aa79-3282-69ffc9cdd282
document_version_independent_id: 39cea6c4-be38-1908-7815-aa9ee552cedf
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/crawl-site-content.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: crawl-site-content
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/crawl-site-content.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: ba35e581-3e67-d84c-b401-55d2524ba609
---

# Manually request crawling and reindexing of a site, a library or a list - SharePoint in Microsoft 365 | Microsoft Learn

In SharePoint, content is automatically crawled based on a defined crawl schedule. The crawler picks up content that has changed since the last crawl and updates the index. You'll want to manually request crawling and full reindexing of a site, a document library, or a list after a schema change has occurred.

Caution

Reindexing a site can cause a massive load on the search system. Don't reindex your site unless you've made changes that require all items to be reindexed.

## Reindex after changing managed properties

When people search for content on your SharePoint sites, what's in your search index decides what they find. The search index contains information from all documents and pages on your site.

The search index is built up by crawling the content on your SharePoint site. The crawler picks up content and metadata from the documents in the form of [crawled properties](/en-us/sharepoint/manage-search-schema#about-the-search-schema). To get the content and metadata from the documents into the search index, the crawled properties must be mapped to managed properties. Only managed properties are kept in the index. This means that users can only search on managed properties.

When you change a managed property, or when you change the mapping of crawled and managed properties, the site must be recrawled before your changes are reflected in the search index. Because your changes are made in the search schema, and not to the actual site, the crawler won't automatically reindex the site. To make sure that your changes are crawled and fully reindexed, you must request a reindexing of the site. The site content is recrawled so that you can start using the managed properties in queries, query rules and display templates.

You can also choose to only reindex a document library or a list. When you've changed a managed property that's used in a library or list, or changed the mapping of crawled and managed properties, you can specifically request a reindexing of that library or list only. All of the content in that library or list is marked as changed, and the content is picked up during the next scheduled crawl and reindexed.

Learn more about search and crawled and managed properties in [Manage the search schema in SharePoint](manage-search-schema).

See also: [Enable content on a site to be searchable](make-site-content-searchable)

## Reindex a site

1. On the site, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and then select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**.
2. Under **Search**, select **Search and offline availability**.
3. In the **Reindex site** section, select **Reindex site**.
4. A warning appears, check the box before **Please check this box to acknowledge and agree to the statement above.** Select **Reindex site** again to confirm. The content is reindexed during the next scheduled crawl.

## Reindex a document library or a list

1. On the site, go to the list or library that you want to reindex.
2. In the upper right corner, select **Settings**, and then choose **Library Settings** or **List Settings**.
3. On the Settings page, under **General Settings**, choose **Advanced settings**. If you don't see the **Settings** page, you may need to choose **More library settings** or **More List settings**.
4. Scroll down to **Reindex Document Library** or **Reindex List**, and select the button. A warning appears. Select the button again to confirm. The content is reindexed during the next scheduled crawl.