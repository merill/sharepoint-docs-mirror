---
layout: Conceptual
title: Manage search dictionaries - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/manage-search-dictionaries
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
ms.custom: admindeeplinkSPO
search.appverid:
- SPO160
- MET150
ms.assetid: 2d0ee673-02f1-4b52-9159-f743b5123460
description: Learn how to manage search dictionaries. You can use search dictionaries to include or exclude company names to be extracted from the contents of your indexed documents, or you can include or exclude words for query spelling correction.
locale: en-us
document_id: 867818b3-ef53-e030-16c0-560e470f3433
document_version_independent_id: 16ec330e-8615-fbdd-9ed7-0b1942accdd1
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/manage-search-dictionaries.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-search-dictionaries
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/manage-search-dictionaries.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: d0401dba-3e9f-c2cf-f6ab-21a05f9603eb
---

# Manage search dictionaries - SharePoint in Microsoft 365 | Microsoft Learn

**APPLIES TO:**![yes-img-13](sharepointserver/media/yes.png)2013 ![yes-img-16](sharepointserver/media/yes.png)2016 ![yes-img-19](sharepointserver/media/yes.png)2019 ![yes-img-se](sharepointserver/media/yes.png)Subscription Edition ![no-img-sop](sharepointserver/media/no.png)SharePoint in Microsoft 365

In SharePoint Server, you can use search dictionaries to include or exclude company names to be extracted from the contents of your indexed documents, or you can include or exclude words for query spelling correction.

## Manage company name extraction

Note

Beginning on November 15th, 2019, we'll be removing Company Name Extraction from SharePoint in Microsoft 365. This will only impact you if you have configured company name extraction to be surfaced in the classic Enterprise Search Center as a refiner. Learn more about the specifics and other options by reading [Changes to company name extraction in SharePoint](changes-to-company-name-extraction-in-sharepoint-online).

For company name extraction to work, that is, for a company name to be pulled from your content and for it to be mapped to the managed property **companies**, you have to make sure that:

- The managed property setting **Company name extraction** is enabled on the managed property that you want to extract company names from. This setting is available for the managed properties **Title**, **Body** and **Notes**. See also [Manage the search schema in SharePoint](manage-search-schema).
- The name of the company that you want to extract is in the prepopulated company name dictionary or in the **Company Inclusions** list.

After you have done this, you can then use the managed property **companies** to create refiners based on the extracted company name in the **Refinement Web** **Part**, on the search results page.

## Include company names

1. Go to [**More features** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185077), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

Note

If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.

1. Under **Search**, select **Open**, and to open the term store, select **Manage Search Dictionaries**.
2. On the **Site Settings: Term Store Management Tool** page, to expand the **Search Dictionaries** menu, select the arrow.
3. Select **Company Inclusions**, then select the arrow, and then select **Create Term**.
4. Enter the name of the company that you want to include in the box that appears.
5. To add the term to the **Company Inclusions** list, select anywhere on the page.

## Exclude company names

1. Go to [**More features** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185077), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

Note

If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.

1. Under **Search**, select **Open**.
2. To open the term store, select **Manage Search Dictionaries**.
3. On the **Taxonomy Term Store** page, to expand the **Search Dictionaries** menu, select the arrow.
4. Select **Company Exclusions**, then select the arrow, and then select **Create Term**.
5. Enter the name of the company that you want to exclude in the box that appears.
6. To add the term to the **Company Exclusions** list, select anywhere on the page.

## Manage query spelling correction

Note

Beginning on December 8, 2020, we'll be removing Query Spelling Inclusions and Query Spelling Exclusions from SharePoint in Microsoft 365. This will only impact you if you have configured Query Spelling Suggestions.

If you or another user enters a word in a search query that appears to be misspelled, the search results page helps you out by displaying query spelling corrections. This is also known as "Did you mean?".

For example, if you enter a query that contains the word "ampitheater", the query spelling correction would show "amphitheater" if this term is available in many places in your indexed documents. You can add terms such as the one just shown to the **Query Spelling Inclusions** list, or to the **Query Spelling Exclusions** list to influence how you want query spelling corrections to be applied or not. It takes up to 10 minutes for any changes to the **Query Spelling Inclusions** or the **Query Spelling Exclusions** list to take effect.

## Include a term in query spelling corrections

1. Go to [**More features** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185077), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

Note

If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.

1. Under **Search**, select **Open**.
2. To open the term store, select **Manage Search Dictionaries**.
3. On the **Site Settings: Term Store Management Tool** page, to expand the **Search Dictionaries** menu, select the arrow.
4. Select **Query Spelling Inclusions**, then select the arrow, and then select **Create Term**.
5. Enter the query spelling that you want to include in the box that appears.
6. To add the term to the **Query Spelling Inclusions**, select anywhere on the page.

## Exclude a term from query spelling corrections

1. Go to [**More features** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185077), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

Note

If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.

1. Under **Search**, select **Open**.
2. To open the term store, select **Manage Search Dictionaries**.
3. On the **Site Settings: Term Store Management Tool** page, to expand the **Search Dictionaries** menu, select the arrow.
4. Select **Query Spelling Exclusions**, then select the arrow, and then select **Create Term**.
5. Enter the query spelling that you want to exclude in the box that appears.
6. To add the term to the **Query Spelling Exclusions** list, select anywhere on the page.

## Edit query spelling corrections or company names

1. Go to [**More features** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185077), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

Note

If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.

1. Under **Search**, select **Open**.
2. To open the term store, select **Manage Search Dictionaries**.
3. On the **Site Settings: Term Store Management Tool** page, to expand the **Search Dictionaries** menu, select the arrow.
4. Depending on which dictionary the term is in, select **Company Exclusions**, **Company Inclusions**, **Query Spelling Exclusions**, or **Query Spelling Inclusions**.
5. Double-click the term that you want to edit.
6. Enter the new name for the term.
7. To save the edited term, select anywhere on the page.