---
layout: Conceptual
title: Set up global navigation in the SharePoint app bar - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/homesites/sharepoint-app-bar
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-11-06T00:00:00.0000000Z
ms.reviewer: 
ms.author: 695643216
author: divyachapan
manager: elizapo
audience: Admin
f1.keywords:
- NOCSH
ms.topic: install-set-up-deploy
ms.service: sharepoint-online
ms.subservice: sites-pages
ms.localizationpriority: high
ms.collection:
- Strat_SP_modern
- M365-collaboration
search.appverid:
- SPO160
- MET150
description: Use the SharePoint app bar to enhance intranet way finding, and display and create personalized content
locale: en-us
document_id: 6d5a12d7-72af-262d-c6dd-22ee30ee5595
document_version_independent_id: 03f1d3d3-2526-f7cd-38fd-f4a2a039a8e3
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/homesites/sharepoint-app-bar.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: homesites/sharepoint-app-bar
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/homesites/sharepoint-app-bar.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 761a64f5-9c7b-a15e-23a9-7888c6aaab09
---

# Set up global navigation in the SharePoint app bar - SharePoint in Microsoft 365 | Microsoft Learn

Help users find important content and resources no matter where they are in SharePoint. The SharePoint app bar improves the global way-finding and creation experiences while dynamically displaying personalized favorites and recents. The app bar is on the left-hand side anywhere in modern SharePoint sites.

