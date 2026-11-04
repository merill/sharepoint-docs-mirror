---
layout: Conceptual
title: Create a SharePoint app in Teams dashboard in more than one language - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/homesites/create-multilingual-dashboard
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-07-16T00:00:00.0000000Z
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
description: Learn how to create a SharePoint app in Teams dashboard in more than one language
locale: en-us
document_id: 4538c613-1a12-2aa8-76d2-4efe36bbc214
document_version_independent_id: ca663c39-148f-ca7c-93f8-a0706d0ea47e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/homesites/create-multilingual-dashboard.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: homesites/create-multilingual-dashboard
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/homesites/create-multilingual-dashboard.md
platformId: 6d47a265-48d2-e33d-7c7b-16d4c95f53b6
---

# Create a SharePoint app in Teams dashboard in more than one language - SharePoint in Microsoft 365 | Microsoft Learn

Create a SharePoint app in Teams dashboard that can be viewed in multiple languages. Start by enabling the multilingual experience, select languages, and then assign translators.

Note

You must have site member level permissions or higher to edit multilingual settings.

## Step 1: Navigate to the SharePoint app in Teams dashboard

Depending on whether your organization has a [SharePoint home site](sharepoint-app-in-teams-plan) or not determines where you go to access the multilingual settings.

1. Navigate to your organization’s home site in SharePoint.
2. Select **Edit** in the dashboard section.
3. Then select **Dashboard details**.
4. Copy the link to the dashboard under **Properties &gt; Name**.
5. Paste the link in a browser and then go to **Settings** in the top-right corner.

## Step 2: Enable the multilingual experience and choose languages in Site settings

1. Select **Settings** from the top right, and then select **Site information**.
2. At the bottom of the site information pane, select **View all site settings**.
3. Under **Site Administration**, select **Language settings**.

    ![Image of multilingual settings in the advanced settings panel.](../sharepointonline/media/homesites/viva-language-enable.png)
4. Under **Enable pages and news to be translated into multiple languages**, slide the toggle to **On**.

## Step 3: Select languages and assign translators

