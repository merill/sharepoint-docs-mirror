---
layout: Conceptual
title: Enable content on a site to be searchable - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/make-site-content-searchable
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
ms.date: 2026-06-25T00:00:00.0000000Z
audience: End User
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: sites-pages
ms.collection: M365-collaboration
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.assetid: 2a420d01-4706-4d23-980e-c4c877113670
description: Change search settings to control whether content on a site can appear in search results.
locale: en-us
document_id: 5faf2831-9899-0574-2de8-bfece943e3e6
document_version_independent_id: 2884bfdb-c023-8a53-2380-628c3ae86086
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/make-site-content-searchable.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: make-site-content-searchable
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/make-site-content-searchable.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
platformId: ba1ed45e-2dd3-ca35-0792-673015bf2816
---

# Enable content on a site to be searchable - SharePoint in Microsoft 365 | Microsoft Learn

When users search on a site, results can come from many places such as columns, libraries, and pages. A site owner can change search settings to decide whether content is allowed to appear in search results. Permissions on content also affect whether users are allowed to see the content in search results. A good understanding of how permissions and search settings work can help you ensure that users can see the right documents and sites in the search results.

Note

Search results are always security trimmed, so users will only see content they have permission to see. The search settings only define what content is included in the search index.

There are specific scenarios where users have permissions to see the content but are still unable to find it in the search results. For more details, see [Search results don't appear for group owners after creating a new Office 365 group](/en-us/sharepoint/troubleshoot/search/search-results-dont-appear-for-group-owners).

## Plan to make your content available in search results

As a site owner, you can use settings to control whether content can appear in search results. Content is stored in many places including sites, lists, libraries, Web Parts, and columns. By default, most content contained in a site, list, library, Web Part page, or column will be crawled and added to the search index. What's in the search index decides what content can appear in search results both in the **classic** and **modern** search experiences. The permissions that are set on items, lists, libraries, sites, and so forth, also affect whether users can see the content in search results.

Site owners and site collection administrators can choose whether content can appear in search results. By default, the content of a site can appear in search results. If a site owner or site collection administrator specifies that the content from a particular site can't appear in search results, then the other search results settings such as those for lists, libraries, ASPX pages, and columns set on that site wouldn't have any effect.

Similarly, if a site owner or site collection administrator prevents list or library content from appearing in search results, then excluding columns wouldn't have any effect. It's important to know what settings are inherited from higher levels in order to plan search effectively.

## Understand search settings and permissions

One of the responsibilities of a site owner is to control who has access to content. You can give some people permission to read and change content, allow others to only read content, and prevent others from viewing content entirely. In order to accommodate this flexibility, you use permissions groups, which are assigned specific permission levels. To allow users access to the site or to content on that site, a site owner assigns users to one or more security groups. By using permissions settings in conjunction with search results settings, the site owner can manage whether users can see content in search results.

For example, let's say Joe is working on a Request for Proposal (RFP) in Microsoft Office Word and is collaborating with a team of 10 people. His team site has 50 users, all of whom are Site Members. Joe isn't ready for the whole team to view the RFP. Therefore, when he uploads it to the team site, he sets the permissions so that only the team of 10 can view and edit it. Until he grants all 50 people read permissions, only the 10 people who have permission to view the document will see it listed in search results.

Permissions can be applied to lists, sites, views, and Web Parts. Also, permissions can be dependent on other permissions. All of this can affect what the user sees in search results. Therefore, before adding any content to your site, you may want to familiarize yourself with SharePoint's permissions model, the permissions model of your site or organization, or to plan what the permissions model will be for your site.

See also: [Default SharePoint Groups in SharePoint](default-sharepoint-groups)

## Show content on a site in search results

As a site owner, you can choose whether the content on your site can appear in search results. By default, all site content can appear in search results. The person who's viewing search results must have permission to view the content.

Note

To change this setting, you must have the Manage Permissions permission level. This permission level is included in the " *Site Name* " Owner group.

1. On the site, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and then select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**.
2. Under **Search**, click **Search and offline availability**.
3. In the **Indexing Site Content** section, under **Allow this site to appear in Search results**, select **Yes** to allow the content of the site to appear in search results.

To prevent the content from appearing in search results, select **No**.

## Show content from lists or libraries in search results

As a site owner, you can decide whether items in lists and libraries on your site are included in search results. By default every list and library is set to include all items in search results.

Note

To change this setting, you must have the Manage Lists permission level. The Designer and " *Site Name* " Owner groups contain this permission level. When you do not have Manage Lists permissions, the menus described in this procedure aren't available.

1. On the site, find and click the list or library you want to customize.
2. Select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and then select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**.
3. Under **Site Administration**, click **Site Libraries and lists**.
4. Click an item from the list, for example, **Customize "Shared Documents."**
5. On the List Settings page, under **General Settings**, click **Advanced settings**.
6. In the **Search** section, under **Allow items from this document library to appear in search results**, select **Yes** to include all of the items in the list or library in search result.

To prevent items from the list or library to appear in search results, select **No**.

## Show contents of ASPX pages in search results

You can control whether the content of ASPX pages is included in search results. When you create a site, many content pages are created automatically. For example, default.aspx, allitems.aspx for your Web Part gallery, and several others are automatically created pages. You can also create custom ASPX pages.

By default, when a Web Part displayed on an ASPX page uses information from a list or library that contains restricted permissions, also known as fine-grained permissions, none of the content in any of the ASPX pages on the site is included in search results. This prevents non-authorized users from viewing content.

For example, let's say five documents are displayed in a Shared Documents Web Part on a team site with 50 members. One of the documents has restricted permissions; only a few people are allowed to see it. Content is automatically hidden from that site in search results so that the content from that document does not appear when users search. This prevents the content of the ASPX page from unintentionally being exposed to people who are not supposed to see it.

You have the option of ignoring this setting to display all content in search results regardless of permissions. In this case, all content can appear in the search results, but unauthorized users will not be able to access the actual documents. Another option is to not include any ASPX content in search results, regardless of permissions.

Note

To change this setting, you must have the Manage Permissions permission level. This permission level is included in the " *Site Name* " Owner group.

1. On the site, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and then select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**.
2. Under **Search**, click **Search and offline availability**.
3. In the **Indexing ASPX Page Content** section, select one of the following options:

| **Option** | **Description** |
| --- | --- |
| Do not index Web Parts if this site contains fine-grained permissions | When permissions of the ASPX page are different from the parent site, no content on the site appears in search results. |
| Always index all Web Parts on this site | Show content of all ASPX pages on the site in search results regardless of permissions. |
| Never index any Web Parts on this site | Hide content of all ASPX pages on the site from search results regardless of permissions. |

## Exclude content in columns from search results

As a site owner you can control whether the content in specific columns in lists or libraries appears in search results. By default, all content is included in search results. This setting is useful when you want to prevent sensitive data from appearing in search results.

Note

To change this setting, you must have the Manage Permissions permission level. This permission level is included in the *"Site Name"* Owner group.

1. On the site that contains the list or library, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and then select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**.
2. Under **Search**, click **Searchable columns**.

    The option is only visible for sites with the classic [publishing feature](publishing-sites-classic-to-modern-experience) enabled. If the option is not visible navigate directly to `<Site URL>>/_layouts/15/NoCrawlSettings.aspx`.
3. In the **Excluded Columns from Search Indexing** section, under **Excluded**, check the box next to the Column Name for the column you want to exclude in search results.

Note

Columns that appear are those that belong to the current site.

## Crawl and re-index a site

When people search for content on your SharePoint sites, what's in your search index decides what they'll find. The search index contains information from all documents and pages on your site. In SharePoint, content is automatically crawled based on a defined crawl schedule. The crawler picks up content that has changed since the last crawl and updates the index.

For cases in which the Search schema has changed where a managed property has been added/removed/changed, you will want to specifically request a full re-indexing of a site. See [Manually request crawling and re-indexing of a site](crawl-site-content) for more information.