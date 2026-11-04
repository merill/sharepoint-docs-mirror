---
layout: Conceptual
title: Manage result sources - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/manage-result-sources
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
audience: End User
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: platform
ms.collection: M365-collaboration
ms.localizationpriority: medium
ms.custom: admindeeplinkSPO
search.appverid:
- SPO160
- MET150
ms.assetid: fd8d6ac6-c5d0-454d-80a9-51580902b25d
description: Result sources limit searches to certain content or to a subset of search results. You can create your own result sources, or change the predefined result sources.
locale: en-us
document_id: 4072d3b5-45f9-746a-2954-64006add2181
document_version_independent_id: 66f9429e-6fd5-500b-048f-add3fdb61b5f
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/manage-result-sources.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-result-sources
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/manage-result-sources.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: f8c3cb26-483c-c421-9fa2-446c1d24451e
---

# Manage result sources - SharePoint in Microsoft 365 | Microsoft Learn

Result sources limit searches to certain content or to a subset of search results. You can also use result sources to send queries to external providers such as Bing.

A [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) can manage result sources for all site collections and sites in the tenant. A site collection administrator or a site owner can manage result sources for a site collection or a site, respectively.

SharePoint has both a classic and a modern search experience. The modern search experience gets results from the default result source. If you change the default result source, this impacts both the classic and modern search experiences. [Learn more about the differences between the classic and modern search experiences in SharePoint](differences-classic-modern-search).

For the classic search experience, you can create your own result sources, or use the predefined result sources. After you create a result source, you configure Search Web Parts and query-rule actions to use it.

## Create a new result source

1. Go to the **Manage Result Sources** page for the tenant, for a site collection, or a site:

    - For a tenant, in the new SharePoint admin center, select [**More features**](https://go.microsoft.com/fwlink/?linkid=2185077). Under **Search**, select **Open**, and then on the search administration page, select **Manage Result Sources**.
    - For a site collection, in your site collection, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and then select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**. Under **Site Collection Administration**, select **Search Result Sources**.
    - For a site, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and then select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**. Under **Search**, select **Result Sources**.
2. On the **Manage Result Sources** page, select **New Result Source**.
3. In the **General Information** section, type a name and a description for the new result source.
4. In the **Protocol** section, select one of the following protocols for retrieving search results:

    - **Local SharePoint**, the default protocol, provides results from the search index of this tenant (Search Service).
    - **Remote SharePoint** (retired) provides results from the index of a search service in a different farm (external source). In the **Remote Service URL** box, type the address of the root site collection of the remote SharePoint farm.
    - **OpenSearch 1.0/1.1** (retired) provides results from a search engine that uses the OpenSearch 1.0/1.1 protocol.
    - **Exchange** provides results from Microsoft Exchange Server. Select **Use AutoDiscover** to have the search system find an Exchange Server endpoint automatically, or type the URL of the Exchange web service to retrieve results from — for example, `https://contoso.com/ews/exchange.asmx`

Important

As of September 2024, for SharePoint Online Microsoft 365 Result Sources, the OpenSearch and Remote SharePoint protocol options have been retired and will soon be removed from the Result Source configuration UI. Any SharePoint Online Result Source currently configured to use these options will have zero results returned.

Note

The Exchange Web Services Managed API must be installed on the computer where the search service is running.

1. If you choose **Local SharePoint** or **Remote SharePoint** for protocol, choose a **Type**:

    - **SharePoint Search Results** to search the whole index.
    - **People Search Results** to search in people profiles and enable query processing that is specific to people search, such as phonetic name matching or nickname matching.
2. In the **Query Transform** section, you can change incoming queries to use a new query text instead. Choose one of these options:

    - Leave the default query transform ( **searchTerms**) as is. The query will be unchanged since the previous transform.
    - Type a different query transform in the box. See [Understanding query transforms](https://support.office.com/article/b31631a5-0c1f-436e-8061-fd807bb96ae1).
    - Build your own query. Select **Launch Query Builder** and build your query by specifying filters on the **BASICS**, sorting on the **SORTING** tab, and then testing the query on the **TEST** tab. Each of these tabs are described in the following sections.
3. In the **Credentials Information** section, choose an authentication type for users to connect to the result source.
4. Select **Save**.

### The BASICS tab

| Choose this option | To do this |
| --- | --- |
| Keyword filter | Use keyword filters to add predefined query variables to the query transform. Select query variables from the list, and add them to the query by clicking **Add keyword filter**. |
| Property filter | Use property filters to query the content of managed properties that are set to **queryable** in the search schema.  Select managed properties from the **Property filter** list. Click **Add property filter** to add the filter to the query. **NOTE**: Custom managed properties are not shown in the **Property filter** list. To add a custom managed property to your query, in the **Query text** box, enter the name of your custom managed property followed by the query condition, for example *MyCustomColorProperty:Green* |

### The SORTING tab

| Choose this option | To do this |
| --- | --- |
| Sort results | Define sorting for results. The **Sort by** list contains managed properties that are set as sortable in the search schema.  Select a property to sort by, and then select **Descending** or **Ascending**. To sort by relevance, select **Rank**.  Click **Add sort level** if you want to specify more levels of sorting. |
| Dynamic ordering | Click **Add dynamic ordering rule** to specify additional ranking by adding rules that change the order of results within the result block when certain conditions are met. You can add conditions by choosing from the lists that appear. |

### The TEST tab

| Choose this option | To do this |
| --- | --- |
| Query text | See the final query text, which is based on the original query template, the applicable query rules, and the variable values. |
| Show more | Click the link to show more options. |
| Query template | See the query as it is defined in the **BASICS** tab or in the text box in the **Query transform** section on the Add Result Source page. |
| Query template variables | Test the query template by specifying values for the query variables. Click **Test query** to see the results. |

## Set a result source as default

The default result source is **Local SharePoint Results**, but you can choose to set a different one as the default. By doing this, it will be easier to edit the query in Search Web Parts. For example, when you add a Content Search Web Part to a page, the Web Part automatically uses the default result source.

1. Go to the **Manage Result Sources** page for the tenant, for a site collection, or a site:

    - For a **tenant**, in the new SharePoint admin center, select [**More features**](https://go.microsoft.com/fwlink/?linkid=2185077). Under **Search**, select **Open**, and then on the search administration page, select **Manage Result Sources**.
    - For a site collection, in your site collection, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and then select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**. Under **Site Collection Administration**, select **Search Result Sources**.
    - For a site, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and then select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**. Under **Search**, select **Result Sources**.
2. On the **Manage Result Sources** page, point to the result source that you want to set as the default, select the arrow that appears, and then select **Set as Default**.

## Delete a result source

A result source might be no longer needed. The following procedure provides the steps for removing a result source.

1. Go to the **Manage Result Sources** page for the tenant, for a site collection, or a site:

    - For a **tenant**, in the new SharePoint admin center, select [**More features**](https://go.microsoft.com/fwlink/?linkid=2185077). Under **Search**, select **Open**, and then on the search administration page, select **Manage Result Sources**.
    - For a site collection, in your site collection, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and then select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**. Under **Site Collection Administration**, select **Search Result Sources**.
    - For a site, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and then select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**. Under **Search**, select **Result Sources**.
2. On the **Manage Result Sources** page, point to the result source that you want to remove, select the arrow that appears, select **Delete**, and then select **Ok** in the confirmation dialog.