---
layout: Conceptual
title: Create and edit the SharePoint app in Teams dashboard - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/homesites/create-dashboard
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2024-11-08T00:00:00.0000000Z
ms.reviewer: evanatkin
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
- M365-collaboration - highpri
search.appverid:
- SPO160
- MET150
description: Learn how to edit the SharePoint app in Teams dashboard from Teams and SharePoint, apply audience targeting, and how SSO works with some dashboard cards.
locale: en-us
document_id: 9075560f-4765-ff64-7f97-59ba308a6a47
document_version_independent_id: eb732f4b-8498-f545-f894-da6b3f13b48e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/homesites/create-dashboard.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: homesites/create-dashboard
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/homesites/create-dashboard.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: e14dc3f1-a679-ff04-b8e5-b173b5130ab6
---

# Create and edit the SharePoint app in Teams dashboard - SharePoint in Microsoft 365 | Microsoft Learn

The SharePoint app in Teams dashboard web part provides fast and easy access to information and job-related tasks. Content on the dashboard can be customized and then targeted to users in specific roles, markets, and job functions. It consists of cards that engage viewers with existing Microsoft Teams apps, partner apps, custom solutions using the SharePoint Framework (SPFx), internal links, and external links. You edit the dashboard directly from within the SharePoint app in Teams user interface.

![Screenshot that shows a Dashboard example for desktop and mobile.](../sharepointonline/media/homesites/vc-dashboard-flw.png)

Note

