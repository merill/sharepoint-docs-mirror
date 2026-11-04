---
layout: Conceptual
title: Change the default sharing link for a site - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/change-default-sharing-link
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-06-30T00:00:00.0000000Z
ms.reviewer: srice
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
customer-intent: As a SharePoint Administrator, I want to change the default sharing link type for a specific site so that I can control the default permissions users see when sharing.
f1.keywords:
- CSH
ms.topic: how-to
ms.custom:
- WSSCentralAdmin_SharingLinkTypeLearnMore
- SharingLinkTypeLearnMore
- seo-marvel-apr2020
- admindeeplinkSPO
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Strat_OD_share
- M365-collaboration
search.appverid:
- SPO160
- BSA160
- GSP150
- MET150
ms.assetid: 81b763af-f301-4226-8842-8d13bd07face
description: Learn how to change the default sharing link for a specific site. You can change this setting at the organization level and at the site level.
locale: en-us
document_id: 7d4d52c4-16bf-1a8c-ae40-e19e82976c8a
document_version_independent_id: 1d13e7f9-8c1d-043a-5929-3d4622b3d9e5
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/change-default-sharing-link.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: change-default-sharing-link
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/change-default-sharing-link.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 774a5048-83d6-2860-528c-bbb16aacb18b
---

# Change the default sharing link for a site - SharePoint in Microsoft 365 | Microsoft Learn

In Microsoft SharePoint, users can share files and folders by sending a link. They should select a link type based on the people to whom they want to give permission. The following link types are available:

- Anyone with the link (previously called "anonymous access" or "shareable")
- People in your organization with the link
- People with existing access
- Specific people

    ![Screenshot of Link settings.](sharepointonline/media/link-settings.png)

As a [SharePoint Administrator](sharepoint-admin-role), you might want to enable users to send "Anyone" links, but you might not want this type of link to be the default when users select to share files and folders. Set the default type of link to something more restrictive, while still allowing users to select other types of links as needed. Change this setting at the organization level and at the site (previously called "site collection") level.

Note

The default sharing link setting applies only to libraries that use the new experience.This setting doesn't affect Outlook Web App, Outlook 2016, or Office clients prior to Office 2016.

For info about changing this setting at the organization level, see [External sharing settings](turn-external-sharing-on-or-off) .

## How do I change the default link type for a site?

1. Go to [**Active sites** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185220), and sign in with an account that has [admin permissions](/en-us/sharepoint/sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the Active sites page.
2. In the left column, select a site.
3. Select **Sharing** on the command bar.
4. Under **Default sharing link type**, clear the **Same as organization-level setting** checkbox.

    ![Screenshot of site-level default sharing link settings](sharepointonline/media/link-settings.png)
5. Choose the default sharing link setting that you want to use for this site, and then select **Save**.

    Note

    To change the default link type for a Teams private or shared channel site, you must use the [Set-SPOSite](/en-us/powershell/module/sharepoint-online/set-sposite) PowerShell cmdlet.

## How do I change the default sharing link permission for a site?

1. Following the steps 1-3 in the preceding section, under **Default link permission**, clear the **Same as organization-level setting** checkbox.
2. Choose the default sharing link permission that you want to use for this site, and then select **Save**.

## Can I use a sensitivity label to configure the default sharing link settings?

If you use [sensitivity labels](/en-us/microsoft-365/compliance/sensitivity-labels) to classify and protect your SharePoint sites, you can also configure the default sharing link type and sharing link permissions for a site and individual documents by using a sensitivity label.

For more information about this scenario, see [Use sensitivity labels to configure the default sharing link type for sites and documents in SharePoint and OneDrive](/en-us/microsoft-365/compliance/sensitivity-labels-default-sharing-link).