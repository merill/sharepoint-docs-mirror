---
layout: Conceptual
title: Manage query rules - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/manage-query-rules
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-06-25T00:00:00.0000000Z
ms.reviewer: 
ms.author: deniseb
author: denisebmsft
manager: dansimp
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
ms.assetid: 53556bb4-3625-490b-aa89-1223e3d4ce3f
ms.collection:
- M365-collaboration
description: Improve search results by creating and managing query rules. Query rules help searches respond to the intent of users.
locale: en-us
document_id: 7f082d30-62d1-e099-8307-5ab5c15d410f
document_version_independent_id: 24906b5f-8745-96f9-0f79-3dc67f1e6720
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/manage-query-rules.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-query-rules
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/manage-query-rules.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
platformId: f9a92a66-24cc-29fc-55e5-bc145e682d6e
---

# Manage query rules - SharePoint in Microsoft 365 | Microsoft Learn

As a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [other administrator](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365, you can improve search results in the classic search experience by creating and managing query rules. Query rules help searches respond to the intent of users.

In a query rule, you specify conditions and associated actions. When a query meets the conditions in a query rule, the search system performs the actions specified in the rule to improve the relevance of the search results. This improvement could be by narrowing results or changing the order in which results are displayed. When the query rule condition is met, an associated action could be to show a specific item at the top of the search results. For example, say you have an intranet site where all company events are maintained in a library, and you want to promote a first-aid seminar. To do this, create a query rule that boosts the first-aid seminar to the top of the search results when someone searches for "seminar" or "event."

A query rule can specify the following three types of actions:

- Promote a search result to appear above ranked results. For example, for the query "sick leave", a query rule could specify a particular result, such as a link to a site that has a statement of company policy regarding time off work.
- Add one or more groups of search results, called result blocks. For example, for a query that contains "Fabrikam sales report", a query rule might recognize "Fabrikam" as a customer, and then display a result block with pertinent results about Fabrikam from your customer relationship management (CRM) system.
- Change the ranking of search results. For example, for a query that contains "download toolbox", a query rule could recognize the word "download" as an action term and boost search results that point to a particular download site on your intranet.

You can create query rules at different levels: for the whole tenant, for a site collection, or for a site. When you create query rules at tenant level, all site collections can use the query rules. When you create query rules at site collection level, all sites in the site collection can use the rules. When you create query rules at site level, only that site can use the rules.

You can configure query rules for one or more result sources, and you can specify a time period for when the query rule is active.

SharePoint has both a classic and a modern search experience. Only query rules that return promoted results can affect the modern search experience. Query rules that do query rewrites aren't supported for modern experiences. Users might see such promoted results on the **All** tab on the search results page when they search across all of SharePoint. [Learn more about the differences between the classic and modern search experiences in SharePoint](differences-classic-modern-search).

Important

In December 2021, Microsoft deprecated query rules with promoted results for organization-scoped queries in favor of [Bookmark and Q&A answers](/en-us/microsoftsearch/manage-bookmarks) in modern search experiences. Examples of organization-scoped queries are SharePoint Home and Office.com. 

Promoted results continue to work for all classic search experiences and for sites and hub sites with modern search experiences. Promoted results also continue to work for environments where Bookmark and Q&A answers aren't available.

## Promote a search result

You can add several individual promoted results. When there's more than one promoted result, you can specify the relative ranking.

1. Go to the **Manage Query Rules** page for the tenant, a site collection, or a site:

    - For a tenant, in the new SharePoint admin center, select **More features**. Under **Search**, select **Open**. On the search administration page, select **Manage Query Rules**.
    - For a site collection, in your site collection, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and then select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**. Under **Site Collection Administration**, select **Search Query Rules**.
    - For a site, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and then select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**. Under **Search**, select **Query Rules**.
2. On the **Manage Query Rules** page, in the **Select a Result Source** list, select a result source for the new query rule.
3. Select **New Query Rule**.
4. On the **Add Query Rule** page, in the **General Information** section, in the **Rule name** field, type the name for the query rule.
5. Select to expand the **Context** section.
6. In the **Context** section, do one of the following:

    - To apply the query rule to all result sources, select **All sources**.
    - To apply the query rule to one or more specific result sources, select **One of these sources**. By default, the result source that you specified earlier is selected. To add a result source to the query rule, select **Add Source**, select a result source in the dialog, and then select **Save**.
7. In the **Query Conditions** section, do one of the following:

    - Select one of the conditions listed in [Overview of conditions that make a query rule fire](manage-query-rules#BKMK_Conditions_that_fire_query_rule).

        Note

        The rule fires when any condition is true.

        To add more conditions, select **Add Alternate Condition**.
    - Select **Remove Condition** to configure this query rule to fire for every query that users type at the level at which you're creating the rule, and then go to the next step. For example, if you're creating this rule for a site collection, select **Remove Condition** if you want this rule to fire for every query that users type inside any search box in the site collection.
8. In the **Actions** section, specify the action to take when the query rule fires. Specify one of the following:

    - To promote individual results so they appear towards the top of search results, select **Add Promoted Result** (in SharePoint 2010 Products this option was called Best Bets). In the dialog, in the **Title** field, type the name that you want to give this promoted result. In the **URL** field, type the URL of the result that should be promoted. Select **Render the URL as a banner instead of as a hyperlink**. Select **Save**.

        You can add several individual promoted results. When there's more than one promoted result, specify the relative ranking.
    - To promote a group of search results, select **Add Result Block**. For more information, see [Create and display a result block](manage-query-rules#__toc343764779).
    - To change ranked search results, select **Change ranked results by changing the query**. For more information, see [Change ranked search results by changing the query](manage-query-rules#__toc343764780).
9. To make the query rule active during a particular time period, select **Publishing**, and then specify the period.
10. Select **Save**.

## Create and display a result block

A result block contains a small subset of results that are related to a query in a particular way. Like individual results, you can promote a result block or rank it with other search results.

When you configure a query condition for a result block, use *query variables*. Query variables are like placeholders for values that you don't yet know when you specify the query. However, when the query runs, this information is available and the system uses it to send the query to the index. For example, {User.Name} stands for the display name of the user who typed in the query. Another one is {searchBoxQuery}, which stands for the query a user typed in a search box. When you use the Query Builder to configure the query, a list of query variables is shown. (See step 3 in the procedure right below.)

1. In step 9 of the procedure [Create a query rule](manage-query-rules#__toc343764778), on the **Add Query Rule** page, in the **Actions** section, click **Add Result Block**.
2. Enter the title that appears in the result block in the **Title** field in the **Block Title** section.
3. Configure the query that gives results for the block. In the **Query** section, click **Launch Query Builder** and on the **BASICS** tab, complete the following steps:

    - Select which content to search by selecting a result source from the drop-down list in the **Select a query** section.
    - Specify your query. See [Query variables in SharePoint Server 2013](technical-reference/query-variables) for a list of available query variables. You can select predefined query variables from the **Keyword filter** drop-down list, and then add them to the Query text box by clicking **Add keyword filter**.
    - If relevant, use property filters to query the content of managed properties that are set to queryable in the search schema. You can select managed properties from the **Property filter** drop-down list. Select **Add property filter** to add the filter to the query.

    Note

    Custom managed properties don't appear in the **Property filter** list. To add a custom managed property to your query, in the **Query text** box, enter the name of your custom managed property followed by the query condition, for example *MyCustomColorProperty:Green*.
4. Specify how the search results within your result block should be sorted. Sorting of search results is case sensitive. On the **SORTING** tab, in the **Sort by** drop-down list, select a managed property, and then select **Descending** or **Ascending**. The list only contains managed properties that are set as sortable in the search schema. You can also sort by rank. To add more sorting levels, click **Add sort level**.
5. If you choose to sort by rank, you can optionally define rules for dynamically changing the ordering of results. In the **Dynamic ordering** section, define when to change ranking by selecting a condition from the drop-down list and then specifying whether to **promote** or **demote** the result. To add more rules, click **Add dynamic ordering rules**.
6. Preview the final query that the Content Search Web Part runs, on the **TEST** tab. The preview is based on the original query template where dynamic variables are substituted with current values. Other changes to the query might be made as part of query rules. Click **Show more** to display additional information.

    - The **Query text** shows the final query that the Content Search Web Part runs. It's based on the original query template where dynamic variables are replaced with current values. You might end up making other changes to the query as part of query rules.
    - The **Query template** box shows the content of the query template that is applied to the query.
    - The **Query template variables** section shows the query variables that are applied to the query, and the values of the variables that apply to the current page. You can type other values to test the effect they have on the query. Click the **Test Query** button to preview the search results.
7. Click **OK** to close the **build your query** dialog.
8. Define which result source this result block should apply to. Use the **Search this Source** drop-down list in the **Query** section.
9. In the **Items** drop-down list, select how many results to show in the result block.
10. Expand the **Settings** section.

    The result block only displays the number of search results that you specified in the previous step. However, you can add a **Show more** link at the bottom of the result block that shows all search results for the result block.

    To add a **Show more** link, select **"More" link goes to the following URL**, and then type a URL. You can use query variables in this URL, like this example: `http://www.\<site\>/search/results.aspx?k={subjectTerms}`.
11. Select **OK**.

## Change ranked search results by changing the query

The ranking model calculates a ranking order of search results. You can change this ranking by promoting or demoting items within the search results. For example, for a query that contains "download toolbox", you can create a query rule that recognizes the word "download" as an action term. Once you add this rule, you can change the ranked search results to promote the URL of a specific download site on your intranet.

You can also dynamically change the sorting order of the search results, based on several variables such as file name extension or specific keywords. When you change ranked search results by changing the query, you see that your results are security trimmed and refinable. Moreover, the search results don't show up if the document is no longer there.

1. In step 9 of the procedure [Create a query rule](manage-query-rules#__toc343764778), on the **Add Query Rule** page, in the **Actions** section, select **Change ranked results by changing the query**. The **build your query** dialog appears.
2. On the **BASICS** tab, complete the following steps:

    - Select which content to search by selecting a result source from the drop-down list in the **Select a query** section.
    - Specify your query. See [Query variables in SharePoint Server 2013](technical-reference/query-variables) for a list of available query variables. You can select predefined query variables from the **Keyword filter** drop-down list, and then add them to the Query text box by clicking **Add keyword filter**.
    - If relevant, use property filters to query the content of managed properties that are set to queryable in the search schema. You can select managed properties from the **Property filter** drop-down list. Select **Add property filter** to add the filter to the query.
3. Specify how the search results within your result block should be sorted. Sorting of search results is case sensitive. On the **SORTING** tab, in the **Sort by** drop-down list, select a managed property, and then select **Descending** or **Ascending**. The list only contains managed properties that are set as sortable in the search schema. You can also sort by rank. To add more sorting levels, select **Add sort level**.
4. If you choose to sort by rank, you can optionally define rules for dynamically changing the ordering of results. In the **Dynamic ordering** section, define when to change ranking by selecting a condition from the drop-down list and then specifying whether to **promote** or **demote** the result. To add more rules, select **Add dynamic ordering rules**.
5. Preview the final query that the Content Search Web Part runs, on the **TEST** tab. The preview is based on the original query template where dynamic variables are substituted with current values. Other changes to the query might be made as part of query rules. Select **Show more** to display additional information.

    - The **Query text** shows the final query that the Content Search Web Part runs. It's based on the original query template where dynamic variables are replaced with current values. You might end up making other changes to the query as part of query rules.
    - The **Query template** box shows the content of the query template that is applied to the query.
    - The **Query template variables** section shows the query variables that are applied to the query, and the values of the variables that apply to the current page. You can type other values to test the effect they have on the query. Click the **Test Query** button to preview the search results.
6. Select **OK** to close the **Build Your Query** dialog.
7. Select **Save**.

## Make a query rule inactive on a site

Site collections and sites inherit query rules that you create at the tenant level. Similarly, sites in the site collection inherit query rules that you create at the site collection level. If you don't want a query rule to apply to a site that inherits it, you can make the query rule inactive for the site.

1. On your site, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and then select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**.
2. On the **Site Settings** page, in the **Search** section, select **Query Rules**.
3. On the **Manage Query Rules** page, on the **Select a Result Source** menu, select the result source that contains the query rule that you want to make inactive.
4. In the **Name** column, point to the query rule that you want to make inactive, select the arrow that appears, and then select **Make Inactive**.

## Rank query rules for a site collection

When multiple query rules are active for a tenant, a site collection, or a site, more than one rule can fire for a query that you perform at that level. By default, the rules don't fire in a specific order. However, if you want to control the order in which the rules fire, add the query rules that you create to query groups. To do this, select rules to add to a group, and then specify the order in which the rules in the group fire if they're triggered. You can also prevent query rules that rank lowest in a group from firing even if they do get triggered.

1. In the site collection, select **Settings**![Settings icon.](sharepointonline/media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png), and then select **Site settings**. If you don't see **Site settings**, select **Site information**, and then select **View all site settings**.
2. On the **Site Settings** page, in the **Site Collection Administration** section, select **Search Query Rules**.
3. On the **Manage Query Rules** page, on the **Select a Result Source** menu, select the result source that contains the query rules that you want to group.
4. For each query rule that you created that you want to add to a group, point to the rule and select the check box.

    Note

    The **Defined for this site collection** section lists query rules that you created for this site collection.
5. Select **Order Selected Rules**.
6. In the **Order Selected Rules** dialog, do either of the following, and then select **OK**:

    - Select **Move rules to new group with this name**, and then type a name for the group.
    - Select **Move rules to existing group** and select a group in the list.
7. On the **Manage Query Rules** page:

    - To change the order in which a rule in a group fires if it's triggered, change the number ordering of the rule.
    - To prevent query rules that are ranked lowest in the group from firing, go to the row for the group's query rule that should fire last, and then in the **Actions** column, in the **Continue/Stop** list, select **Stop**.

## Overview of conditions that make a query rule fire

| Query condition | Description | Configuration | Example |
| --- | --- | --- | --- |
| **Query Matches Keyword Exactly** | The query rule fires when a query exactly matches a word or phrase that you specify. | In the **Query exactly matches one of these phrases** text box, type one or more phrases separated by semicolons. | Type "picture; pic" in the box. The query rule fires when a user types "picture" or "pic" in a search box. The rule doesn't fire if a user types "pictures" or "sunny picture." |
| Query Contains Action Term | The query rule fires when a query contains a term for something that the user wants to do. The term must be at the beginning or end of the query. | Enter the action term that causes the query rule to fire by doing one of the following:  Select **Action term is one of these phrases**, and type one or more phrases. | Type the word "download" in the **Action term is one of these phrases** box. When a user types "download Contoso Electronics datasheet" in a search box, there are chances the user isn't searching for a document that contains the words "download," "Contoso," "Electronics," and "datasheet." Instead, the user most likely wants to download a Contoso Electronics datasheet. The query rule fires, and only the words "Contoso," "Electronics," and "datasheet" are sent to the search index. |
| Query More Common in Source | The query rule fires if users frequently sent this query from another source that you already specified. | In the **Query is more likely to be used in this source** list, select a result source. | You selected **Local Video Results** in the list. The query rule fires if a user types the word "training" in a search box and if that word is already frequently typed in a search box in the Videos vertical. |
| Result Type Commonly Clicked | The query rule fires if other users frequently clicked a particular result type after typing the same query. | In the **Commonly clicked results match result type** list, select a result type. | You selected **SharePoint MicroBlog Post** in the list. If users frequently click a microblog post in search results, consider configuring the most recent microblog post as the first promoted result, and the next most recent microblog post as the second promoted result (in the **Actions** section). |
| Advanced Query Text Match | You want to use a phrase or a dictionary entry that causes the query rule to fire, and then define more detailed conditions for when the query rule fires. | Enter the phrase or term that causes the query rule to fire by doing one of the following:  Select **Query contains one of these phrases**, and type one or more phrases. | You selected **Query contains one of these phrases**, and then chose **Start of query matches, but not entire query**. The query rule fires only if the phrase is at the beginning of a query, not if it's at the end. |