---
layout: Conceptual
title: Set up the SharePoint in Teams experience in a specific language - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/homesites/sharepoint-app-in-teams-language
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-10-06T00:00:00.0000000Z
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
- Strat_SP_modern
search.appverid:
- SPO160
- MET150
description: Set up the SharePoint app in Teams experience in a specific language
locale: en-us
document_id: c2cee890-7e24-f4d9-f543-8df0aeffa50c
document_version_independent_id: e05ec0e5-8eea-fa72-60ec-d76654f33125
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/homesites/sharepoint-app-in-teams-language.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: homesites/sharepoint-app-in-teams-language
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/homesites/sharepoint-app-in-teams-language.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/c6f99e62-1cf6-4b71-af9b-649b05f80cce
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3f56b378-07a9-4fa1-afe8-9889fdc77628
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 0becbb08-fb86-dbf1-cc75-378ada911950
---

# Set up the SharePoint in Teams experience in a specific language - SharePoint in Microsoft 365 | Microsoft Learn

The SharePoint app in Teams experience is available in most major languages used in Microsoft 365. Use this article to learn more about how to create and deploy the SharePoint app in Teams experience in a specific language, other than your organization’s default language.

Note

Teams and SharePoint can individually support more than the following languages.

## Available languages

English  Japanese  German  Chinese (Simplified)  Spanish  French  Portuguese (Brazil)  Russian  Italian 

Chinese (Traditional)  Korean  Dutch  Polish  Swedish  Turkish  Czech  Portuguese (Portugal)  Thai 

Danish  Hungarian  Finnish  Indonesian  Greek  Romanian  Ukrainian  Catalan  Norwegian Bokmål 

Broadly, the [SharePoint app in Teams](sharepoint-app-in-teams-overview) has four components that influence the end user’s overall language experience - the dashboard, news, resources, and announcements. This experience is also supported across desktop and web, and on mobile and tablet devices through the Teams mobile app.

The following steps use English as an example, but the steps apply for any one of the 27 languages specified in the available languages.

## The SharePoint app in Teams dashboard

The dashboard is intended to provide quick access to content and tasks from various sources including:

- Intranet content,
- Line-of-business applications,
- HR tools,
- Frontline worker tools, and
- Internal or partner applications.

### For organizations using an intranet portal (SharePoint home site)

1. Create a communication site and make sure to select English as the default language at site creation time.

    ![Image of where to specify the language for a site.](../sharepointonline/media/homesites/vc-language-select.png)
2. [Create the SharePoint app in Teams experience](sharepoint-app-in-teams-overview) using this site as your existing intranet portal.
3. When creating the dashboard, make sure the dashboard author is typing the content in the English language for details like card titles and descriptions – [even if their own preferred language setting](https://support.microsoft.com/sharepoint/get-started-with-sharepoint/change-your-personal-language-and-region-settings) in Microsoft 365 isn't English.
4. Then, you can [create dashboards in more than one language](create-multilingual-dashboard) using the SharePoint multilingual feature.

    Note

    For [custom cards on the dashboard](/en-us/sharepoint/dev/spfx/web-parts/guidance/localize-web-parts), ask your card developer to include content localized in the English language.

## News for the SharePoint app in Teams

You can configure the News web part to display SharePoint news posted from:

- SharePoint Home sites,
- SharePoint sites users frequent and follow,
- [Boosted SharePoint news](https://support.microsoft.com/sharepoint/sites-pages/boost-sharepoint-news-from-organization-news-sites), and
- Trending sites and news published by people the user works with.

### Organizational news

Make sure that authoritative news sites (there can be more than one organization news site) are created with English as the default language and that authors of news post are creating the news posts in English language – even if their own preferred language setting in Microsoft 365 isn't English. In order for content in the news reader to display in a language other than your organization’s default language, SharePoint news posts need to be available in more than one language.

#### All company Viva Engage

Announcement posts in the [All-company group in Viva Engage](/en-us/viva/engage/manage-viva-engage-groups/all-company-community) should be created in English.

## Resources web part

The [Resources web part](https://support.microsoft.com/sharepoint/sites-pages/resources-web-part) doesn't support multiple languages.

## Microsoft Teams mobile app

In the Teams mobile app, SharePoint is displayed as another tab in the Teams app bar, representing the [SharePoint app in Teams](sharepoint-app-in-teams-overview). The language experience of the mobile app is determined by the device language set by the user. Make sure to inform your users to set it to English for a cohesive experience – although it isn't required.

If a user has a device set to the French language, the Teams mobile app "system" strings (placeholder text Microsoft provides out-of-the-box) will be in French while the dashboard cards and news reader will appear in English if the French version of the SharePoint app in Teams experience isn't published. Resources content will also be in English.

![Image of where to specify the language for the mobile app.](../sharepointonline/media/homesites/vc-language-mobile-app.png)