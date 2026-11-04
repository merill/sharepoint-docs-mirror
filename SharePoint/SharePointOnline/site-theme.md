---
layout: Conceptual
title: Site theme - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/site-theme
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-06-25T00:00:00.0000000Z
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: article
ms.service: sharepoint-online
ms.subservice: sites-pages
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-collaboration
ms.custom:
- admindeeplinkSPO
- onedrive-toc
description: Learn how SharePoint site themes work at a global level to optimize websites effortlessly, expedite site creation with smart algorithms, and ensure accessibility and professional look and feel.
locale: en-us
document_id: fdee50a4-d43b-3767-4409-d563ea4968c2
document_version_independent_id: 862aec70-c5ec-b866-2fb4-41049bff5fe4
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/site-theme.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: site-theme
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/site-theme.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 9eb53867-2f65-dba7-6b66-e8bec6bed3cd
---

# Site theme - SharePoint in Microsoft 365 | Microsoft Learn

The theme is a powerful tool that allows SharePoint site owners and Viva Connections operators to apply cohesive and visually appealing colors to their web spaces. By leveraging these themes, organizations can create a unified look and feel across their sites, ensuring both aesthetic harmony and brand consistency. The customization options provided by themes enable users to tailor their site designs to reflect their unique brand identities while maintaining functionality and accessibility.

## Principles of SharePoint themes

### Guided

Our theming system works at a global level so that updates can be made consistently across each site, allowing users to optimize their websites effortlessly.

### Smart and efficient

Our theming system expedites the site creation process by using smart algorithms to generate options that maximize aesthetic choices.

### Professional

Our themes embody a professional look and feel that ensures coherency and conveys the brand of our enterprise audiences

### Accessible

Our built-in accessibility checker ensures universal design at all levels of themes. For users who decide to customize, we provide helpful guidance to design for accessibility.

## Default themes from Microsoft

- Teal
- Blue
- Orange
- Red
- Purple
- Green
- Periwinkle
- Cobalt
- Dark Teal
- Dark Blue

This collection of themes have been designed for accessibility and reflect colors from the Microsoft brand revealing our shared goals and personality.

## Anatomy of a theme

### Color Combinations

Color combinations are the foundation of your theme, enabling multiple brand colors to reflect your organization’s brand identity and personality. Each theme supports up to 16 color pairs, with each pair consisting of an accent color and a background color. To ensure readability, the text color is automatically set to black or white based on the contrast ratio of the background color.

### Application Zones

Theme colors are applied across key areas of the SharePoint site:

- Site Header and Footer: Managed by site owners to establish consistent branding.
- Section Design: Page authors can apply color combinations to individual sections for visual distinction.
- Text Web Part (Rich Text Editor): Theme colors enhance text formatting and styling.
- Design Ideas: Color combinations are reflected in suggested layouts and visual enhancements.

## Create your own theme

In the SharePoint brand center, a brand manager can create custom themes for your organization. These themes are available in the Change the Look experience for site owners and Viva Connections operators to apply to their sites and experiences.

Note

To create custom themes in the Brand center, your administrator must have enabled the Brand center from the Microsoft 365 Admin center. You can only read or delete a legacy custom theme which consists of primary color, text color, background color, accent color. The legacy custom theme won't be automatically upgrade to the new custom theme format.

Visit the SharePoint or Viva Connections branding experiences and select **New theme**.

- **Step 1**: Select your primary, secondary colors using your brand colors or by adding a custom color. Add up to 16 combinations within the primary and secondary colors. In each color combination, you can switch around the background/accent color.
- **Step 2**: Name your theme and preview in SharePoint experiences.

![Screenshot of creating a new theme.](sharepointonline/media/brand-center-new-theme-2025.png)

## Pay attention to accessibility

Color and contrast are important for accessibility. People with low vision, such as those with macular degeneration, need a certain amount of contrast to be able to see what’s on the screen. It’s also important to be careful with color selection, because color blind people can’t tell the differences between certain colors. For example, someone who has red-green color-blindness sees red and green as the same color. In this theme creation experience we provide a color contrast checker built into the UI Elements preview to guide you towards creating accessible themes.