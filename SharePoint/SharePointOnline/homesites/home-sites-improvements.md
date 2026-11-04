---
layout: Conceptual
title: Home site updates - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/homesites/home-sites-improvements
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
description: Home site updates. Viva Connections is now the SharePoint app in team
author: divyachapan
ms.author: dipadur
ms.service: sharepoint-online
ms.topic: article
ms.date: 2026-11-02T00:00:00.0000000Z
ms.subservice: sites-pages
manager: dansimp
locale: en-us
document_id: c2fccdd4-d8ba-e631-e1c7-36ebcb6defc9
document_version_independent_id: ec719027-f655-0944-b868-adf689bde7e9
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/homesites/home-sites-improvements.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: homesites/home-sites-improvements
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/homesites/home-sites-improvements.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 163bf4d8-689c-af45-e2da-e24a4b816e61
---

# Home site updates - SharePoint in Microsoft 365 | Microsoft Learn

This article highlights SharePoint home site updates rolling out starting May 2026 and details the specific changes due to the rename of Viva Connections to SharePoint app.

Note

SharePoint home site technology fully powers the Connections experience in Teams, now branded as the **SharePoint app in Teams.** Targeted Release rollout of all these updates is planned for early May 2026 with GA by end of June 2026. You can track progress on the related Microsoft 365 public roadmap: ID [557983](https://www.microsoft.com/microsoft-365/roadmap?searchterms=557983).

A SharePoint home site provides a customized landing experience that reflects the organization's brand, voice, and priorities. A SharePoint home site also serves as the gateway to other portals in your organization's intranet. It's simply a special communication site in your organization. You can either create a new home site or set an existing communication site as your home site. An admin can do this action in the SharePoint admin center.

Viva Connections is a customizable employee engagement experience app in Teams. It is how your SharePoint intranet can be deployed within Teams desktop and mobile. With the rename of Viva Connections to SharePoint app in Teams, this functionality becomes a prominent feature of a SharePoint home site.

By using this update, you can:

- Create or set a home site in SharePoint admin center.
- [Configure your home site](/en-us/viva/connections/home-site-plan) with web parts and deploy it to your organization, just like any [portal launch](/en-us/microsoft-365/enterprise/portallaunchscheduler).
- In the home site, under **Settings**, set up the [SharePoint app for Teams](/en-us/viva/connections/sharepoint-teams-app-config).

## SharePoint home site updates - May-June 2026

**What's not changing**

- Existing home sites, site content, branding, and overall look and feel stay the same.
- Existing Viva Connections configurations, including customized app names and logos, keep working as configured.
- Existing Viva Connections deployments stay available as a branded employee experience within SharePoint.
- Organizations that require multiple home sites still need the appropriate licensing.

**What's new**

- SharePoint administrators can now create and designate home sites directly from the SharePoint admin center.
- A new [Resources web part](https://support.microsoft.com/office/resources-web-part-6ab12c98-0249-4a3e-92d5-776ce2217d37) is available for curated links and employee resources.
- A new [Announcements web part](https://support.microsoft.com/office/announcements-web-part-ad305eeb-1049-4a03-9f95-88f696efac10) is available. We also removed the extra Viva license requirement for using the Announcements feature.
- New filmstrip layout options are available for the News web part.
- A simplified experience for [configuring SharePoint app in Teams](/en-us/viva/connections/sharepoint-teams-app-config) is now available directly from the home site experience.

**What's changing in the user experience**

- The Teams desktop and mobile branding change from the default Viva Connections to SharePoint for noncustomized experiences.
- The default app experience aligns with SharePoint branding and removes Viva-specific default content, including the "Go to Connections" UX in the default app experience. Users can get back to the default experience by double clicking the app logo in Teams left navigation and clicking on the app name in the panel.
- The global navigation experience within the SharePoint app in Teams desktop displays either SharePoint or your organization's customized app name.
- The Dashboard web part "See all" experience now supports end-user personalization and customization.

## Create and designate home sites directly from the SharePoint admin center

You can now create and establish a communication site as a SharePoint home site directly within your organization's SharePoint admin center. Previously, you needed to go to the Viva Connections management console within Microsoft 365 admin center. Use the following step-by-step instructions to help set up your SharePoint home site. You must be assigned the role of SharePoint admin to accomplish these steps.

Once established, you can configure and manage your site content like any other SharePoint site - choosing your preferred theme, layouts, pages, navigation, and more.

To create a SharePoint home site, follow these steps:

1. Go to your SharePoint admin center and sign in. (The URL resembles `https://tenantname-admin.sharepoint.com/`.)
2. In the navigation pane, select **Settings**.
3. Under **SharePoint apps**, select **Home sites** to open a configuration panel called **Home sites**.
4. Select either **+ Add** or **Add a home site**.

    ![Screenshot of the Home sites settings within the SharePoint admin center.](../sharepointonline/media/home-sites-improvements/sphomesite-spadmin-001-start.jpg)
5. Select the type of home site you want to add. To create a new site, go to *step 6*. To use an existing communication site, go to *step 7*.
6. To create a new site to use as your home site:

    1. Select **Create a new site**, and then select **Next**.
    2. On the **Preview and use 'Home site' template** page, select **Use template**.
    3. Give your site a unique name in the text box under **Site name**.
    4. Validate your site name and URL, add a site owner, and then select **Next**.
    5. Set your language and time zone, and then select **Create site**.

        The site gets created as a home site, with Site name and URL.

        ![Screenshot of the site name dialog when creating a new SharePoint home site from within the SharePoint admin center.](../sharepointonline/media/home-sites-improvements/sphomesite-spadmin-002-create-new.jpg)
7. To use an existing communication site:

    1. Select **Use an existing communication site**, and then select **Next**.
    2. Specify the site URL of the existing communication site you want to set as your home site.
    3. Validate that this site can be set as your home site. Green text indicates that the site meets the criteria.
    4. Select **Save**.

        The specified site is assigned as a home site, with its site name and URL.

        ![Screenshot of the edit pane when entering the URL of an existing SharePoint communication site to convert it to a home site.](../sharepointonline/media/home-sites-improvements/sphomesite-spadmin-003-use-existing.jpg)