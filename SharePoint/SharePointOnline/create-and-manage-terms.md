---
layout: Conceptual
title: Create and manage terms in a term set - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/create-and-manage-terms
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2024-05-28T00:00:00.0000000Z
ms.reviewer: shrganguly
ms.author: ruihu
author: maggierui
manager: jtremper
audience: End User
f1.keywords: NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: admindeeplinkSPO
search.appverid:
- SPO160
- MET150
ms.assetid: 549070a7-41c2-4210-9e9c-5fad22bd8748
description: Learn how to use the SharePoint Term Store Management Tool to create and edit terms in a term store for managed metadata.
locale: en-us
document_id: c38c3945-28eb-8953-4b3f-3d6861434ad3
document_version_independent_id: 110fe1c2-1267-a493-544d-01667fcda8b9
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/create-and-manage-terms.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: create-and-manage-terms
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/create-and-manage-terms.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/c6f99e62-1cf6-4b71-af9b-649b05f80cce
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3f56b378-07a9-4fa1-afe8-9889fdc77628
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: eaa35092-442c-6285-0918-c93089e2e41b
---

# Create and manage terms in a term set - SharePoint in Microsoft 365 | Microsoft Learn

To create and manage terms, you must be a contributor, a group manager, or a term store admin. (If you have many terms that you want to add, consider [importing them](https://support.office.com/article/168fbc86-7fce-4288-9a1f-b83fc3921c18).)

Note

If you are adding a term to a local term set, you must [open term store management at the site level](open-term-store-management-tool#open-term-store-management-for-a-site).

To create a term in a term set

1. In the SharePoint admin center, under **Content services**, select [**Term store**](https://go.microsoft.com/fwlink/?linkid=2185073).
2. In the tree-view pane, select the term set to which you want to add a term.
3. Select **Add term**.

    ![Screenshot of the term store page in the SharePoint admin center with Add term highlighted.](sharepointonline/media/create-manage-term-sets.png)
4. Type a name for the term and press ENTER.
5. Update the term settings as needed:

    - On the **General** tab, to add languages, translations, and synonyms, select **+Add**. The **Add translation and synonyms** panel appears. Select your language, translation, description, and add synonyms. Select **Save**.

        Note

        If you don't see **+Add**, that's probably because you have only one working language, which is your default language. You can add more working languages by selecting **Taxonomy**, then selecting **Edit** next to **Default language**
    - On the **Usage settings** tab, to make the term available to the users and content editors of sites consuming this term set, select **Edit**. The **Available for tagging** panel appears. By default, the term is enabled for tagging. To disable, select the **Enable** checkbox. Select **Save**.
    - On the **Advanced** tab, to use shared or local custom properties to store more data about term sets, select **Edit**. The **Edit shared custom properties** panel appears. Add property names and values. Select **Save**.

## Take another action with terms

There are several actions that you can take on terms that help you build and manage term sets as the business needs of your organization evolve.

To take any of the following actions, first select the term that you want to update.

### Rename term

- Select **Rename term**.

### Copy term

- Select **Copy term**. This action shows the name of the new term as **&lt;original term name&gt; - Copy**. No child terms for the source term are copied.

### Copy term with children

Select **Copy term with children**. This action is only available on terms having at least one child term. This action shows the name of the new term as **&lt;original term name&gt; - Copy**. Children terms of the source term are also copied. Names of children terms are preserved as they are in the source term.

### Move term

1. Select **Move term**. The **Move to** panel appears.
2. Select the target term set or term.
3. Select **Move**.

### Delete term

If you delete this term, any terms below it will also be deleted. Terms that are shared with other term sets will be placed in the Orphaned terms set under System.

1. Select **Delete term**.
2. Select **Delete**.

### Pin term

Pinning a term makes linked copies of the term and its children available at the destination. You can only create or edit the children of a pinned term at the source and the changes reflect everywhere the term is used.

1. Select **Pin term**. The **Pin term to** panel appears.
2. Select the target term set or term where you want to pin the term.
3. Select **Pin**.

### Reuse term

Reusing a term makes linked copies of the term and its children available at the destination. You can create children for a reused term anywhere it's used but will exist only in the term set they were created.

1. Select **Reuse term**. The **Reuse term to** panel appears.
2. Select the target term set or term where you want to reuse the term.
3. Select the term, and then select **Reuse**.

### Merge term

Merging this term with another will collapse its synonyms, translations, and custom properties into the other term.

1. Select **Merge term**. The **Merge to** panel appears.
2. Select the target term set or term where you want to merge the term.
3. Select **Merge**.

### Deprecate term

This action makes any instances of this term in any term set to which it belongs unavailable for tagging. Child terms of the term aren't deprecated.

- Select **Deprecate term**.