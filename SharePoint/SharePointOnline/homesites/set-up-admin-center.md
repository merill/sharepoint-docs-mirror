---
layout: Conceptual
title: Set up Viva Connections in the Microsoft 365 admin center - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/homesites/set-up-admin-center
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-01-22T00:00:00.0000000Z
ms.reviewer: 
ms.author: dipadur
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
- essentials-get-started
- Strat_SP_modern
- M365-collaboration
- m365initiative-viva-connections
- intro-get-started
- highpri
ms.custom: intro-get-started
search.appverid:
- SPO160
- MET150
ROBOTS: 
description: Learn how to set up Viva Connections in the Microsoft 365 admin center and prepare your experience for your organization
locale: en-us
document_id: a015afb5-32b8-67e4-f485-26c4dbc91897
document_version_independent_id: 7a1cda08-f528-de3d-d176-14e423601799
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/homesites/set-up-admin-center.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: homesites/set-up-admin-center
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/homesites/set-up-admin-center.md
platformId: 1688d008-0544-98cc-fde1-36f9febcf002
---

# Set up Viva Connections in the Microsoft 365 admin center - SharePoint in Microsoft 365 | Microsoft Learn

Note

- You must have an Enterprise (E), Frontline (F), or Academic (A) license type to create a Viva Connections experience.
- Users with a Microsoft 365 subscription (E, F, or A license) are limited to creating and using one experience. If you want to create or use two or more experiences (up to 50), then every user in your tenant must have a Microsoft Viva Suite or Viva Communications and Communities license. See [Microsoft Viva plans and pricing](https://www.microsoft.com/microsoft-viva/pricing) for more info.
- You must have SharePoint admin permissions to access the Microsoft 365 admin center.
- You must have Teams administrator (or higher) permissions to pin the Viva Connections app in the Teams Admin Center.
- SharePoint home sites that are part of a multi-geo tenant outside of the main geo need to manage their permissions in the SharePoint Admin Center.

[Microsoft Viva Connections](sharepoint-app-in-teams-overview) is a user experience app in Microsoft Teams that brings together relevant news, conversations, resources, and tools in one place for every person. It's built on your current Microsoft 365 ecosystem to help you engage, inform, and empower your workforce. The Viva Connections experience is deployed and accessed in Microsoft Teams.

Use these step-by-step instructions to help you set up and launch Viva Connections experiences in the Microsoft admin center (MAC) for your organization.

## Before getting started

Setting up Viva Connections only takes a few steps but there are some considerations to think through with other stakeholders at your organization before getting started:

- **Consider the type of experience(s) that are best for your organization**: You can create a stand-alone Viva Connections experience, or you can create a Connections experience that also builds off an existing intranet portal or SharePoint home site. You can create a single Connections experience for your entire organization with dashboard cards targeted to specific audiences (that is, Centralized HR communication), or you can create multiple experiences to meet the needs of distinct audiences (for example, separate content for frontline workers, subsidiaries needing separate content and branding, etc.). Keep in mind that if you have multiple experiences with overlapping content, each experience needs to be updated separately. Learn more on how to [plan, build, and launch Viva Connections](sharepoint-app-in-teams-plan).
- **Decide which audiences should be associated with each experience**: You can create more than one Connections experience if your organization has a need for different user experiences for distinct audiences. Decide which experiences should be associated with specific audiences. You want to consider the [order of experiences](set-up-admin-center#step-4-decide-the-order) that should be seen for audiences that might belong to more than one experience.
- **Think about who should have owner permissions to each experience**: [Owners have full permissions to edit the experience](edit-sharepoint-app-in-teams) and manage access for others. As a best practice, it’s recommended that each experience has a minimum of two owners assigned to it.
- **Pick an icon and name for your app**: Choose an app icon and name to apply to your entire Connections app. This icon and label display as an app in the Teams app bar. Consider what the right branding elements are for your organization. You want to pick a name that aligns with your organization’s brand, and that’s also meaningful and recognizable to viewers.

Note

Currently the app icon and name can be managed only at a tenant level. Organizations with multiple experiences won't see individual names and icons for each one in Teams.

## How to access Viva Connections in the Microsoft admin center

1. Navigate to [admin.microsoft.com](https://admin.microsoft.com/Adminportal/Home#/homepage) and sign in with your credentials.
2. Select **Settings** to expand the selection and select **Viva**.

    Note

    If Settings doesn't show, select **show all** to reveal all available menu options.
3. Select **Viva Connections** to open the Viva Connections admin center.

    [![Screenshot showing how to navigate to the Microsoft Viva admin center.](../sharepointonline/media/homesites/set-up-admin-center/microsoft-viva-option.png)](../sharepointonline/media/homesites/set-up-admin-center/microsoft-viva-option.png#lightbox)
4. Select **Create and manage Viva Connections experiences**.
5. The Viva Connections admin center opens. If you already have a SharePoint home site (intranet portal), Viva Connections displays it as an experience automatically.

## Create a new Connections experience

Create an all-encompassing Connections experience for the entire organization, or for distinct audiences. Optionally, when you create a new experience, you can choose to create a stand-alone Connections experience, or to create a Connections experience and [build off an existing intranet portal (SharePoint home site)](/en-us/viva/connections/viva-connections-overview#how-sharepoint-home-sites-and-viva-connections-work-together).

[![Screenshot of steps to setting up Viva Connections as an admin.](../sharepointonline/media/homesites/set-up-admin-center/set-up-viva-connections-as-admin.png)](../sharepointonline/media/homesites/set-up-admin-center/set-up-viva-connections-as-admin.png#lightbox)

Note

- A Microsoft Viva Suite license or Viva Communications and Communities license is required to create more than one Viva Connections experience. Check the [current license for your organization in billing under licenses](https://www.microsoft.com/microsoft-viva/pricing).
- Organizations are limited to creating a maximum of 50 Viva Connections experiences overall per tenant.
- You must have SharePoint admin permissions to access the MAC.

### Step 1: Create a new experience

Admins are able to create multiple standalone experiences well as intranet home sites having their own Viva Connections experience. As a result, there are now two options for creating a new experience:

> 
> **A. Creating a Connections experience**: This option is the fastest way to get started. It creates a standalone, out-of-the-box Connections experience as an app in Teams without the need for an existing intranet portal. A special site container will be created where the dashboard, resources, and overall Viva home experience are hosted and sourced from. Owners can then begin adding their own content. An intranet portal can be added at any time and designated as a home site.
> 
> **B. Build from an existing intranet portal**: This option is ideal for organizations that already have a SharePoint communications site and would like to use their own content, or would like to add an intranet portal that includes Connections components that can easily be extended to the Web. This option creates a new Connections experience and automatically designates the communications site as a SharePoint home site (intranet portal) that displays navigational elements, and shares permissions.

[![Screenshot showing options for creating a Viva Connections experience.](../sharepointonline/media/homesites/set-up-admin-center/create-new-viva-connections-experience.png)](../sharepointonline/media/homesites/set-up-admin-center/create-new-viva-connections-experience.png#lightbox)

#### Create a Connections experience

This option is ideal if your organization doesn't have an existing intranet portal and just needs to create an experience. This option provides a lightweight experience without a SharePoint intranet portal that users can use to add their own content. Once the Connections experience is created, it can be set as a SharePoint intranet portal (it can be accessed from SharePoint).

1. Select **+ Create new**, displayed on top of the list of experiences.

    [![Screenshot of the option to create a new Connections experience highlighted.](../sharepointonline/media/homesites/set-up-admin-center/option-to-create-new-connections-experience.png)](../sharepointonline/media/homesites/set-up-admin-center/option-to-create-new-connections-experience.png#lightbox)
2. Select **Create a Connections experience**, then select **Next**.

    [![Screenshot of selecting to create a Connections experience.](../sharepointonline/media/homesites/set-up-admin-center/select-create-connections-experience.png)](../sharepointonline/media/homesites/set-up-admin-center/select-create-connections-experience.png#lightbox)
3. Give the new experience a name, add a description, decide the settings, and then select **Next**.

    Note

    The name given to the experience in the MAC displays for owners and members who help manage and edit experiences.
4. After reviewing your settings, select **Create experience**.

    Note

    Each experience you create won't be accessible by viewers until permissions have been assigned by the experience's owners and it’s been enabled.

#### Build from an existing intranet portal

If your organization has an existing intranet portal, then this option allows you to use the existing content, or add an intranet portal that includes Connections components that can easily be extended to the Web.

1. Select **+ Create new**, displayed on top of the list of experiences.

    [![Screenshot of the option to create a new Connections experience highlighted.](../sharepointonline/media/homesites/set-up-admin-center/option-to-create-new-connections-experience.png)](../sharepointonline/media/homesites/set-up-admin-center/option-to-create-new-connections-experience.png#lightbox)
2. Select **Build from an existing intranet portal**, then select **Next**.

    [![Screenshot of selecting to build a Connections experience from an existing intranet portal.](../sharepointonline/media/homesites/set-up-admin-center/build-from-existing-intranet-portal.png)](../sharepointonline/media/homesites/set-up-admin-center/build-from-existing-intranet-portal.png#lightbox)
3. Paste the URL of your SharePoint communication site in the **URL of the communication site you want to use** field.

    Note

    The name given to the experience in the MAC displays for owners and members who help manage and edit experiences.

    [![The screenshot of this diagram presents the option to build a Connections experience from an existing intranet portal.](../sharepointonline/media/homesites/set-up-admin-center/set-intranet-portal-pr.png)](../sharepointonline/media/homesites/set-up-admin-center/set-intranet-portal-pr.png#lightbox)
4. After reviewing your settings, select **Create experience**.

    Note

    Each experience you create won't be accessible by viewers until it’s been enabled, and permissions have been assigned by the experience's owners.

#### Choose the landing destination in the Viva Connections app

Customers building from an existing intranet portal are able to choose the landing destination for audiences in Teams via PowerShell command. (See Choose the default landing experience for Viva Connections desktop for more info).

PowerShell functionality is limited initially as follows:

| Command | Result |
| --- | --- |
| **Get-SPOHomeSite** | Returns the single SharePoint home site URL.  With multiple Viva Connections experiences, a warning message and the first Viva Connection experience from the list is shown. |
| **Set-SPOHomeSite** | 1. Initially it will continue supporting a single SharePoint home site setup. Setting up more SharePoint home sites can be done in the MAC. Support for setting up multiple SharePoint home sites will be supported at a later stage. 2. It updates the Viva Connections default landing destination (Viva Connections, SharePoint home site, or draft status for a SharePoint home site). This functionality will continue getting support in multiple Viva Connection experiences. The cmdlet can be run with the SharePoint home site URL to set the landing destination. |
| **Remove-SPOHomeSite** | This command won't be supported initially for multiple SharePoint home sites customers, but the MAC will support this operation. Users attempting to use the cmdlet will receive an error message and be redirected to the MAC. |

#### When to use a separate experience vs dashboard card-level targeting

Depending on the size of your organization, and the information to communicate, you might decide to create a separate experience for each audience you wish to target. You can also use card-level targeting in your dashboard to provide a targeted experience.

##### When to create another Viva Connection experience

- If you have subsidiaries that need their own content.
- If you don't want users to have to visit the experience of another subsidiary.
- If you have international legal entities that need control over the content.
- If you're presenting international content in a different language that won't overlap with existing content (for example, English experience, Spanish experience, and so on).
- If you have content specific to frontline workers (for example, dashboard and resources with the frontline worker focus such as tasks, shifts, approvals, and top news).

If creating multiple experiences, make sure you don't have any overlap with your content authors, content plan, or audience groups. Overlap requires you to manually manage the content across each experience.

##### Scenarios for card-level targeting and end-user personalization

- Creating a mix of corporate- and department-specific content (for example, centralized HR or corporate communications).
- Decluttering the dashboard to prevent cards from appearing to users who wouldn't use them frequently.

When you're using card-level targeting, consider testing your dashboard with different audience groups to ensure your audiences are seeing the content you want them to.

### Step 2: Assign permissions

Assign two or more owners to each experience so that they have full access to [edit the experience and manage permissions and access for others](edit-sharepoint-app-in-teams).

1. After creating your Connection experiences, select the experience to assign owners to it.
2. Select the **Permissions** tab from the settings panel. The owners assigned to the experience display here.

    Note

    If your SharePoint home site is part of a multi-geo tenant outside of the main geo you need to manage your permissions in the SharePoint Admin Center.
3. Select **Add site owners**.
4. Enter the names of the people you want to assign as owners to this experience in the search bar.
5. Select **Add** after you've finished entering the names.
6. If you want to add more owners later, select **+ Add site owners** under the **Permissions** tab.

    [![Screenshot of the screen on which you can add permissions to owners of experiences.](../sharepointonline/media/homesites/set-up-admin-center/add-permissions-to-assigned-owners.png)](../sharepointonline/media/homesites/set-up-admin-center/add-permissions-to-assigned-owners.png#lightbox)

### Step 3: Designate audiences

Decide which Microsoft Entra security groups or Microsoft 365 groups should be associated with each Viva Connections experience. Adding audiences doesn't grant permissions to the experience but creates associations to scope down who should see the experience by default. Later, owners assign member and visitor level permissions to grant access to the experience, and will further filter the experiences through audience targeting.

Note

Visitors are set to **Everyone in the company except external users** by default.

Audience targeting can be set up by doing either of the following tasks:

- Assigning one or more Microsoft Entra security groups or Microsoft 365 groups to the experience (This situation is the most common scenario).
- Assigning license-level filtering, and choosing if frontline workers (F-license holders) or non-frontline workers should be targeted (This option has been introduced to account for a scenario where a targeted experience for frontline and information workers is needed.).

For example, Contoso Retail wants to target all sales frontline workers for a specific Connections experience. However, they have a Microsoft Entra group for ‘*Contoso Sales All*’ that includes sales directors and higher who are non-frontline workers.

To set up the audience targeting, the Microsoft Entra group ‘*Contoso Sales All*’ license filtering option should be set to **frontline workers**. This setting filters down the experience to only members of the ‘*Contoso Sales All*’ group who are also frontline workers (F-license holders).

If the end user selects both the group ('*Contoso Sales All'*), and license filtering option (F-license holders), an ‘AND’ operation is created. The end user has to satisfy both the group and the license filtering criteria to access the experience.

Users who have already designated audiences for their experiences can use the following steps to manage their audiences:

1. After creating your Connection experiences, select the experience to assign audiences to it.
2. Select the **Audience** tab from the settings panel.
3. Select **Edit audience**.

    [![Screenshot of the screen on which you can save the setting of designating audiences to experiences.](../sharepointonline/media/homesites/set-up-admin-center/editing-audience.png)](../sharepointonline/media/homesites/set-up-admin-center/editing-audience.png#lightbox)
4. To create an experience for the entire organization, select **Everyone in the organization**.
5. To create an experience for a distinct audience, select **Scope down the audience for this experience**. Then, you can filter audiences by license type, by Microsoft Entra group or Microsoft 365 group, or by both.

    1. **Filter by group**: Filter based on the Microsoft Entra group or Microsoft 365 group by typing one or more group names in the search bar.
    2. **Filter by license type**: Filter based on the subscriber license type (Everyone, frontline workers, or information workers).

        Note

        If filtering by Microsoft 365 group and license options, only audiences who belong to both will be associated. For example, an administrator might want to create a distinct experience for a subset of all the frontline workers.
6. Select **Save** when you're done.

    The audiences will display here under **Groups** and can be edited in the future.

    [![Screenshot of the screen displaying details of the audience under Groups tab.](../sharepointonline/media/homesites/set-up-admin-center/display-of-audience-data-under-groups.png)](../sharepointonline/media/homesites/set-up-admin-center/display-of-audience-data-under-groups.png#lightbox)

### Step 4: Decide the order

If your organization has multiple experiences, some audiences might belong to more than one. By setting an order for each experience, you can determine the priority in which experiences are seen first. Experiences should be ordered based on the size of the targeted audiences, from the smallest to the largest. This pattern ensures your smaller audiences see their tailored experience without being flooded with information that larger, more general, audiences might receive.

#### Example of how ordering works with multiple experiences

In the example screenshot, there are two Connections experiences for an organization. Both experiences are enabled and can be seen by viewers.

[![Screenshot of the screen that describes how ordering works with multiple experiences.](../sharepointonline/media/homesites/set-up-admin-center/how-ordering-works-with-multiple-experiences.png)](../sharepointonline/media/homesites/set-up-admin-center/how-ordering-works-with-multiple-experiences.png#lightbox)

The experience named **Contoso 123** is scoped to workers at the organization who are members of the CM (Contoso Members) group. The **comm1** experience is targeted to all users at the organization and provides information targeted to everyone.

Since the CM workers belong to more than one experience, the **Contoso 123** experience should be ordered to come before the experience set to the **Everyone** audience. By ordering the scoped experience first, you create a rule that prioritizes displaying this experience over the default experience for users who belong to more than one experience.

If the example organization creates another experience scoped to a subset of the audience, they need to reorder experiences again to ensure the most scoped experiences are prioritized over the default experience.

#### To set the order of experiences

1. Select **Change order**.
2. Drag and drop the handles next to each experience to reorder as desired.
3. Select **Save** when you're done.

    [![Screenshot of the screen on which you set the order of experiences.](../sharepointonline/media/homesites/set-up-admin-center/set-order-of-experiences.png)](../sharepointonline/media/homesites/set-up-admin-center/set-order-of-experiences.png#lightbox)

    [![Screenshot of the screen that shows order of experiences.](../sharepointonline/media/homesites/set-up-admin-center/set-order-2.png)](../sharepointonline/media/homesites/set-up-admin-center/set-order-2.png#lightbox)

#### Configure the dashboard

Follow the [steps to create the dashboard](create-dashboard) to choose what your users see when they open Viva Connections.

### Step 5: Enable the experience

Enable each Viva Connections experience to make it visible to your audience.

1. Select a Connection experience.
2. In the **General** tab, under **Status**, select **Edit status**.

    [![Screenshot of the screen on which you can edit the status to enable the experience.](../sharepointonline/media/homesites/set-up-admin-center/edit-status-option.png)](../sharepointonline/media/homesites/set-up-admin-center/edit-status-option.png#lightbox)
3. Select the **Enable experience** checkbox, and then select **Save**.

If you need to update the experience, you can also return it to **Draft** status and hide it from viewers.

#### Pin the Viva Connections app in Teams

Note

- The Viva Connections app is part of the [tailored apps experience](/en-us/microsoft-365/frontline/pin-teams-apps-based-on-license). Frontline users who see the tailored app experience have Viva Connections pinned in the first position in the Teams app bar on both mobile and desktop. If you don’t want the app prepinned, either [turn off tailored apps for frontline workers](/en-us/microsoft-365/frontline/pin-teams-apps-based-on-license#admin-controls), change the [app settings](/en-us/microsoftteams/teams-custom-app-policies-and-settings), or [edit how apps in Teams are managed](/en-us/microsoftteams/manage-apps).
- When pinning by a policy, revisit your pinning policy to make sure the Viva Connections app is pinned correctly for intended users every time you add a new experience. See Manage app setup policies for more info.
- Teams administrator (or higher) permissions are required.

Viva Connections creates web parts for organizations who build off existing intranet portals, or home sites which can be accessed via Microsoft Teams. The app is auto enabled in the Teams app bar by default.

If you want to reorganize the app's location in the Teams app bar, follow these steps:

1. Navigate to **Teams admin center &gt; Teams apps &gt; Setup policies**.
2. Select **Global (Org-wide default)** (default policy for all users).
3. Scroll down to **Pinned apps**.
4. Select **+ Add apps**.
5. In the search field, search for the Viva Connections app you enabled with the name you gave it; for example, Intranet.
6. Select **Add** next to the app name, and then, select **Add** at the bottom of the panel.
7. Use the two horizontal lines next to the app to drag it to the top of the app list.
8. Select **Save** at the bottom of the page.

## Options in the Connections experience settings panel

The following settings are available in the Connections experience settings panel:

Note

[Analytics data for Connections experiences](sharepoint-app-in-teams-analytics#how-to-access-the-report) can be accessed from its SharePoint site or the Connections app in Microsoft Teams.

1. **Delete**: [Permanently delete](set-up-admin-center#delete-a-connections-experience) the selected Viva Connections experience.
2. **General tab**: Provides settings to manage the selected experience.
3. **Audience tab**: Create audiences to associate with the selected experience.
4. **Permissions tab**: Assign owners who have permission to edit content in the selected experience.
5. **Experience name**: Edit the name of the selected experience (visible only to administrators in the MAC).
6. **URL**: Location of the intranet home site (if one has been added) or the special site container (if the experience wasn't created from an existing intranet portal).
7. **Status**: Indicates if the status of the selected experience is **Draft** or **Enabled**.
8. **License type**: Which license type the experience has been created for (for example, frontline workers, enterprise, or all).
9. **Default language**: What default language the experience is set as.
10. **Experience description**: A brief description of the experience for administrators (not commonly seen by users).
11. **Creation details**: Information on the creation of the experience.

### Delete a Connections experience

Important

Deleting a Viva Connections experience removes it from your list of experiences. However the site will still remain available under the list of active sites in the SharePoint Admin Center (SPAC).

- If the experience was tied to an intranet portal-based experience, the SharePoint home site designation will be removed and the site will become a regular SharePoint communication site again.
- If the experience was a standalone Connections experience, it will be removed from the list but the special site container, and the content, will still be available through the active sites in SPAC.

Move expired or ‘out of service’ experiences to a draft state to keep the experience intact.

1. Select the experience you wish to delete.
2. In the settings panel, select **Delete**.

    ![Screenshot of the screen on which you can delete a Viva Connections experience.](../sharepointonline/media/homesites/set-up-admin-center/deleting-experience.png)
3. A confirmation screen displays. Select **Delete** to remove the experience.

## Setting a home site after setting up a standalone Connections experience

[![Screenshot showing an example of a SharePoint home site after set up.](../sharepointonline/media/homesites/set-up-admin-center/setting-home-site-after-setting-up-connections-experience.png)](../sharepointonline/media/homesites/set-up-admin-center/setting-home-site-after-setting-up-connections-experience.png#lightbox)

Note

- Organizations that aren't Viva Suite or Viva Communications and Communities subscribers are limited to creating one Viva Connections experience.

If you chose to create a Viva Connections experience without using your own SharePoint communication site as an intranet portal, you can set the special site container that was created to house your content as the home site. Doing so ensures you get the home site features on the existing site, without losing any of the previously configured Connections experience.

Important

Find the special site hosting the Connections experience in the list of active sites in SharePoint admin center. Have the site owners make necessary content updates to that site. This step should be performed once your site is ready to be launched as the home site. Learn more about [planning, building, and launching a home site for your organization](sharepoint-app-in-teams-plan).

To set the site that was created when creating your Viva Connections experience as a home site:

1. Select the experience from the Viva Connections admin page.
2. In the **URL** section, select **Set as home site**.

    [![Screenshot highlighting the steps to select an experience and set it as the home site.](../sharepointonline/media/homesites/set-up-admin-center/set-as-home-site.png)](../sharepointonline/media/homesites/set-up-admin-center/set-as-home-site.png#lightbox)
3. If the selected Viva Connections experience is in a draft state, you can select **enable experience** to take it out of the draft state and make it available to viewers.
4. Select **Set home site**.

    ![Screenshot highlighting the steps to enable the Viva Connections experience and set it as a home site.](../sharepointonline/media/homesites/set-up-admin-center/enable-connections-experience.png)

Once your home site is set up, it's time to plan the launch of the experience and make sure the rest of the organization can find and use the home site. Learn more about [launching your SharePoint home site](sharepoint-app-in-teams-plan#launch-your-sharepoint-home-site).

### Frequently Asked Questions

**I already have a SharePoint home site but I haven’t set up a Connections dashboard yet. Where do I get started to set up a Connections experience?**

If you already have a SharePoint home site, you can see it in your Microsoft 365 admin center under **Setup &gt; Viva &gt; Viva Connections &gt; Create and manage Connections experiences**.

To manage the dashboard, visit the site as site admin, owner, or member, and select **Edit** above the dashboard.

**Will I be able to customize the Viva Connections app name and icon in Teams for each experience that I create?**

You can only choose one icon and app name regardless of how many experiences you set up, so you need to choose an icon and name that make sense to your entire organization. All of your users see the same name and icon, but when they select the app icon, they'll land on their targeted experience.

**I already have dashboard set up with card-level audience targeting. Will that change?**

Card-level audience targeting continues to be supported. This type of targeting is ideal for targeting a subset of cards for departmental scenarios where most cards are still common across the organization.

**I'm looking to set up additional SharePoint home sites but not ready yet to deploy Viva Connections. What are my options?**

Viva Connections and SharePoint home site administration are being combined in the Microsoft 365 admin center. If you only want to set up another SharePoint home site, choose the option to set up Connections by building from an intranet portal. This option designates the intranet portal as the SharePoint home site. Enable the experience so the SharePoint home site can be accessed by others. Each additional SharePoint home site comes with the default Viva Connections dashboard content, so it’s simple to set up Viva Connections. You can set up Viva Connections later and pin the app in Teams for your users.

**I would like my users to access more than one Viva Connections experience in Teams. Is that supported?**

In Teams, users will only be able to see the experience that they're targeted to. If the users are targeted to more than one experience, they see the one with the highest rank order. On the web, users will still be able to access more than one SharePoint home site based on the site access permissions.

The multiple experiences feature is designed for subsidiaries and conglomerates who have nonoverlapping content for their users such that users don’t need to access more than one experience.

**Can content authors (operators) access more than one experience for updating the content?**

Yes, content authors can update intranet-portal-based Viva Connections experiences directly through the web as long as they have the required permissions.

Additionally, if a content author has Owner or Member permissions to the Connections experience in Teams, they're able to switch among the different experiences that they have the permission to edit. Select **[Switch Experience](edit-sharepoint-app-in-teams#how-to-switch-between-multiple-sharepoint-app-in-teams-experiences)** in the settings menu.

**I just changed the status or the rank order of an experience. How soon will the changes take effect for the users?**

It might take up to 24 hours for changes to fully propagate. Consider this timing when you plan to make changes.

**My current SharePoint home site is set up on the SharePoint root site. Now I want to set up additional SharePoint home sites. How do I ensure that the users targeted to the new SharePoint home site don’t see the news posts from the existing SharePoint home site (root site)?**

If your SharePoint home site is set up on the root site, all your users should have access to the root site for SharePoint access. This means that if some of your users are targeted to a new SharePoint home site, they might still see content in the news reader from the existing SharePoint home site (root site).

To avoid this, it's recommended to not use a root site as a SharePoint home site if you plan to set up multiple SharePoint home sites. Alternatively, you can decide to publish content on the existing SharePoint home site (root site) that is broadly applicable to everyone.

Note

The news reader experience is being rolled out to users that will replace the current Feed experience across desktop, web, and mobile devices. This update is planned to roll out to all customers across all devices by the end of April 2025.

**I would like to restore my original setup. How do I get back to my original setup?**

Assuming you already had a single experience set up when you added another experience, you can take the following steps to restore your original setup:

1. Change the audience to **Everyone in the organization** for your original experience and change the rank order to one. This starts serving the experience to everyone.
2. Either change the status of new experiences to draft or delete them from the experiences list.

**I don't see any experience listed in the Viva Connections experience list. However, I still see a dashboard experience in the Viva Connections app in Teams. Why am I seeing this experience?**

Viva Connections offers a default out-of-the-box experience without any initial setup. This experience shows tailored out-of-the-box dashboard cards to information workers and frontline workers. When a SharePoint admin edits the experience for the first time, a special site container gets created to host the customization, which then becomes visible in the Viva Connections experiences list in the Microsoft 365 admin center as **Viva Home**. For more information about editing the out-of-the-box experience, see [Customize and edit the Viva Connections experience](edit-sharepoint-app-in-teams).