---
layout: Conceptual
title: Plan, build, and launch a SharePoint home site for your organization - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/homesites/sharepoint-app-in-teams-plan
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-07-13T00:00:00.0000000Z
ms.reviewer: 
ms.author: dipadur
author: divyachapan
manager: elizapo
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
ms.custom:
- seo-marvel-apr2020
search.appverid:
- SPO160
- MET150
- BSA160
description: Learn about how to plan, build, and launch the main SharePoint landing site for your organization.
locale: en-us
document_id: 000496c3-d564-0972-bc93-0c0c64db68d8
document_version_independent_id: a3cc6ba7-3c3e-04b0-fdea-be4461040582
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/homesites/sharepoint-app-in-teams-plan.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: homesites/sharepoint-app-in-teams-plan
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/homesites/sharepoint-app-in-teams-plan.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: e0fc2e2b-f3e5-a86c-a2b7-df3b60b2cc14
---

# Plan, build, and launch a SharePoint home site for your organization - SharePoint in Microsoft 365 | Microsoft Learn

A SharePoint home site provides a customized landing experience that reflects the organization’s brand, voice, and priorities. A SharePoint home site also serves as the gateway to other portals in your organization’s intranet. It is the base SharePoint component when designing and implementing for the SharePoint app in Teams (formerly Viva Connections). Think of SharePoint home sites as an *add-on* to your intranet design. SharePoint home sites are communication sites that have special capabilities such as being marked as an official source of news in the organization. Consider making your organization's root site the SharePoint home site.

If you’ve already created the communication site and are ready to specify it as your home site now, learn how to [configure the SharePoint app in Teams](/en-us/viva/connections/sharepoint-teams-app-config).

Note

