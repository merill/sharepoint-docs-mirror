---
layout: Conceptual
title: Curate the allowed list for Restricted SharePoint Search - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/restricted-sharepoint-search-allowed-list
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-07-06T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.reviewer: 
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: administrator
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- M365-collaboration
- m365copilot
- magic-ai-copilot
- trust-pod
- M365-sam
description: 'Learn how to use SharePoint Admin Center active sites report and SharePoint Advanced Management Data Access Governance report to find the most active and shared sites for the Restricted SharePoint Search allowed list. '
locale: en-us
document_id: 16e1cbce-140a-9b64-61e5-154cfabb1ffd
document_version_independent_id: e51580d2-2514-6e0d-ee4c-bd091e3d36b6
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/restricted-sharepoint-search-allowed-list.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: restricted-sharepoint-search-allowed-list
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/restricted-sharepoint-search-allowed-list.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
platformId: 195a4d66-126e-05ce-031f-df172b633991
---

# Curate the allowed list for Restricted SharePoint Search - SharePoint in Microsoft 365 | Microsoft Learn

Important

Restricted SharePoint Search is retiring. Starting July 31, 2026, new enablement is blocked. Use comprehensive data controls such as [Restricted Content Discovery](/en-us/sharepoint/restricted-content-discovery) (RCD) for content discoverability.

[Restricted SharePoint Search](/en-us/sharepoint/restricted-sharepoint-search) is designed for customers of Microsoft Copilot Chat and agentic experiences. It's designed as a short-term solution to allow time for your organization's administrators to thoroughly review and audit site and file permissions, but it's not intended or scalable for long-term use. Comprehensive data security solutions are available, including [SharePoint Advanced Management](/en-us/sharepoint/advanced-management) and [Microsoft Purview](/en-us/purview/ai-microsoft-purview).

