---
layout: Conceptual
title: SharePoint app in Teams News notifications - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/homesites/sharepoint-app-in-teams-news-notifications
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2024-08-23T00:00:00.0000000Z
ms.reviewer: 
ms.author: dipadur
author: divyachapan
manager: elizapo
audience: Admin
f1.keywords:
- NOCSH
ms.topic: concept-article
ms.service: sharepoint-online
ms.subservice: sites-pages
ms.localizationpriority: high
ms.collection:
- Strat_SP_modern
- M365-collaboration
search.appverid:
- SPO160
- MET150
description: Learn how News notifications are presented in the SharePoint app in Teams across the desktop, mobile, and web environments
locale: en-us
document_id: 71e3240e-bc72-4712-f81e-0fa55f50f60c
document_version_independent_id: 861c19cc-072f-f3e5-1c78-baff34c8e324
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/homesites/sharepoint-app-in-teams-news-notifications.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: homesites/sharepoint-app-in-teams-news-notifications
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/homesites/sharepoint-app-in-teams-news-notifications.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: fdbcbef7-2ab0-1cd4-48d4-8dd71fe9af59
---

# SharePoint app in Teams News notifications - SharePoint in Microsoft 365 | Microsoft Learn

The SharePoint app in Teams delivers News notifications via Microsoft Teams and links users to the SharePoint in Teams app through the notification. This document describes when notifications are sent, and the conditions that need to be met for receiving notifications.

## When notifications are sent via Microsoft Teams

News notifications are delivered via Microsoft Teams in the desktop, mobile, and web environments in the following scenarios:

- News is published to a SharePoint team or communication site a user follows or by someone a user works closely with.
- News that is targeted to a user is boosted.
- Someone comments on a new News post that a user posted.
- Someone "Likes" a News post that a user posted.
- Someone is @mentioned in a comment on a news post that a user posted.

Note

- Notifications are pulled from the top 100 collaborators that an author works with. If an author works with more than 100 collaborators, the most relevant notifications will be pulled.
- Authors can set an audience on their news posts and notifications will honor the audience that is set. Only users part of the selected Microsoft 365 audience(s) specified receive notifications. Learn more about [audience targeting](https://support.microsoft.com/office/target-navigation-news-files-links-and-web-parts-to-specific-audiences-33d84cb6-14ed-4e53-a426-74c38ea32293#bmstep2) in SharePoint.
- Notifications triggered when a News link is published will be available only on Microsoft Teams mobile.

## Who receives notifications and when

End-users only receive notifications through Microsoft Teams when the following conditions are met:

1. The SharePoint app in Teams is installed for Microsoft Teams.
2. Notifications are enabled in the Teams mobile app and are enabled in the notification settings option in Teams desktop.
3. The notification is outside of the user's set quiet hours as configured in Microsoft Teams.
4. The user has permissions access to the news post.
5. The user is part of the selected Microsoft 365 audience if Audience targeting is enabled for the news post.

Once these conditions are met, end-users receive a notification when news is published by someone they work closely with, or a site they follow. Authors also receive notifications when posts they publish are liked or commented on.

### End-users receive notifications when

- A SharePoint news page is published to [a site you follow](https://support.microsoft.com/office/find-and-follow-sites-news-and-content-4411e38f-9bc5-4ecc-bd33-3dbe939ac84c).
- A SharePoint news page is published by [someone you work closely with](/en-us/graph/people-insights-overview).
- A SharePoint news page is [boosted](https://support.microsoft.com/office/46ad8dc5-8f3b-4d81-853d-8bbbdd0f9c83), and the user is part of the audience target.
- You're "@mentioned" in a comment left on a SharePoint news page.

Authors can receive extra notifications when posts they publish are liked or commented on.

### Authors receive notifications when

- A user 'likes' a SharePoint news page the author created.
- A user comments on a SharePoint news page the author created.

After an author receives a notification of either of these type, the SharePoint app in Teams will batch more notifications of the same type. After the first comment notification to a user, Comments are batched in 20-min intervals. After the first like to a user, likes are batched in 60-min intervals.

## How can notifications be controlled?

The SharePoint app in Teams notifications follow the Microsoft Teams notification settings, including Quiet Hours settings, and are only sent if users have the SharePoint app in Teams installed.

Note

There is no organization-wide method for an administrator to control the SharePoint app in Teams notifications.

Users can control what notifications they want to see in the following ways:

- On Teams desktop and web, specific notification types can be selectively enabled or disabled under **Settings** &gt; **Notifications and activity** &gt; **SharePoint**. These settings are respected on Teams mobile as well.
- On Teams mobile, notifications can't be selectively enabled or disabled, but users can toggle all push notifications in the Teams mobile app:

    - For iOS: **Settings** &gt; **Notifications** &gt; **Custom** &gt; under **Notify me for** &gt; **Apps on Teams**.
    - For Android: **Settings** &gt; **Notifications** &gt; **Custom** &gt; under **Teams - General** &gt; **Apps on Teams**.

        Notifications will still be visible under the Microsoft Teams activity feed.

### Frequently Asked Questions

**What defines ‘people I work with’?**

You can read more about how this list of people is determined and how to disable it [in this documentation](/en-us/graph/people-insights-overview).

**How do notifications work?**

If the user selects a notification from their home screen within Microsoft Teams, or from the Microsoft Teams activity feed, the notification takes the user directly to the source news post within the SharePoint app in Teams.

**Will SharePoint app in Teams users be notified every time a user reacts to a news post?**

No. Only authors who created the news post receive notifications when someone likes or comments on a post.

**Why isn’t boosted news displaying in the Top News Card?**

It can take up to 24 hours for boosted news created from those sites to appear in the Top News card in the SharePoint app in Teams dashboard.