- You must have an Enterprise (E), Frontline (F), or Academic (A) license type to create a Connections experience.
- Users with a Microsoft 365 subscription (E, F, or A license) are limited to creating and using one experience. If you want to create or use two or more experiences (up to 50), then every user in your organization must have a Microsoft Viva Suite or Viva Communications and Communities license. See [Microsoft Viva plans and pricing](https://www.microsoft.com/microsoft-viva/pricing) for more info.
- You must have SharePoint admin permissions to access the SharePoint admin center.

**Use a SharePoint home site to:**

- Provide a gateway to other high-traffic portals.
- Connect people with an intranet-wide search experience.
- Showcase targeted news and content.
- Use the [SharePoint app in Teams](sharepoint-app-in-teams-overview) to integrate your intranet into Microsoft Teams.

| Example of a SharePoint home site: | View in the SharePoint mobile app: |
| --- | --- |
| ![Screenshot of a SharePoint home site as an example.](../sharepointonline/media/homesites/home-site-example-3.png) | ![Screenshot of a SharePoint app viewing a SharePoint home site.](../sharepointonline/media/homesites/home-site-fre-3.png) |

**SharePoint home site features explained:**

SharePoint home sites are unlike any other site in SharePoint. When you set a SharePoint communication site as a home site, you’ll automatically apply special capabilities that make the SharePoint home site an ideal landing destination for your organization's intranet.

### Search for content across the entire intranet

SharePoint home sites allow users to search for content (such as sites, news, and files) across the entire intranet rather than searching just the site like typical SharePoint sites. The search scope for the SharePoint home site searches the entire intranet instead of just the site collection like a typical site.

### Official source of organizational news

By default, a SharePoint home site is set as the organizational news source. News posts that are created from the SharePoint home site automatically become official organizational news and take priority on the SharePoint start page. Administrators can [set additional sites as official organizations news sources in the SharePoint admin center](/en-us/sharepoint/organization-news-site).

### Enable and customize global navigation in the SharePoint app bar

The SharePoint app bar features a global navigation option that displays intranet navigational nodes and resources no matter where users are in SharePoint. To take full advantage of this feature, you must have a SharePoint home site. Learn more about how to [enable and customize global navigation in the SharePoint app bar](/en-us/SharePoint/sharepoint-app-bar).

## Before getting started

Before you get started planning and building your SharePoint home site, review best practices and considerations.

### Best practices for creating SharePoint home sites

- A SharePoint home site that will be used by the entire organization needs to be [inclusive and easily accessible on all devices](https://support.microsoft.com/topic/get-ready-build-an-accessible-sharepoint-site-3a1df3ad-f093-450c-85a6-b3bf70fd6abb).
- The site needs to be inclusive and easily accessible on all devices, [consider other languages that might be needed](https://support.microsoft.com/office/create-multilingual-communication-sites-pages-and-news-2bb7d610-5453-41c6-a0e8-6f40b3ed750c).
- The SharePoint home site will be viewed by a high volume of users. Make sure you [manage site performance](/en-us/sharepoint/portal-health) through the planning and building phases.
- Links in the SharePoint home site's navigation can direct users to content in addition to [global navigation](/en-us/sharepoint/sharepoint-app-bar), which can be used to lead users to universally used resources and portals.
- The SharePoint home site should be discoverable by [adding an entry point to Microsoft 365 Copilot](/en-us/microsoft-365/admin/manage/customize-the-app-launcher) and a [featured link on the SharePoint start page](/en-us/sharepoint/change-links-list-on-sharepoint-home-page).
- [News published from the SharePoint home site](https://support.microsoft.com/office/create-and-share-news-on-your-sharepoint-sites-495f8f1a-3bef-4045-b33a-55e5abe7aed7) should be relevant to the entire organization.

### Considerations

- Align the branding on the SharePoint home site to the overall intranet brand where possible.
- Organizations with many portals and resources should consider [making your SharePoint home site a hub site](/en-us/sharepoint/planning-hub-sites) to expand navigational options and easily sync permissions and branding across many sites.
- Use a SharePoint home site template like the [Organization home template](https://support.microsoft.com/office/3e5b98fd-c829-4b26-8367-f94291d9812e) when creating a new site to jump-start the design process.

## Summary of how to get a SharePoint home site for your organization

Since SharePoint home sites are the gateway to your intranet, you want to prioritize content and resources that are relevant to most users. Work with business owners and stakeholders to organize and align the flow of information and the navigational design. Then, use the [Page diagnostics for SharePoint tool](/en-us/microsoft-365/Enterprise/page-diagnostics-for-spo) to ensure to best viewing experience. Next, [set your SharePoint communication site as a home site](/en-us/SharePoint/home-site) in the SharePoint admin center. Finally, use the [Portal launch scheduler](/en-us/microsoft-365/enterprise/portallaunchscheduler) to plan the launch of your new site and make the site discoverable by adding links to key entry-points in the Microsoft 365 experience.

| Plan | Build | Launch and manage |
| --- | --- | --- |
| - Align objectives with partners and business owners  - Organize priority content  - Design way finding for the SharePoint home site and global navigation  - Think about branding  - Use audience targeting on navigational links, news, and web parts | - Upload and organize site assets and content like files and logos (64x64px).  - Customize the site to align with the rest of the intranet  - Apply audience targeting  - Turn on a content approval flow  - Use PowerShell to turn the SharePoint comm site into a home site  - Swap the root site location with the SharePoint home site  - Measure site health and performance  - Test on all devices | - Share the site with your organization  - Use the Portal launch scheduler to release the new site in phases  - Make the SharePoint home site discoverable  - Announce the launch of the SharePoint home site using various communication channels  - Monitor site usage and analytics |

### Plan your SharePoint home site

A great SharePoint home site starts with a plan. Because your SharePoint home site is essentially the gateway to your intranet, you want to collaborate with other business owners such as human resources, leadership teams, and even your legal team to ensure the most important and universal resources are accessible for everyone in the organization.

| Icon | Action | Get started |
| --- | --- | --- |
| ![Screenshot of a sign](../sharepointonline/media/homesites/icon-plan-organize.png) | **Get organized** | Start by aligning objectives with stakeholders and organizing priority content and resources. Consider details specific to your organization like if the SharePoint home page needs to be available in more than one language. Use modern SharePoint sites for the home site. Learn more about how [modern SharePoint sites](https://support.microsoft.com/SharePoint/get-started-with-sharepoint/sharepoint-classic-and-modern-experiences) and how to [create a multi-lingual site and pages](https://support.microsoft.com/SharePoint/sites-pages/create-multilingual-sharepoint-sites-pages-and-news). |
| ![Screenshot of a compass](../sharepointonline/media/homesites/icon-plan-nav.png) | **Plan navigation** | Then, organize the navigational structure for the SharePoint home site itself and global navigation. Consider making the SharePoint home site a hub site if you need to add an extra layer of navigation and make it easier to sync associated site permissions and branding. Learn more about [planning site navigation](/en-us/sharepoint/plan-implement-navigation-design) and how to [make your SharePoint home site a hub site](/en-us/sharepoint/planning-hub-sites). Then, review guidance on how to [set up global navigation on the SharePoint home site](/en-us/SharePoint/sharepoint-app-bar). |
| ![Screenshot of a user](../sharepointonline/media/homesites/icon-plan-gather.png) | **Personalize content** | Next, think about the different audiences that your organization serves. Consider how elements on your SharePoint home site like navigational links and certain web parts could benefit from audience targeting to specific audiences. Learn more about [audience targeting](https://support.microsoft.com/SharePoint/sites-in-sharepoint/change-the-look-of-your-sharepoint-site). |
| ![Screenshot of a file](../sharepointonline/media/homesites/marketing-materials-icon.png) | **Gather branding assets** | Finally, start gathering assets needed to apply custom branding and other details to your SharePoint home site, like logo files (64x64px recommended), color themes, and any custom solutions. Learn more about how to [change the look of your site](https://support.microsoft.com/SharePoint/sites-in-sharepoint/change-the-look-of-your-sharepoint-site). |
| ![Screenshot of a chart](../sharepointonline/media/homesites/icon-plan-perf.png) | **Consider site performance** | Even before you build your site, understand the main elements that make sure your SharePoint home site is healthy. A healthy SharePoint home site optimizes performance to ensure the best possible viewing experience. Use the Page diagnostics for SharePoint tool to make sure the SharePoint home page is healthy before sharing with end users. Learn more about [healthy portals](/en-us/sharepoint/portal-health) and using the [Page diagnostics tool for SharePoint](/en-us/microsoft-365/enterprise/page-diagnostics-for-spo). |

### Build your SharePoint home site

When you've prepared a plan, you're ready to start creating the home site in SharePoint. Start with a communication site, and after you have the general layout finalized, create a [SharePoint app in Teams experience from your existing SharePoint home site](sharepoint-app-in-teams-overview) in the Connections admin center.

| Icon | Action | Get started |
| --- | --- | --- |
| ![Screenshot of a clipboard ](../sharepointonline/media/homesites/icon-plan.png) | **Create a modern communication site** | Start by creating a SharePoint communication site and build out the site by using sections, web parts, and pages. Consider using a mega menu and footer to enhance way finding. See the article on [Using web parts to display content on your SharePoint site](use-web-parts-in-sharepoint) for information on creating personalized content for users. Learn how to [create a communication site](https://support.microsoft.com/SharePoint/sites-in-sharepoint/create-a-communication-site-in-sharepoint), use [modern web parts](https://support.microsoft.com/SharePoint/web-parts-and-apps-in-sharepoint/using-web-parts-on-sharepoint-pages), and [customize your site](https://support.microsoft.com/SharePoint/sites-pages/customize-your-sharepoint-site). |
| ![Screenshot of an audience](../sharepointonline/media/homesites/icon-build-audience.png) | **Apply audience targeting** | Next, turn on audience targeting on for the SharePoint home site. By enabling audience targeting, specific content is prioritized to specific audiences in navigational links, news, and certain web parts. Learn more about [how audience targeting works](https://support.microsoft.com/SharePoint/sites-pages/target-content-to-a-specific-audience-on-a-sharepoint-site) and [how to apply it](https://support.microsoft.com/SharePoint/data-and-lists/target-navigation-news-files-links-and-web-parts-to-specific-audiences) to navigational links, news, and web parts. |
| ![Screenshot of a site](../sharepointonline/media/homesites/icon-build-flow.png) | **Set up a page approval flow** | Then, make sure the SharePoint home site is set up for regular content updates. Turn on content approval to ensure only high-quality content is published on the SharePoint home site. Learn how to [turn on a page approval flow](https://support.microsoft.com/SharePoint/sites-pages/approval-flow-for-modern-pages). |
| ![Screenshot of a two sites getting switched](../sharepointonline/media/homesites/icon-build-swap.png) | **Swap the root site location with the SharePoint home site** | Before you set a communication site as the SharePoint home site, swap the communication site in place of the root site of your tenant as a best practice. The root site for your organization is one of the sites that's provisioned automatically when you purchase and set up a Microsoft 365 plan. If you set up a SharePoint home site first, and then swap locations with your root site, you might lose SharePoint home site settings and need to reapply them. Learn how to [swap the root site with the SharePoint home site](/en-us/sharepoint/modern-root-site#replace-your-root-site). |
| ![Screenshot of a house](../sharepointonline/media/homesites/icon-build-home.png) | **Set the SharePoint home site** | Next, [build a SharePoint app in Teams experience from an existing intranet portal](/en-us/viva/connections/sharepoint-teams-app-config). |
| ![Screenshot of a map](../sharepointonline/media/homesites/icon-build-global.png) | **Set up global navigation** | Then, enable global navigation to allow users to easily navigate to important intranet resources anywhere in SharePoint. Global navigation can only be customized from the SharePoint home site’s home page. Learn how to [enable and customize global navigation](sharepoint-app-bar#customize-global-navigation-in-the-app-bar). |
| ![Screenshot of an approved site](../sharepointonline/media/homesites/icon-build-test.png) | **Test site health and the viewing experience** | Finally, review portal launch guidance and understand the main elements that make sure your SharePoint home site is healthy. A healthy SharePoint home site optimizes performance to ensure the best possible viewing experience. Use the Page diagnostics for SharePoint tool to make sure the SharePoint home page is healthy before sharing with end users. Learn more about [healthy portals](/en-us/sharepoint/portal-health) and using the [Page diagnostics tool for SharePoint](/en-us/microsoft-365/enterprise/page-diagnostics-for-spo). |

### Launch your SharePoint home site

After you've set your SharePoint home site, it’s time to plan the launch and make sure the rest of the organization can find and use the SharePoint home site.

| Icon | Action | Get started |
| --- | --- | --- |
| ![Screenshot of a sharing a site with users](../sharepointonline/media/homesites/icon-launch-add.png) | **Share the site and schedule the portal launch** | Start by ensuring your SharePoint home site is healthy, and then its time to share the site with the rest of the organization and schedule the launch. Use the Portal launch scheduler tool to gradually roll out the SharePoint home site to batches of end users. Using a phased approach is ideal to manage any performance issues that might arise and to ensure a positive viewing experience. Learn how about how to use the [Portal launch scheduler tool](/en-us/microsoft-365/enterprise/portallaunchscheduler). |
| ![Screenshot of a magnify glass](../sharepointonline/media/homesites/icon-launch-search.png) | **Improve discoverability** | Next, make sure people in your organization can easily find the SharePoint home site through a few different entry points in the Microsoft 365 experience. Add a link to the SharePoint home site in the Microsoft app launcher (sometimes called the waffle) and on the SharePoint start page. Learn more about how to [add a custom tile to the app launcher](/en-us/microsoft-365/admin/manage/customize-the-app-launcher) and how to [add a featured link to the SharePoint start page](/en-us/sharepoint/change-links-list-on-sharepoint-home-page). |
| ![Screenshot of a mega phone](../sharepointonline/media/homesites/icon-launch-engage.png) | **Engage your audience** | Then, let your organization know about the new SharePoint home site resource, and other new elements like global navigation. Consider multiple communication options like a SharePoint news post that can also be shared in email and in Microsoft Teams. Learn more about how to [create and post SharePoint news](https://support.microsoft.com/SharePoint/sites-in-sharepoint/create-and-share-news-on-your-sharepoint-sites) and [share it in an email](https://support.microsoft.com/SharePoint/pages-in-sharepoint/use-the-news-web-part-on-a-sharepoint-page#bkmk_send). |
| ![Screenshot of a usage report](../sharepointonline/media/homesites/icon-launch-manage.png) | **Manage and maintain your SharePoint home site** | Finally, when the site is healthy, launched, and being used by the organization, monitor site usage and maintain the site. Site maintenance should include making sure site content is relevant, there aren’t any broken links, and that the site stays healthy and performant. Learn how to [view usage data and analytics](https://support.microsoft.com/SharePoint/sites-in-sharepoint/view-usage-data-for-your-sharepoint-site) for your site and how to [maintain your site over time](https://support.microsoft.com/SharePoint/sites-pages/manage-your-sharepoint-communication-site). |
| ![Screenshot of a globe and monitor](../sharepointonline/media/homesites/icon-launch-viva.png) | **(Optional) Integrate the SharePoint home site into Microsoft Teams using the SharePoint app in Teams** | Expand the reach of the SharePoint home site and help meet users where they're already working by making it easy to access and share content all in one place. After you have a SharePoint home site and the global navigation enabled and customized in the SharePoint app bar, you can integrate the SharePoint home site into Microsoft Teams. |

## SharePoint home site FAQs

**Q:** Are SharePoint home sites set in the Microsoft 365 admin center of SharePoint admin center?  Starting in July 2026, use the SharePoint admin center to [set a SharePoint home site to establish the SharePoint app in Teams experience](sharepoint-app-in-teams-overview).

**Q:** What’s the difference between a SharePoint home site and the SharePoint start page?  The content on the [SharePoint start page](https://support.microsoft.com/SharePoint/sites-pages/discover-content-with-the-sharepoint-start-page) is driven and managed by [Microsoft Graph](/en-us/graph/overview#whats-in-microsoft-graph). Content is personalized to the individual users’ recent activity, followed sites, and content that is saved for later. The SharePoint home site is a landing experience for your entire organization. It displays universally relevant content and directs users to other important portals like Human Resources and company directories.

**Q:** Can I integrate the SharePoint start page with my SharePoint home site?  Integration between the SharePoint home site and SharePoint start page isn't available at this time. However you can [add a featured link to the SharePoint start page](/en-us/sharepoint/change-links-list-on-sharepoint-home-page) to increase SharePoint home site discovery.

Watch for updates in the [Microsoft 365 public roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=SharePoint).

## Resources

[Planning your SharePoint hub sites](/en-us/sharepoint/planning-hub-sites)

[Creating and launching a healthy SharePoint portal](/en-us/sharepoint/portal-health)

[Apply and customize SharePoint site templates](https://support.microsoft.com/office/39382463-0e45-4d1b-be27-0e96aeec8398)