[![Screenshot of the tabs in the SharePoint app bar.](../sharepointonline/media/homesites/sharepoint-app-bar/app-bar-png.png)](../sharepointonline/media/homesites/sharepoint-app-bar/app-bar-png.png#lightbox)

## The SharePoint app bar experience

The SharePoint app bar brings together intranet resources and quick access to Discover, Publish, Build, and OneDrive. Enable and customize global navigation to help users navigate to important intranet resources across SharePoint. Explore personalized content and see what's new in Discover. Create and share pages and communications in Publish. Create and manage sites in Build, and access your files in OneDrive. Hover over the app bar icons to browse content and find what you need.

Note

- The SharePoint icon shows only to customers who enable the SharePoint app in Teams experience with a configured and published dashboard.

[![Screenshot of the SharePoint app bar tabs.](../sharepointonline/media/homesites/sharepoint-app-bar/sharepoint-app-bar-overview.png)](../sharepointonline/media/homesites/sharepoint-app-bar/sharepoint-app-bar-overview.png#lightbox)

Note

- Global navigation is the only app bar tab that can be customized.
- If global navigation is disabled or not configured, the home icon links to the SharePoint start page.
- Specific SharePoint app bar tabs can't be disabled.
- The SharePoint app bar can't be disabled on specific sites.
- The SharePoint app bar isn't available on classic SharePoint sites.
- The SharePoint app bar might affect current page customizations, specifically customizations that appear on the left side.
- The SharePoint app bar doesn't display in SharePoint for guests outside of your organization.
- In GCC High and DoD environments, users might experience a degraded experience for the My sites panel in the app bar.
- Extra restrictions might apply to tenants within the GCC High and DoD environments when using My News in the SharePoint app bar.
- You must enable global navigation in the SharePoint app bar for SharePoint resources to display in the [Microsoft Teams app bar for the SharePoint app in Teams](sharepoint-app-in-teams-overview).

The SharePoint app bar is a significant change to the user experience and your organization's [intranet information architecture](/en-us/sharepoint/information-architecture-modern-experience). To ensure a seamless experience, Microsoft created specific guidance on how to design current navigation to complement the global navigation feature. There's also [end-user guidance](https://support.microsoft.com/office/use-the-sharepoint-app-bar-b2ab82d5-9af7-445e-ad24-236c5a86b5f8?ui=en-US&amp;rs=en-US&amp;ad=US) to help onboard the rest of your organization.

## Customize global navigation in the app bar

You can enable and customize global navigation in the SharePoint app bar. Customize the global navigation logo, title, and source based on your users’ and organization’s needs.

If you choose to keep global navigation disabled, the home icon links to the SharePoint start page.

Note

- To enable global navigation, you need site owner permissions (or higher) to the SharePoint home site.
- To view the global navigation links, users need read access (or higher) to the SharePoint home site.
- You can apply [audience targeting](https://support.microsoft.com/office/target-content-to-a-specific-audience-on-a-sharepoint-site-68113d1b-be99-4d4c-a61c-73b087f48a81) to menu links in global navigation.
- If you get an error after editing links to sites, try deleting the link and adding it again.
- After implementing global navigation, it might take up to 24 hours for the changes to take effect for users.

### Get started customizing the global navigation tab

1. Set up a [SharePoint home site](sharepoint-app-in-teams-plan) if your organization doesn’t already have one.
2. [Share the SharePoint home site](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) with everyone in your organization to ensure all users can access the global navigation links.
3. Go to your organization’s SharePoint home site.
4. Select **Settings** and then select **Global navigation** settings.

    ![Screenshot of the global navigation option in the settings panel.](../sharepointonline/media/homesites/sharepoint-app-bar/app-bar-settings.png)

    Note

    If you don't see **Global navigation** in the **Settings** pane on the SharePoint home site, you might not have site owner permissions (or higher) to the SharePoint home site.
5. Switch the **Enable global navigation** toggle to **On**.

    ![Screenshot of where to enable the global navigation option in the settings panel.](../sharepointonline/media/homesites/sharepoint-app-bar/app-bar-enable.png)
6. Next, add the **Logo** to represent global navigation for your organization (organization or custom logo). No action is needed if you choose to keep the default home icon.

    Global navigation logo specifications:

    - The logo size should be 20x20 pixels
    - PNG file type
    - Transparent background recommended
7. Then, enter a **Title** that displays at the top of the global navigation pane.
8. Under **Navigation source**, make edits to the selected global navigation source if needed by selecting **Edit global navigation**.
9. Select **Save** when you're done. Updates to global navigation might take several minutes before they appear.

    ![Screenshot of where to select the global navigation source.](../sharepointonline/media/homesites/sharepoint-app-bar/app-bar-source.png)

Note

- The global navigation source can be edited at any time by site owners or admins of the SharePoint home site.
- The site and global navigation [links and labels](https://support.microsoft.com/office/3cd61ae7-a9ed-4e1e-bf6d-4655f0bf25ca) can be edited at any time by editors of the SharePoint home site.
- Implementing global navigation might take up to 24 hours for the changes to take effect.
- If you get an error after editing links to sites, try deleting the link and adding it again.

### Determine the global navigation source based on your SharePoint home site configuration

Set up your [SharePoint home site](/en-us/sharepoint/home-site) first. If you're setting up a SharePoint home site specifically to implement global navigation, review this guidance.

#### For SharePoint home sites that are a hub

Choose one of these source options:

- Select the site navigation source to display the SharePoint home site’s navigation.
- Select the Hub or global navigation source to display the SharePoint home site’s hub navigation.

![Screenshot of the site and hub navigation source options.](../sharepointonline/media/homesites/sharepoint-app-bar/app-bar-hub.png)

Note

When you apply the extended header layout to the site, you no longer see the site navigation.

#### For SharePoint home sites that aren't a hub site

Choose one of these source options:

- Select the site navigation source to display the SharePoint home site navigation.
- Create a secondary set of navigation nodes specifically for the global navigation panel by selecting **Hub or global navigation**. Then, select **Edit global navigation** to create the new global navigation menu. Select **Save** when you're done.

![Screenshot of the site navigation source option.](../sharepointonline/media/homesites/sharepoint-app-bar/app-bar-site.png)

Note

If you create a secondary set of navigation nodes for the global navigation pane, and then you decide to make your SharePoint home site a hub in the future, the new hub site navigation inherits the current navigation nodes for global navigation and can be [edited at any time](https://support.microsoft.com/office/3cd61ae7-a9ed-4e1e-bf6d-4655f0bf25ca).

## See all the different ways you can set up global navigation

Depending on the content you want to make available in the global navigation, you can configure your SharePoint home site navigation and global navigation in three different ways.

### Display the SharePoint home site’s navigation in global navigation

Display hub and site navigation on the SharePoint home page, and the home site navigation in the global navigation panel.

1. Go to the SharePoint home site’s **Settings** and then **Global navigation**.
2. **Enable** global navigation, enter a **Title**, and then select **Home site navigation** as the source.
3. Select **Save**. Changes might take a few minutes to reflect.

### Display the SharePoint home site’s hub navigation in global navigation

Display hub and site navigation on the SharePoint home page, and the hub navigation in the global navigation panel.

1. Go to the SharePoint home site’s **Settings** and then **Global navigation**.
2. **Enable** global navigation, enter a **Title**, and then select **Hub or global navigation** as the source.
3. Select **Save**. Changes might take a few minutes to reflect.

### Hide the site navigation and display it in the global navigation

Display just the hub navigation on the SharePoint home page, and the site navigation in the global navigation panel.

1. Hide the site navigation by going to **Settings**, then **Change the look**, then **Navigation** and toggle the **Site navigation visibility** to **Off**.
2. Go to the SharePoint home site’s **Settings** and then **Global navigation**.
3. **Enable** global navigation, enter a **Title**, and then select **Home site navigation** as the source.
4. Select **Save**. Changes might take a few minutes to reflect.

## Set up a SharePoint home site for the first time

A [SharePoint home site](sharepoint-app-in-teams-plan) is a SharePoint communication site that you create and set as the top landing page for all users in your intranet. The home site brings together news, events, conversations, and other resources to deliver an engaging experience that reflects your organization's voice, priorities, and brand.

Set up a SharePoint home site for your organization to take full advantage of SharePoint’s communication and collaboration features. You need a home site to enable and customize global navigation in the SharePoint app bar.

### Set up a SharePoint home site just for global navigation

If you're creating a [SharePoint home site](sharepoint-app-in-teams-plan) for the main purpose of setting up global navigation, you can simplify the steps recommended to plan and launch a SharePoint home site.

Learn more about planning navigation in SharePoint and apply information architecture principles to your new SharePoint home site’s navigational design.

Note

- Only one communication site can be set as the SharePoint home site.
- The first time you set up a SharePoint home site, it might take up to several minutes for the changes to take effect.
- SharePoint admin credentials are required to transform a communication site into a SharePoint home site.

1. Start by creating a [SharePoint communication site](https://support.microsoft.com/office/7fb44b20-a72f-4d2c-9173-fc8f59ba50eb).
2. [Customize the communication site navigation](https://support.microsoft.com/office/3cd61ae7-a9ed-4e1e-bf6d-4655f0bf25ca) to reflect the view you’d like to see in the global navigation pane. You can make edits to the navigation source and individual labels and links at any time.
3. [Set this communication](/en-us/sharepoint/home-site#set-a-site-as-your-home-site) site as a SharePoint home site within the SharePoint admin center.
4. [Share the SharePoint home site with users](https://support.microsoft.com/office/958771a8-d041-4eb8-b51c-afea2eae3658) so they can access the global navigation links.
5. On the SharePoint home site, select **Settings** and then **Global navigation** to **enable** and customize.
6. For the global navigation source, select **Home site navigation** to display the SharePoint home site navigation that you created in the global navigation panel, then select **Save**.

## Understand how the app bar might affect page customizations

The SharePoint app bar might affect current page customizations, specifically customizations positioned to the left of your page. For organizations using [page placeholders](/en-us/sharepoint/dev/spfx/extensions/get-started/using-page-placeholder-with-extensions), the SharePoint app bar covers parts of both the header and footer page placeholder. In the following image, the placeholder footprint is in red:

![Screenshot of a SharePoint home site with customizations.](../sharepointonline/media/homesites/sharepoint-app-bar/app-bar-overlap.png)

## Modernize classic SharePoint sites to display the SharePoint app bar

The SharePoint app bar only appears in [modern SharePoint sites](/en-us/sharepoint/dev/transform/modernize-classic-sites) and [pages](/en-us/sharepoint/dev/transform/modernize-userinterface-site-pages).

We highly recommend modernizing classic sites not only to display the SharePoint app bar but for a more consistent user experience. Learn more about how to modernize classic SharePoint sites and pages by using the open-source [SharePoint PnP Page Transformation solution](/en-us/sharepoint/dev/transform/modernize-userinterface-site-pages).

## Teach end users about this feature

Help end users understand [how the new SharePoint app bar works](https://support.microsoft.com/office/use-the-sharepoint-app-bar-b2ab82d5-9af7-445e-ad24-236c5a86b5f8?ui=en-US&amp;rs=en-US&amp;ad=US).

### Resources

- Learn more about [SharePoint home sites](sharepoint-app-in-teams-plan).
- Learn more about [planning](/en-us/sharepoint/planning-hub-sites) and [creating hub sites](/en-us/sharepoint/create-hub-site).
- Learn more about [navigation and information architecture in SharePoint](/en-us/sharepoint/information-architecture-modern-experience).
- Learn more about [sharing and permissions in SharePoint](/en-us/sharepoint/modern-experience-sharing-permissions).