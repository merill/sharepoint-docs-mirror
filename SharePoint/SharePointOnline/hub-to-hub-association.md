---
layout: Conceptual
title: Associate a hub site to another hub site in the SharePoint admin center - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/hub-to-hub-association
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-06-24T00:00:00.0000000Z
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: sites-pages
ms.localizationpriority: medium
ms.collection:
- Strat_SP_admin
- M365-collaboration
- m365solution-scenario
- m365solution-spintranet
- highpri
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
search.appverid:
- SPO160
- MET150
- BSA160
description: Learn how to associate a SharePoint hub site to another hub site.
locale: en-us
document_id: c98d42c3-a275-25a1-efbf-03a383c511c1
document_version_independent_id: 7de4ec5f-4a1d-651f-1ace-6d3f62cbf89a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/hub-to-hub-association.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: hub-to-hub-association
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/hub-to-hub-association.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 28137094-1e30-c616-132e-3c3ce1abd743
---

# Associate a hub site to another hub site in the SharePoint admin center - SharePoint in Microsoft 365 | Microsoft Learn

Associate a [SharePoint hub](https://support.microsoft.com/office/what-is-a-sharepoint-hub-site-fe26ae84-14b7-45b6-a6d1-948b3966427f) to another hub to expand search results across multiple hubs in your organization. This enables users to discover relevant content when searching on any sites related to the associated hubs. Learn more about [how to plan](planning-hub-sites) and [create hub sites](create-hub-site) for your organization.

Note

- You must have administrator editing privileges to associate hubs to each other in the SharePoint admin center.
- Hub level associations do not change site permissions.
- Web parts configured to show content from all sites in the hub will continue to show data from the original parent hub only.

## How hub to hub associations work

When you associate hubs, there are no visual changes to the user experience except when viewing search results. When viewing search results, the breadcrumb path at the top of the page displays the associated hub name where content can be found. Hub associations are designed to expand the availability of related content to end users.

![Image of the breadcrumbs when searching on a hub](sharepointonline/media/hub-creadcrumb.png)

Hub to hub site associations create a network of hubs that roll-up to each other to create connections. When hubs are associated with each other, content can be searched for and displayed on hubs up to three levels of association.

**Basic hub association diagram:**

![Image of the basic hub site structure](sharepointonline/media/basic-hub-structure.png)

The following diagram illustrates how hub sites can be associated to other hubs and what site content will appear in search for users searching on any of these sites.

![Image of the basic hub site structure when hubs are associated to eachother](sharepointonline/media/hub-structure-layered.png)

- **Parent hub (level 1):** Think of associated hubs on level 1 as "Parent" hubs that determine the search scope for peer associated hubs.
- **Associated child hub (level 2):** These hub sites are already associated to the parent hub and content within these sites appear when users search at any of these hubs.
- **Associated child hub (level 3):** This level (and all preceding levels) of peer associated hubs behaves the same way as the first level. Content on sites beyond level 3 won't appear in search results.

## Associate a hub to another hub

![Image of the hub management panel in the SharePoint admin center](sharepointonline/media/hub-settings-admin-2.png)

1. Go to [**Active sites** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185220), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.
2. Select the hub site that you'd like to make an association. Then select **Hub** on the command bar and select **Edit hub site settings** to open to hub settings panel.
3. Next, select a hub to associate to in the **Parent hub association** field. Hubs that are available for association appears here.
4. To confirm which hubs have already been associated with your hub site, select **View hubs associated to this hub**.
5. Select **Save**.

Note

Only a hub site that is a parent hub to other hub sites displays the link **View hubs associated to this hub**. If this link is missing, it means the hub site has no child hubs.

## Add links to hub associations to the hub site navigation

Hub site owners can quickly add links to the associated parent hub or child hubs when editing site navigation. Adding links to associated hubs is *optional* but makes it even easier for users to discover more relevant content across hubs.

![Image of the navigation section on a SharePoint site in edit mode](sharepointonline/media/hub-nav-links.png)

1. On the hub site, select **Edit** in the hub navigation bar.
2. Next, select **Associated hubs** to add navigational links to the Parent hub(s).

    - In the hub structure example mentioned before, if you are on the North American marketing hub (level 2) and you select **Associated hubs**, you see a links to the *Teams*, and *Guidelines* hubs.
3. Or, select **Associated child hubs** to add navigational links to associated child hubs (hubs on levels 2 and 3) if available.

    - In the hub structure example mentioned before, if you are on the North American marketing hub (level 2) and you select **Associated child hubs**, you'll see links to the *South America Marketing* and *Asia Marketing* hubs.
4. Then, enter a display name for the new navigational links.
5. Select **OK** to save your selection.
6. Select **Save** when you're done.

Note

Navigational links to associated hubs *are not* automatically updated when there are changes to hub associations in the SharePoint admin center.

## How to confirm the Parent hub association

To view the parent hub association for a site, first go to the site, then select **Settings** and then **Hub site settings**.

Note

Changes to hub associations must be made in the SharePoint admin center and require administrative privileges.

![Image of the hub site settings panel highlighting the Parent hub association](sharepointonline/media/hub-setting-panel-2.png)

### Resources

[Planning your SharePoint hub sites](planning-hub-sites)

[Set up your SharePoint hub site](https://support.microsoft.com/office/set-up-your-sharepoint-hub-site-e2daed64-658c-4462-aeaf-7d1a92eba098)