1. Under **Add or remove site languages**, start typing a language name in **Select or type a language**, or choose a language from the dropdown. You can repeat this step to add multiple languages. You can add or remove languages from your site at any time by going back to this page.
2. In the **Translator** column, start typing the name of a person you want to be a [translator](https://support.microsoft.com/sharepoint/sites-pages/create-multilingual-sharepoint-sites-pages-and-news#bkmk_translators), and then select the name from the list.

    ![Image of multilingual settings turned on.](../sharepointonline/media/homesites/viva-setting-language.png)
3. Select **Save**.

Note

- Anyone in your organization's [Active Directory](/en-us/azure/active-directory/fundamentals/active-directory-whatis) can be assigned as a translator. People assigned as translators won't automatically be given appropriate permissions. When someone without edit permissions to the dashboard tries to access the site, they're directed to a web page where they can request access.
- You can add or remove languages from your dashboard at any time by going back to this settings page.
- The default language of a dashboard is set to the language chosen when the dashboard is created. However, when English is among the supported languages, English is treated as the preferred language if the user's preferred language isn't supported by the dashboard. This is a known issue.

## Step 4: Create dashboards in specific languages

Translators manually translate copies of the dashboard into one or more languages specified. When you select a language and assign a translator, a copy of the dashboard is created, and translators are notified in an email that a translation is requested. The email includes a link to a copy of the dashboard. An email notification is sent to the person who requested the translation when it's finished. The translator will:

1. Select the **Start translating** button in the email.

    ![Image of a email translation request.](../sharepointonline/media/homesites/ml-dashboard-email.png)
2. Select **Edit** on the top right of the dashboard and translate the content.
3. When the translation is done, select **Save as draft** (if you're not ready to make it visible to readers) or, if the dashboard is ready to be visible to everyone who is using that language on the site, select **Publish**.

    Note

    Some components of 2nd and 3rd party Dashboard cards (for example, the card name) might not be translatable.

## Step 5: Add a translated dashboard name and description

1. To edit the description, from the dashboard, select **Dashboard settings** in the command bar.
2. **Edit** the dashboard description.
3. To edit the name of the dashboard, navigate to **Settings**, and then **Site contents**, and then find the translated dashboard in **Site pages**. Hover over the dashboard that you want to rename and select the ellipsis **(...)** and then select **Rename.**

## Email notifications

The default dashboard owner and assigned translators receive emails when content is edited, with email notifications batched in 30-minute increments as needed. For example, after the first email related to a page is sent, and an update is made to the default language page, the next notification email or any others that need to be sent, will be batched and sent after 30 minutes.

- When a translation dashboard is created, an email is sent to one or more assigned translators to request a translation. The email includes a Start translating button.
- When a translation dashboard is published by a translator, an email is sent to the person who requested the translation.
- When an update is made to the default language dashboard and saved as a draft or is published, an email is sent to the translator to notify them that an update to the translation dashboard might be required.

## More tasks for your multilingual dashboard

After creating dashboards in additional languages, you should confirm which languages are available, update translated versions, and delete translations that are no longer needed.

### Confirm the languages the dashboard can be viewed in

The status of the translation of the dashboard (draft saved, published, and so on) is shown in the Translation pane next to each language. To see the status:

1. Go to the default dashboard.
2. Select **Translation** at the top of the page.
3. In the Translation pane on the right, the status of each language is shown, and a link to view the dashboard in that specific language.

### Find a translated dashboard

You can use the language dropdown at the top of the page, the translation panel, or find the dashboard in the Pages library.

To find it in the Pages library, follow these steps:

1. Go to the Pages library for the home site.
2. Find the dashboard you want to delete in the language folder next to the default language page. The folder can be identified by its two or four letter language code. For example, the French folder is identified as "fr."

### Delete a version of the dashboard for a specific language

To delete a translated dashboard, you must perform a few extra steps to break the association between the default language dashboard and the deleted dashboard.

1. Go to the **Pages library** for the dashboard.
2. Find the version of the dashboard you want to delete in the language folder next to the default language page. The folder can be identified by its two or four letter language code. For example, the French folder is identified as "fr."
3. Select the dashboard you want within the folder, and then select the ellipsis (...) to the right of the selected page.
4. Select **Delete**.
5. After you've deleted the version of the dashboard that’s no longer needed, go to the default language dashboard, and select **Edit** at the top right. If you aren't in edit mode, the rest of the steps won't work.
6. Select **Translation** at the top of the page.
7. In the Translation panel, you should see a message indicating that an association with the page has been removed.
8. **Republish** the default language dashboard.

### Update the dashboard with new changes or edits

Make changes as needed over time to the dashboard and select **Save as draft** or **Republish**. Then, the translators for the translated dashboard are notified in email that an update has been made so updates can be made to the individual translation pages as well.

### Update the default language page

When the default language dashboard is updated, it must be republished. Then, the translators for the translated dashboard are notified in email that an update has been made so updates can be made to the individual translation pages. Translators need to view the version history of the default dashboard to see what content has changed.

## Translated dashboards in the Dashboard web part

The [Dashboard web part](/en-us/sharepoint/use-dashboard-web-part-on-home-site) can be used once the dashboard has been published. The Dashboard web part will display in the users preferred language (if different from the default language) if a translated dashboard has been provided.

Note

- Translation dashboards must be approved and published before they appear.
- Some components of partner dashboard cards (like the card name) might not be translatable.

### More resources

[Set up the SharePoint app in Teams experience in a specific language](sharepoint-app-in-teams-language)

[Edit the SharePoint app in Teams dashboard](create-dashboard)

[Create multilingual SharePoint sites, pages, and news](https://support.microsoft.com/sharepoint/sites-pages/create-multilingual-sharepoint-sites-pages-and-news)