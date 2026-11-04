---
layout: Conceptual
title: Introduction to information management policies - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/intro-to-info-mgmt-policies
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
f1.keywords:
- NOCSH
ms.author: kyrachurney
author: kyracatwork
manager: roygles
ms.date: 2014-05-16T00:00:00.0000000Z
audience: Admin
ms.topic: overview
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
search.appverid:
- WSU150
- SPO160
- OSU150
- MET150
ms.assetid: 63a0b501-ba59-44b7-a35c-999f3be057b2
ms.collection:
- purview-compliance
- Tier3
ms.custom:
- seo-marvel-apr2020
description: Learn how to use information management policies to control and track things like how long content is retained or what actions users can take with that content.
locale: en-us
document_id: 4486f09c-cf60-7dc7-44e4-289ddbe13890
document_version_independent_id: 4795c327-2340-03a1-cc25-2073c317d758
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/intro-to-info-mgmt-policies.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: intro-to-info-mgmt-policies
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/intro-to-info-mgmt-policies.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 54fb4dcb-bde3-7abb-d5ac-5275b5b52772
---

# Introduction to information management policies - SharePoint in Microsoft 365 | Microsoft Learn

Note

To manage content in SharePoint, we recommend you use [Microsoft Purview risk and compliance](/en-us/microsoft-365/compliance) solutions rather than the older information management policies. For example, you can use [Microsoft 365 retention](/en-us/microsoft-365/compliance/retention) to automatically retain and delete content across SharePoint, OneDrive, Teams, Exchange, and other online services.

An information management policy is a set of rules for a type of content. Information management policies enable organizations to control and track things like how long content is retained and what actions users can take with that content. Information management policies can help organizations comply with legal or governmental regulations, or they can simply enforce internal business processes.

For example, an organization that must follow government regulations requiring that they demonstrate "adequate controls" of their financial statements might create one or more information management policies that audit specific actions in the authoring and approval process for all documents related to financial filings.

For how-to information, see [Create and apply information management policies](https://support.microsoft.com/office/eb501fe9-2ef6-4150-945a-65a6451ee9e9).

## Features of information management policies

There are four basic categories of predefined policy features that organizations can use individually or in combination to manage content and processes.

![Types of content policies.](sharepointonline/media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)

The Auditing policy feature helps organizations analyze how their content management systems are used by logging events and operations that are performed on documents and list items. You can configure the Auditing policy feature to log events such as when a document or item is edited, viewed, checked in, checked out, deleted, or has its permissions changed. All of the audit information is stored in a single audit log on the server, and site administrators can run reports on it.

The Expiration policy feature helps organizations delete or remove out-of-date content from their sites in a consistent, trackable way. This helps you manage both the cost and risk associated with retaining out-of-date content. You can configure an Expiration policy to specify that certain types of content expire on a particular date or within a period of time after the document was created or last modified.

Organizations can also create and deploy custom policy features to meet specific needs. For example, a manufacturing organization might want to define an information management policy for all draft product-design specification documents that prohibits users from printing copies of these documents on nonsecure printers. To define this kind of information management policy, you can create and deploy a Printing Restriction policy feature that can be added to the relevant information management policy for the product design specification content type.

## Locations to use an information management policy

To implement an information management policy, you must add it to a list, library, or content type in a site. The location where you create or add an information management policy affects how broadly the policy applies or how broadly it can be used. You can:

**Create a site collection policy and then add this policy to a content type, list, or library** You can create a site collection policy in the Policies list in the top-level site of a site collection. After you create a site collection policy, you can export it so that administrators of other site collections can import it into their Policies list. Creating an exportable site collection policy enables you to standardize the information management policies across the sites in your organization.

When you add a site collection policy to a site content type, and an instance of that site content type is added to a list or library, the owner of that list or library cannot modify the site collection policy for the list or library. Adding a site collection policy to a site content type is a good way to ensure that site collection policies are enforced at each level of your site hierarchy.

![Content Type Policy Template link on Site Settings page.](sharepointonline/media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)

**Create an information management policy for a site content type in the top-level site's Site Content Type Gallery, and then add that content type to one or more lists or libraries** You can also create an information management policy directly for a site content type and then associate an instance of that site content type with multiple lists or libraries. If you create an information management policy this way, every item in the site collection of that content type or a content type that inherits from that content type has the policy. However, if you create an information management policy directly for a site content type, it is more difficult to reuse this information management policy in other site collections because policies that are created this way cannot be exported.

Note

If the content type of an item changes, it might impact the enforcement of policy actions on that item. For more information about content types, see [Introduction to content types](https://support.microsoft.com/en-us/office/introduction-to-content-types-and-content-type-publishing-e1277a2e-a1e8-4473-9126-91a0647766e5).

![Site content types link on Site Settings page.](sharepointonline/media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)

![Information management policy link on settings page for a site content type.](sharepointonline/media/15d83a34-6c8f-4b6e-b6ee-e9b0a70cbb4b.png)

Note

To control which policies are used in a site collection, site collection administrators can disable the ability to set policy features directly on a content type. When this restriction is in effect, users who create content types are limited to selecting policies from the site collection Policies list.

**Create an information management policy for a list or library** If your organization needs to apply a specific information management policy to a very limited set of content, you can create an information management policy that applies only to an individual list or library. This method of creating an information management policy is the least flexible, because the policy applies only to one location, and it cannot be exported or reused for other locations. However, sometimes you may need to create unique information management policies with limited applicability to address specific situations.

![Information management policies link on settings page for document library.](sharepointonline/media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)

You can create an information management policy for a list or library only if that list or library does not support multiple content types. If a list or library supports multiple content types, you need to define an information management policy for each individual list content type that is associated with that list or library. (Instances of a site content type that are associated with a specific list or library are known as list content types.)

To control which policies are used in a site collection, site collection administrators can disable the ability to set policy features directly on a list or library. When this restriction is in effect, users who manage lists or libraries are limited to selecting policies from the site collection Policies list.