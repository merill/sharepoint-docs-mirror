---
layout: Conceptual
title: Target content to specific audiences in the SharePoint app in Teams - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/homesites/use-audience-targeting-sharepoint-app-in-teams
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2024-09-25T00:00:00.0000000Z
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
ms.localizationpriority: high
ms.collection:
- Strat_SP_modern
- M365-collaboration
search.appverid:
- SPO160
- MET150
description: Use audience targeting in the SharePoint app in Teams to highlight relevant content for the right audiences
locale: en-us
document_id: 01a48858-b464-6223-34a2-7d7d6fabf19b
document_version_independent_id: 7b0505fb-fe8f-17fe-b8c8-285ad03cf335
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/homesites/use-audience-targeting-sharepoint-app-in-teams.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: homesites/use-audience-targeting-sharepoint-app-in-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/homesites/use-audience-targeting-sharepoint-app-in-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 1a00be9c-7792-985c-c7e8-d77128747006
---

# Target content to specific audiences in the SharePoint app in Teams - SharePoint in Microsoft 365 | Microsoft Learn

Audience targeting can help you target content to specific [Microsoft 365 Groups](/en-us/microsoft-365/community/all-about-groups) within your organization so your content is seen by the right people. Audience targeting can be applied to cards on the dashboard, SharePoint news posts, and links in the Resource section - along with numerous other web part and pages. For example, if a regional finance department has many specialized dashboard cards needed for their daily tasks, audience targeting ensures that only members of that group see those cards.

Depending on the size of your organization, and the information to communicate, you might decide to create a separate experience for each audience you wish to target. Consider creating a separate SharePoint app in Teams experience if you have subsidiaries that need their own content. Or if you have international legal entities that need control over the content. Or a common use case when you want to present unique content specific to frontline workers (for example, dashboard and resources with the frontline worker focus such as tasks, shifts, approvals, and top news).

Note

- Audience targeting filters content and isn't a security measure. It isn't meant to manage permissions, access, or secure confidential content.
- [Microsoft Entra Groups](/en-us/microsoft-365/community/all-about-groups) (including security groups, Microsoft 365 Groups, and Microsoft Entra Dynamic Groups) are supported.
- The author is able to view all content in Edit mode. In read-mode, the content is filtered based on the audiences selected.
- Publish (or republish) to save changes made to existing page content, page metadata, and audience targeting settings for audience targeting features to take effect.

## Apply audience targeting to cards in the dashboard

Create a personalized experience by targeting dashboard cards to specific audiences to ensure only the most relevant cards are seen. You can then create a mix of corporate- and department-specific content (for example, centralized HR or corporate communications). It, too, helps declutter the dashboard to prevent cards from appearing to users who wouldn't use them frequently. Use audience targeting:

- To create custom views for distinct roles and regions,
- To generate as many different views as needed to create unique experiences, and
- To ensure the most important content is seen by the intended audience.

When you're using card-level targeting, consider testing your dashboard with different audience groups to ensure your audiences are seeing the content you want them to.

Note

- Site owner permissions to the SharePoint home site are required to edit the SharePoint app in Teams dashboard.
- Site owners should review [creating a SharePoint app in Teams dashboard and adding cards](create-dashboard) for more information.

To apply audience targeting to a dashboard card:

1. From the dashboard, select **Edit**.
2. Select **Edit** on the card you want to apply audience targeting to.

    ![Screenshot showing the edit icon](../sharepointonline/media/homesites/edit-card.png)
3. At the bottom of the edit pane, enter the Groups to the **Audience to target** field. Exit the edit pane when you're done.
4. Preview the viewing experience for different audiences and devices by selecting **Preview** from the command bar.
5. Publish the dashboard when you're done for the audience targeting to take effect. An icon appears on the card indicating audience targeting is applied.

    ![Screenshot of a dashboard card with the targeted audience icon displayed](../sharepointonline/media/homesites/card-targeted-audience.png)

Note

If an audience group that you recently created or changed was selected, it might take some time to see targeting applied for that group.

### Preview your SharePoint app in Teams dashboard to see how it displays for different audiences

After creating or editing cards on your SharePoint app in Teams dashboard, make sure you preview the experience for each audience and on both desktop and mobile devices.

What you see in *preview mode* approximates how the dashboard displays for certain audiences and devices. When you apply audience targeting to cards, you can preview how different people view the dashboard depending on the audience or device.

While in preview-mode, make sure:

- Physical gaps aren't present between cards that might appear while previewing different audiences and devices. If you see gaps, rearrange cards so that every audience and device has a high-quality viewing experience.
- Icons, graphics, and images are easy to identify and understand.
- Buttons and links are active and go to their intended destinations.
- Labels and description text are helpful, easy to read, and make sense for the intended audience.

To preview different audiences:

