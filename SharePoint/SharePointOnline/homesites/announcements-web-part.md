---
layout: Conceptual
title: Use the Announcements web part in the SharePoint app in Teams - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/homesites/announcements-web-part
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-11-02T00:00:00.0000000Z
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
description: Create, schedule, and manage targeted messages with the Announcements web part in the SharePoint app in Teams to reach your organization.
locale: en-us
document_id: e6b1b8bc-79fd-d817-b481-538214c94812
document_version_independent_id: 79620032-47dc-5579-a313-c5733c39051b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/homesites/announcements-web-part.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: homesites/announcements-web-part
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/homesites/announcements-web-part.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 85406f0c-0dca-367f-9360-bfc75a9b7bb0
---

# Use the Announcements web part in the SharePoint app in Teams - SharePoint in Microsoft 365 | Microsoft Learn

Announcements allow you to create, manage, and schedule time-sensitive messages for the SharePoint app in Teams to users in your organization. Use this web part to create and then display announcements. Typically, you add this web part to the top section of the home site's homepage for visibility.

[![Screenshot of what an announcement in Viva Connections looks like on a mobile device.](../sharepointonline/media/homesites/announcements-viva-connections/display-announcement-in-connections-for-mobile.png)](../sharepointonline/media/homesites/announcements-viva-connections/display-announcement-in-connections-for-mobile.png#lightbox)

Note

- Only email-enabled security groups are supported.
- You must have edit permissions or higher for your organization’s SharePoint home site to author and manage announcements.

## When to use announcements

Announcements are the best way to communicate targeted, time-sensitive information for the SharePoint app in Teams. Some examples include:

- To remind users of a specific role about upcoming deadlines, like time sheets, application deadlines, and more.
- To share details about open enrollment benefits with a link to your organization’s Human Resources website.
- To send a specific call to action for new users, such as reminders of required security trainings, morale events, and more.

Important

For emergencies such as a safety hazard, use multiple modes of communication.

### Best practices for using and writing announcements

- Announcements aren't designed for life-threatening emergencies.
- Keep messages short with a clear call to action. Provide a link to more information for more complex topics.
- Use audience targeting to specify which audiences need to receive the announcement to ensure the highest engagement possible.
- Use announcements sparingly so that users understand their importance. Sending them too frequently can cause users to disregard the notifications.
- Allow users to dismiss announcements for less-urgent topics or when there are several high priority announcements active at the same time.
- The delivery time increases with the size of the targeted audience. Sending an announcement to a group of 50 users might take a few minutes but sending one to 100,000 users can take several hours.

## Manage announcements from the Announcements web part

You can view, create, and manage all announcements (active, scheduled, drafts, and expired) from the Announcements web part on your SharePoint home site.

[![Screenshot of the announcements page with multiple announcements visible.](../sharepointonline/media/homesites/announcements-viva-connections/announcements-page.png)](../sharepointonline/media/homesites/announcements-viva-connections/announcements-page.png#lightbox)

### Create a new announcement

When you create a new announcement, you can choose up to 10 audiences to send it to, set an expiration date, schedule a future send date, provide a link for more information, and allow users to dismiss the announcement.

1. From the **Announcement** page, select **+ New Announcement**.

    Note

    You can also create a new announcement from your SharePoint home site. Select **+ New**, and then select **Announcement** to start creating your announcement.
2. Add a **title** and **message**.
3. Select up to 10 audiences to distribute the announcement to. Audiences can be Microsoft Entra groups, Microsoft 365 Groups, or Microsoft Entra dynamic groups.
4. To schedule the message, enable **Scheduling** and enter the **date** and **time** the announcement should be set. Scheduling is off by default and the scheduling date and time fields only display if scheduling is enabled.
5. Select an **end date and time** (up to two weeks from posting) for the announcement to expire. Expired announcements won't display to users.

    [![Screenshot of an announcement in the SharePoint app in Teams.](../sharepointonline/media/homesites/announcements-viva-connections/announcement-details-v2.png)](../sharepointonline/media/homesites/announcements-viva-connections/announcement-details-v2.png#lightbox)

    Note

    At any time while creating your announcement, select **Save as draft** to save the announcement as a draft and work on it later from the announcement page.
6. Under **More options**, **add a link** to more information. Enter a URL and label for the link.
7. Select **Next** to review the details of your announcement.
8. Select **Send announcement** when you're ready to send.

    If you schedule the announcement for a future date, **Send announcement** becomes **Schedule announcement**.

    Note

    After you send an announcement, you can still edit the message details and end date.

    [![Screenshot of editing an announcement in the SharePoint app in Teams.](../sharepointonline/media/homesites/announcements-viva-connections/announcement-details-edit.png)](../sharepointonline/media/homesites/announcements-viva-connections/announcement-details-edit.png#lightbox)

### Edit an active, scheduled, or draft announcement

1. Access the **Announcements** web part.
2. Select the **pencil** icon next to the announcement you want to edit.
3. Make any desired changes in the **Announcement details**, and then select **Next**.
4. Choose to send, schedule, or save as draft to apply your edits.

### Delete an announcement

1. Access the **Announcements** web part.
2. Select the **trashcan** icon next to the announcement you want to delete.

    Note

    Deleted announcements can't be recovered.

    [![Screenshot of the announcement page with the delete icon highlighted.](../sharepointonline/media/homesites/announcements-viva-connections/delete-announcement.png)](../sharepointonline/media/homesites/announcements-viva-connections/delete-announcement.png#lightbox)
3. When prompted, choose **Yes, delete**.
4. If the announcement was active, users can't view it, but it might still be accessible through a Teams notification.

### How announcements display on mobile and tablet devices

**In the Teams mobile app**: Users get a Teams notification displayed on the lock screen of their mobile device alerting them of a new announcement. ([Teams notifications must be enabled by the user](https://support.microsoft.com/office/1cc31834-5fe5-412b-8edb-43fecc78413d)).

[![Screenshot of the lock screen of a mobile phone with an announcement displayed.](../sharepointonline/media/homesites/announcements-viva-connections/announcement-mobile-lockscreen.png)](../sharepointonline/media/homesites/announcements-viva-connections/announcement-mobile-lockscreen.png#lightbox)

Users can also see the announcement appear under the **Activity** tab in Microsoft Teams. Selecting the announcement opens it in the SharePoint app in Teams on mobile.

[![Screenshot of the Activity tab in Teams mobile showing an announcement.](../sharepointonline/media/homesites/announcements-viva-connections/announcement-mobile-activity.png)](../sharepointonline/media/homesites/announcements-viva-connections/announcement-mobile-activity.png#lightbox)

**From the SharePoint app in Teams mobile**: Announcements display at the top of the SharePoint app in Teams mobile experience.

[![Screenshot of an announcement displaying in the Connections app in Teams mobile.](../sharepointonline/media/homesites/announcements-viva-connections/display-announcement-in-connections-for-mobile.png)](../sharepointonline/media/homesites/announcements-viva-connections/display-announcement-in-connections-for-mobile.png#lightbox)

### How announcements display on desktop

When users [access their SharePoint app in Teams experience](https://support.microsoft.com/office/8b4e7f76-f305-49a9-b6d2-09378476f95b#bkmk_access_connections_desktop) through SharePoint, Microsoft Teams, or the Viva Home suite, announcements display above the news spotlight.

[![Screenshot of an announcement in Viva Connections.](../sharepointonline/media/homesites/announcements-viva-connections/announcement-desktop.png)](../sharepointonline/media/homesites/announcements-viva-connections/announcement-desktop.png#lightbox)

When in Microsoft Teams, the announcement also appears in the **Activity** tab. Selecting the announcement opens it within the SharePoint app in Teams experience.

[![Screenshot of an announcement displaying in the Activities feed in Microsoft Teams.](../sharepointonline/media/homesites/announcements-viva-connections/announcement-in-teams-activity-feed.png)](../sharepointonline/media/homesites/announcements-viva-connections/announcement-in-teams-activity-feed.png#lightbox)

## Announcements for frontline workers

The following section covers topics related to sending announcements to frontline workers. Learn how to:

- Use @mentions in a Teams channel to send an announcement to the SharePoint app in Teams to frontline workers.
- Target announcements to frontline workers based on job attributes (location, title, and more).
- Map frontline attributes to workers.
- Enable regional filtering.
- Filter announcements based on frontline worker attributes.

Note

- If you have authentication issues, disable the **Limited-access user permission lockdown mode** under site collection features from your SharePoint site. Learn more in [Enable or disable site collection features](https://support.microsoft.com/office/a2f2a5c2-093d-4897-8b7f-37f86d83df04).
- Vanity domains aren't supported. Contact your organization's support team for more information.
- An update to an existing Teams Channel announcement doesn't display in the SharePoint app in Teams. Users need to follow the link from the original announcement in the SharePoint app in Teams to view the Teams Channel announcement.
- Teams Channel announcements that you delete and then undo show as unread.

### Target announcements to frontline audiences based on department, location, and job title

Managers can send targeted announcements based on a user’s department, location, and job title to frontline workers on a time-sensitive basis by using regional filtering.

Before turning on regional filtering, set up Dynamic Teams at Scale (DTAS) and your organization's hierarchy within the Teams admin center so the proper information is available to filter.

Note

- Set up DTAS and your hierarchy configuration before using this feature to avoid users receiving an error.
- After configuring DTAS and your hierarchy, turn on regional filtering in the SharePoint app in Teams.

#### Map frontline attributes in the admin center

You need to complete some preliminary configuration before you can enable regional filtering in the SharePoint app in Teams.

1. First, your organization needs to set up DTAS within the [Teams admin center](https://admin.teams.microsoft.com/).
2. If DTAS is set up for your organization, you need to set up your frontline operational hierarchy through a CSV file uploaded to the Teams admin center. The CSV file enables you to map your organization’s structure of frontline teams and locations to a hierarchy.
3. After the hierarchy is in place, you'll be able to map your frontline attributes to the Microsoft Entra ID attributes that represent your organization’s departments and job titles.
4. Your final step is to enable regional filtering in the SharePoint app in Teams.

Learn more in [Deploy frontline teams with flexible membership](/en-us/microsoft-365/frontline/deploy-dynamic-teams-at-scale).

##### Get started creating your CSV hierarchy file

1. In the left navigation of the [Teams admin center](https://admin.teams.microsoft.com/), choose **Teams** &gt; **Manage frontline teams**.
2. Go to the **Operational hierarchy tab**.
3. Choose **Get Started**. The **Operational hierarchy** pane opens, and from here, you can upload your hierarchy CSV file or download a CSV template to create one.
4. Select **Download the CSV template** to create your file.
5. After creating the file, return to the **Operational hierarchy tab**.
6. Choose **Get Started** and upload your CSV file.

Learn more in [Deploy your frontline operational hierarchy](/en-us/microsoft-365/frontline/deploy-frontline-operational-hierarchy).

##### Map frontline attributes

Map your attributes on the **Map frontline attributes** page of the [deploy frontline dynamic teams](/en-us/microsoft-365/frontline/deploy-dynamic-teams-at-scale?view=o365-worldwide&amp;preserve-view=true) experience. Select the Microsoft Entra attribute for **Department** and **Job title** that best represents the departments and job titles in your organization. You can map one or both attributes.

Learn more in [Set up targeted communications for your frontline](/en-us/microsoft-365/frontline/set-up-targeted-communications).

##### Enable regional filtering

After you configure the DTAS and hierarchy service in Microsoft Teams, enable **Regional filtering** within the **Announcements** page in the SharePoint app in Teams (or from your SharePoint home site).

**To enable from the SharePoint app in Teams:**

1. After accessing the announcements page, select **Settings** in the upper-right corner of the page.
2. In the Settings pane, select the toggle to enable **Regional filtering**.
3. Select **Save** to save your changes.

**To enable from a SharePoint home site**:

1. After accessing the announcements page, select **Settings** in the upper-right corner of the page.
2. In the Settings pane, select the toggle to enable **Regional filtering**.
3. Select **Save** to save your changes.

#### Filter announcement by frontline worker properties

After location, department, and role values are set up in Microsoft Teams, and regional filtering is enabled in Viva Connections, owners and members see options to filter their announcement based on the new set of frontline worker properties created in Microsoft Teams.

To create an announcement filtered by frontline worker properties, follow the same steps for up to selecting your audience:

1. Select **Filter by property**.
2. Select from three properties to enable announcement filtering based on the following variables:

    - **Location**: enter a location in the text field to filter down based on available choices or select the drop-down arrows to choose multiple locations from a list of available options. You can select up to 10 locations.
    - **Department**: enter a department in the text field to filter down based on available choices or select the drop-down arrows to choose multiple departments from a list of available options.
    - **Job title**: enter a job title in the text field to filter down based on available choices, or select the drop-down arrows to choose multiple job titles from a list of available options.

    [![Screenshot of the Viva Pulse properties.](../sharepointonline/media/homesites/announcements-viva-connections/target-announcement-properties.png)](../sharepointonline/media/homesites/announcements-viva-connections/target-announcement-properties.png#lightbox)
3. Continue creating your announcement until you're ready to send.