- You're asked to select your primary audience to generate a set of default dashboard cards for when setting up your experience for the first time.
- Operators or members should limit the number of dashboard cards to about 20 for the best viewing experience.
- Operator or member permissions are required to edit the SharePoint app in Teams dashboard.
- Users are able to customize their dashboard in the SharePoint app in Teams on [desktop](https://support.microsoft.com/office/3da30f39-684a-4bde-bb81-2e1407d59b52#bkmk_desktop_customize_dashboard) and [mobile](https://support.microsoft.com/topic/use-a-screen-reader-to-access-and-customize-viva-connections-on-android-and-ios-c4f573dd-cca0-41bd-a409-bc421bf39f32) by reordering, hiding, and showing cards. These changes only affect the experience for the user.

1. From within your SharePoint app in Teams experience, select **Edit** in the dashboard section.
2. Select **+ Add a card**.
3. Select **Edit** (pencil icon) for each card to edit properties like the label, icon, image, and audience targeting settings where applicable.
4. Select **Delete** (trash can icon) to remove cards.
5. Preview the experience on all devices to ensure usability before publishing or republishing.
6. **Publish** or **Republish** when you're done to share the edits with others.

## Change the dashboard settings

The dashboard details contain settings for your dashboard, page versioning, and controls for the Editor and enabling user customization on their personal dashboard view.

Note

Some settings are only available to the SharePoint app in Teams owner.

1. From the SharePoint app in Teams, select **Edit**.
2. Select **Dashboard details** above the dashboard.

    [![Screenshot showing the Dashboard details button](../sharepointonline/media/homesites/create-dashboard/dashboard-details-expanded.png)](../sharepointonline/media/homesites/create-dashboard/dashboard-details-expanded.png#lightbox)
3. In the Dashboard details pane, you can add a thumbnail and description to show in search results:

    - **Change Thumbnail**: Select to add an image to be shown in search results.
    - **Description**: Enter a description in the text field to be shown in search results.
4. The **Editor** can be toggled off or on. When enabled, the editor checks spelling and grammar (Enabled by default).
5. **Allow users to rearrange and hide dashboard cards** can be enabled or disabled (Enabled by default):

    - If enabled, users see the **Customize** button on their dashboard, which enables them to show or hide unused dashboard cards, reorder their dashboard card view, and add their own cards.
    - Changes users make to their dashboard are only seen by that user. Any updates or changes to the dashboard by an owner or member of the experience will override the user’s personal changes.

    Note

    Disabling user customization resets all user dashboard views to what the organization created. This includes removing any dashboard cards the user added to their dashboard.

    [![Screenshot of the dashboard details pane with numbered callout corresponding to steps three through five.](../sharepointonline/media/homesites/create-dashboard/dashboard-details-pane.png)](../sharepointonline/media/homesites/create-dashboard/dashboard-details-pane.png#lightbox)
6. When finished making your changes, select the **X** to close the Dashboard details pane.

Note

- After editing content on the dashboard, it might take several minutes until the new content is available in the Dashboard web part.
- Dashboard cards are refreshed when users manually select Refresh in the SharePoint app in Teams or restart Teams app or navigate away from and back to the SharePoint app in Teams. If Teams remains open and idle in the background, dashboard content may not automatically update until one of these actions occurs.
- For best results, we recommend placing the Dashboard web part in a right vertical section.
- > 
> Images are an important aspect to making your cards rich and inviting. If you're a SharePoint admin, we recommend enabling a Content Delivery Network (CDN) to improve performance for getting images. Consider when storing images that /siteassets is by default a CDN source when Private CDN is enabled while /style library is the default source when the Public CDN is enabled. [Learn more about CDNs](/en-us/office365/enterprise/content-delivery-networks).

![Screenshot of the SharePoint app in Teams Dashboard web part highlighted.](../sharepointonline/media/homesites/vc-dashboard-web-part.png)

You can set the maximum number of cards you want to display.

## Customize your dashboard with cards and audience targeting

Further customize your dashboard by adding various cards meant to help specific users perform specific tasks. Audience targeting and unique dashboard cards can show specific content for specific groups within your organization.

For a list of available dashboard cards, along with a description of the tool and steps for setting up, refer to the article on [Available dashboard cards for the SharePoint app in Teams](available-dashboard-cards).

For more information on audience targeting and aspects of your SharePoint app in Teams experience it can be applied to, see the article on [applying audience targeting to dashboard cards](use-audience-targeting-sharepoint-app-in-teams#apply-audience-targeting-to-cards-in-the-dashboard).

## How URLs and single sign-on works

For some cards, you'll use links to URLs. Depending on the location of the content, links to URLs might display content in Microsoft Teams or elsewhere and [Single sign-on (SSO)](/en-us/azure/active-directory/manage-apps/what-is-single-sign-on) behavior can differ. Get more information about how links to URLs and SSO behave depending on the location of the content you're linking to.

Note

When SSO isn't supported, users are asked to enter their sign-in credentials.

| Opens URL to… | On Teams mobile | On Teams desktop |
| --- | --- | --- |
| Teams App | Teams apps (like Shifts, Approvals, or Kudos) open within Teams and user doesn’t need to authenticate again. | Teams apps (like Shifts, Approvals, or Kudos) open within Teams and user doesn’t need to authenticate again. |
| Forms | Forms open within Teams, user is asked to sign-in on the first time, and user doesn’t need to authenticate again if they stay signed in. | Forms open within Teams, user is asked to sign-in on the first time, and user doesn’t need to authenticate again if they stay signed in. |
| Viva Engage | Viva Engage opens within Teams, user is asked to sign-in on the first time and user doesn’t need to authenticate again if they stay signed in. | Opens a web browser session and the user might need to reauthenticate depending on browser and machine settings. |
| Power Apps | Power Apps opens within Teams, user is asked to sign-in on the first time and user doesn’t need to authenticate again if they stay signed in. | Opens a web browser session and the user might need to reauthenticate depending on browser and machine settings. |
| Power Portals | Power portals open within Teams, user is asked to sign-in on the first time and user doesn’t need to authenticate again if they stay signed in. | Opens a web browser session and the user might need to reauthenticate depending on browser and machine settings. |
| Stream | Stream opens within Teams, user is asked to sign-in on the first time and user doesn’t need to authenticate again if they stay signed in. | Opens a web browser session and the user might need to reauthenticate depending on browser and machine settings. |
| External Links | Web view opens within Teams and the user might need to authenticate again (depending on the site.) | Opens a web browser session and the user might need to reauthenticate depending on browser and machine settings. |

## Related resources

[Learn more about how to plan a dashboard](plan-sharepoint-app-in-teams)

[Design your own dashboard card with the card designer](use-card-designer)

[Available dashboard cards for the SharePoint app in Teams](available-dashboard-cards)