1. While in edit mode, select **Preview** on the top right.

    [![Screenshot of the preview dashboard button.](../sharepointonline/media/homesites/use-audience-targeting-in-viva-connections/preview-button.png)](../sharepointonline/media/homesites/use-audience-targeting-in-viva-connections/preview-button.png#lightbox)
2. Open the **Select audiences to preview as** drop-down list. (if no cards are audience targeted, you’ll see a disabled **Audience targeting** label).

    [![Screenshot of the audience selection button.](../sharepointonline/media/homesites/use-audience-targeting-in-viva-connections/audience-selection.png)](../sharepointonline/media/homesites/use-audience-targeting-in-viva-connections/audience-selection.png#lightbox)

    - Search for and select a group. Once added, the group is selected by default. You can select the group again in the **Select audiences to preview as** drop-down list to deselect it. Cards targeted to a specific group display.
    - When one or more audiences are selected, cards that don’t have audience targeting applied also display.
    - If no audiences are targeted, only cards that aren’t audience targeted display. If there aren’t any cards with audience targeting applied, none display.
    - If you aren’t part of one of the selected audiences, you’ll only see cards that aren’t audience targeted. If none of the cards are audience targeted, you won’t see any cards.

    [![Screenshot of the audience targeting properties pane.](../sharepointonline/media/homesites/use-audience-targeting-in-viva-connections/audience-selection-overview.png)](../sharepointonline/media/homesites/use-audience-targeting-in-viva-connections/audience-selection-overview.png#lightbox)

In the following example, the preview is set for mobile devices and highlights the different views that can be created from a single dashboard using audience targeting.

| View 1 (General User) | View 2 (Users in Sales) |
| --- | --- |
| ![Screenshot of a mobile preview showing audience targeting for general users.](../sharepointonline/media/homesites/use-audience-targeting-in-viva-connections/mobile-view-1.png) | ![Screenshot of a mobile preview showing audience targeting for users in sales.](../sharepointonline/media/homesites/use-audience-targeting-in-viva-connections/mobile-view-2.png) |

## Apply audience targeting to news posts that display in the News web part

Audience targeting is useful when you want to present information that is relevant only to a particular group of people. For example, you can target news stories about a specific project to only team members and stakeholders of the project.

To use audience targeting, you must first enable audience targeting for each pages library that contains the news stories you wish to target. For more information, see the article on [enabling audience targeting for your pages library](https://support.microsoft.com/office/c2dcee50-f5d7-434b-8cb9-a7feefd9f165#bkmk_audiencetarget).

### Apply audience targeting to news posts from SharePoint

To apply audience targeting to news posts (site pages) from your SharePoint site:

1. Access **Settings** from the SharePoint site where the news is published and select **Site contents**.
2. Navigate to the news post you want to apply audiences to and select **Properties** from the command bar.
3. Under Audience, enter the Groups you wish to target the news post to. Close the Properties panel when done.
4. **Republish** the news post for the audience targeting to take effect. News posts that are targeted to specific audiences list the groups in the Audience column.

    ![Screenshot showing which audience the news post is targeting](../sharepointonline/media/homesites/use-audience-targeting/at-apply-to-news-sharepoint.png)

### Apply audience targeting to news posts from the SharePoint app in Teams

To apply audience targeting to news posts from the SharePoint app in Teams:

1. Navigate to the news post you want to apply audiences to and select **Edit**.
2. Select **Page details** from the command bar.
3. Under Audience, enter the Groups you wish to target the news post to. Close the Properties panel when done.

    ![Screenshot of applying audience targeting in the properties panel.](../sharepointonline/media/homesites/apply-groups.png)
4. Select **Update news** for the audience targeting to take effect.

## Apply audience targeting to links in the Resources web part

Resources are the navigation links that display beneath the dashboard. You can provide another level of customization to your Resource links by applying audience targeting. Resource links that have audience targeting applied only appear to users who are part of the selected audience.

For example, an organization could use audience targeting to provide a set of resource links for users working in Human Resources that would only be seen by those users.

1. Start by selecting **Edit** in the Resources section of your SharePoint app in Teams experience.
2. Hover over the resource link and select the **ellipsis**.
3. Select **Edit**.

    ![Screenshot of the resource link drop-down menu with the edit option highlighted.](../sharepointonline/media/homesites/edit-viva-home/atr-edit-resource.png)
4. Under **Audiences to target**, enter the Groups that you want to see the resource link. Up to 10 audiences can be targeted.
5. Select **Save**.

    ![Screenshot of the resource link properties menu with the audiences to target field highlighted.](../sharepointonline/media/homesites/edit-viva-home/atr-add-at-to-existing-resources.png)
6. Links targeted to specific audiences display an audience targeting icon in the upper left of the resource link.

    ![Screenshot of the audience targeting icon shown in the upper left of the resource link.](../sharepointonline/media/homesites/edit-viva-home/atr-audience-targeting-icon.png)

For more information, see the article on [using the Resources web part](https://support.microsoft.com/office/resources-web-part-6ab12c98-0249-4a3e-92d5-776ce2217d37).

### More resources

[Overview: SharePoint app in Teams](sharepoint-app-in-teams-overview)

[Create the SharePoint app in Teams dashboard](create-dashboard)

[Using web parts to display content on your SharePoint site](use-web-parts-in-sharepoint)

[Set up global navigation in the SharePoint app bar](sharepoint-app-bar)