As a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [other administrator](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365, you can set up an allow list of Restricted SharePoint Search with a maximum of 100 selected SharePoint sites. For Copilot and organization-wide search, besides the contents that users already have access to, either by direct sharing, visiting, or owning, your organization's users can only reach the sites on the allow list, honoring these sites' current permissions.

Setting up the allow list in Restricted SharePoint Search gives you time to review and audit site permissions. But which sites should you include in the allow list? This article introduces strategies and techniques for curating the allow list.

## Steps to create the curated allow list

To create a curated allow list for Restricted SharePoint Search, start by creating an initial list of sites. Then work with your site admins and stakeholders to assess permissions and review the sites. Finally, [apply the list with PowerShell scripts](restricted-sharepoint-search-admin-scripts) as a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365.

### Step 1: Get an initial list of sites

Every organization might have different criteria on what sites you choose to be searched across your organization and discoverable by Copilot. You can use SharePoint Admin Center (SPAC) features to identify sites that can be part of the allow list based on your own criteria. To keep the list manageable, start with the following two types of sites for the allow list:

- **The "Known" sites**: You and your SharePoint site admins already know a set of sites from your organization that are safe to participate in organization wide search and the Copilot experience. Include these sites in the allow list.
- **The top active and shared sites**: The allow list affects what users can see in their organization-wide search results and their Copilot experience. To optimize users' search and Copilot experience, include the top active and shared sites in the allow list. Depending on your license, you can use either the SharePoint Admin Center (SPAC) or the SharePoint Admin Center [Data access governance (DAG) Activity(sharing) report](/en-us/SharePoint/data-access-governance-reports#sharing-links-reports) to identify the most active and shared sites.

### Step 2: Review site permissions

Once you have the list of sites (up to 100), make sure the site permissions and content controls are implemented well enough to make them visible for search and Copilot experience. Work with your site admins and stakeholders to assess permissions and review the sites.

Note

The limit of up to 100 SharePoint sites includes Hub sites, but not their sub-sites. When you enable Hub sites, the sub-sites under a Hub site are included in the allow list but don't count towards the 100-site limit. So if you're picking Hub sites, make sure all the child sites have proper permissions.

### Step 3: Use PowerShell scripts to apply the allow list

After you review permissions in your curated sites, use PowerShell scripts to turn on Restricted SharePoint Search, add sites, and remove sites. You can also use PowerShell scripts to get the list of all sites in your allow list.

## Find the most active and shared sites

You can find the most active sites by using the SharePoint Admin Center (SPAC). If you have [either Microsoft 365 E5 licensing or Microsoft - SharePoint Advanced Management](/en-us/SharePoint/data-access-governance-reports#requirements), you can also use SPAC DAG to find the most shared sites.

- **Using the SharePoint admin center:** If your organization has SharePoint, you have access to SharePoint admin center. Use the Active sites feature in the SharePoint admin center to get the list of sites that had the most page views and files in the last 30 days. This activity can indicate the list of sites that interest the broadest possible audience in the organization.
- **Using the data access governance activity (sharing) report** to [identify sites](/en-us/SharePoint/data-access-governance-reports) that are shared most in the last 28 days.

### Use the SharePoint admin center to find the most active sites

Admins can use the SharePoint admin center features to identify sites that can be part of the allow list based on their criteria. The [Active sites page in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185220) lets you view the SharePoint sites in your organization. Based on your organization's needs, you can [sort and filter sites](/en-us/sharepoint/customize-admin-center-site-list#sort-and-filter-the-site-list) based on columns such as Last activity, Page views, and Page visits. You can search for sites, and [customize the columns and views](/en-us/sharepoint/customize-admin-center-site-list#customize-columns).

1. In the SharePoint admin center, in the navigation pane, select **Active Sites**.

    ![Screenshot of the first step of getting to the active sites page in SPAC](sharepointonline/media/rss-spac-1.png)
2. Using the sorting and filtering functionality of the Active sites you can curate top 100 sites based on your organization needs and create a custom view.

    ![Screenshot of using filter and sorting functions to sort active sites page in SPAC](sharepointonline/media/rss-spac-2.png)
3. Move the columns by scrolling to right and selecting **Customize columns**. 

    ![Screenshot of how to get to customize columns](sharepointonline/media/rss-spac-3.png)

    Use the up and down arrows next to each column's name to move up the Page Views and Files columns next to the URL, so it's easy for you to see the important columns together for analysis. 

    ![Screenshot of how to move columns up and down.](sharepointonline/media/rss-spac-4.png)
4. To create custom view of the top 100 sites sorted by **page views** for last 30 days, follow these steps: 

    1. Select the arrow next to the column header of **Page views** and select **Large to Small**.
    2. Select the arrow next to the column header of **Last activity** select on the **Filter by last activity** &gt; **Last 30 days**.
    3. Use the other columns to sort, or filter based on your needs.

        ![Screenshot of using other columns to filter and sort to sort active sites](sharepointonline/media/rss-spac-5.png)
5. Create a custom view based on your current setting, and save it for future use. To create a custom view, select **All sites** &gt; **Save view as**.

    ![Screenshot of saving custom active sites view](sharepointonline/media/rss-spac-6.png)
6. Specify a name for your custom view:

    ![Screenshot of naming custom active sites view](sharepointonline/media/rss-spac-7.png)

    Your saved custom view is now available for you to choose from the drop-down menu next time.

    ![Screenshot of reviewing saved custom active sites view](sharepointonline/media/rss-spac-8.png)
7. Export the sites and manage the list in CSV file that you can use to add to the list by selecting the **Export** tab.

    ![Screenshot of exporting  active sites results](sharepointonline/media/rss-spac-export.png)

Your exported CSV file looks similar to the following CSV file:

![Screenshot of exported csv file](sharepointonline/media/rss-spac-csv.png)

### Use the data access governance activity (sharing) report to find most shared sites

[SharePoint Advanced Management](advanced-management) includes data access governance reports for SharePoint sites. This report helps you identify potential sites that are active and shared in the last 28 days. 

1. In the SharePoint admin center, select **Reports** &gt; **Data access governance**. Select the **Sharing links** report.

    ![Screenshot of where to find SPAC DAG report.](sharepointonline/media/rss-spac-dag-1.png)
2. In the pane of the **Sharing Links** page, select the **Anyone links** report.

    ![Screenshot of where to find Anyone link.](sharepointonline/media/rss-spac-dag-2.png)
3. The **"Anyone" links** report gives you a list of sites in which the highest number of **Anyone** links were created. These links let anyone access files and folders without signing in. These sites might be great candidates to allow in tenant/org wide search.

    ![Screenshot of where to find Anyone link.](sharepointonline/media/rss-spac-dag-2.png)

## Resources

[Configure a secure and governed foundation for Microsoft Copilot](/en-us/microsoft-365/copilot/configure-secure-governed-data-foundation-microsoft-365-copilot)