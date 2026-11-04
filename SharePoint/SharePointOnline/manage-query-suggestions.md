---
layout: Conceptual
title: Customize query suggestions in SharePoint search - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/manage-query-suggestions
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
f1.keywords: NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.collection: M365-collaboration
ms.localizationpriority: medium
ms.custom: admindeeplinkSPO
search.appverid:
- SPO160
- MET150
ms.assetid: 9ef0f859-3b92-41e9-b393-cb43d6094c7b
description: Learn how to add phrases that you want the system to suggest to users as they search for an item, and how to add phrases that you don't want the system to suggest to users. Also, learn how to turn this feature on or off.
locale: en-us
document_id: 393443ee-bbb2-09d5-c16c-2522ca855c57
document_version_independent_id: 44ae935c-f080-d1ce-4c2c-463121fb7911
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/manage-query-suggestions.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-query-suggestions
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/manage-query-suggestions.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 73cc8c75-cdd4-c96e-8706-a63b1eef9f04
---

# Customize query suggestions in SharePoint search - SharePoint in Microsoft 365 | Microsoft Learn

Query spelling suggestions are words that appear below the search box as a user types a query. SharePoint automatically creates query suggestions from frequently entered queries that resulted in a click on a search result. For example, if you've repeatedly entered the query word "coffee" and then clicked a search result each time, "coffee" automatically becomes a query suggestion.

Automatic query suggestions are generated periodically for each result source and each site collection, so the query suggestions can be different for different result sources and site collections.

For example, in the following screenshot, "contoso" is automatically suggested. ![Screenshot of Query Suggestion.](sharepointonline/media/query-suggestion.png)

SharePoint has both a classic and a modern search experience, [learn about the differences between the classic and modern search experiences in SharePoint](differences-classic-modern-search). The modern search experience uses the same default result source as the classic search experience. Automatic query suggestions for the default result source appear only in the classic search experience.

As an admin you can manually create your own lists of queries that always shall be suggested or phrases that never shall be suggested, and import them to SharePoint.

- Your list of queries that shall always be suggested only applies to modern search and only in tenant-wide scope.
- Your list of phrases that never shall appear apply to both classic and modern search, to all result sources and all site collections.

To create query suggestions for multiple languages, you'll need to create a separate file for each language. The language determines how the query suggestions are processed internally in the search system. All manual query suggestions are always displayed for **all** languages. Add each phrase as a separate line in the text file that you create and save the file in UTF-8 encoding.

Query suggestions are turned on by default. To turn them off, go to **Search Suggestions**, and clear **Show search suggestions**.

## To create query suggestions in SharePoint search

1. Go to [**More features** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185077), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.
2. Under **Search**, select **Open**.
3. On the search administration page, select **Query Suggestion Settings**.
4. Open a text editor of your choice, and enter a list of terms that you want the system to always suggest to users. Only add one term per line to the text file, and don't mix languages in the text file.
5. Save the text file to a location that's accessible from SharePoint.
6. To import a list of query suggestions to SharePoint search, go to **Always suggest phrases** &gt; **Import from text file**. When you import query suggestions, any existing ones will be overwritten.
7. Browse to the file that you want to import.
8. Go to **Language for suggestion phrases**, and select the processing language of your query suggestions. It should match the language of the terms in the text file.
9. Select **Save Settings**.

### Related tasks

You can edit a list of query suggestions that you've manually created. To edit a list that you've already imported into SharePoint, choose **Export to text file**, update the text file with your changes, and then re-import it. After you've uploaded your query suggestions file, it might take up to a week until your query suggestions are displayed. You can check that they're working properly by entering a phrase from your list of query suggestions in the search box. The query suggestion should appear below the search box.

To get rid of a list of query terms, you must overwrite it. Do this by importing an empty text file.

To prevent terms from appearing in the search box, create a text file with the query terms that you never want users to see below the search box, and then import it to **Never suggest phrases**.