---
layout: Conceptual
title: SharePoint Brand Center - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/brand-center-overview
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-10-19T00:00:00.0000000Z
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
ai-usage: ai-assisted
audience: Admin
f1.keywords:
- NOCSH
ms.topic: article
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-collaboration
ms.custom:
- admindeeplinkSPO
description: Learn what SharePoint brand center is, how to set it up and manage it, and learn about brand assets.
locale: en-us
document_id: 90ef061a-5e63-eb3f-c2b1-68d93d00506a
document_version_independent_id: 41389177-942d-5ea5-da01-abbbb5406e3e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/brand-center-overview.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: brand-center-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/brand-center-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/befac1c4-b371-401f-bb32-b2c555258404
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/a3a42e80-4ec5-48ab-90ee-478df3614861
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 8e7a2173-2ecf-d99b-cc58-1ea7bcf156f2
---

# SharePoint Brand Center - SharePoint in Microsoft 365 | Microsoft Learn

The SharePoint brand center offers a centralized branding management application that empowers your brand managers or designated brand owners to help your organization to customize the look and feel of their experiences.

With this new brand asset management system, you can handle your colors, fonts, and images, and other assets all in one place.

## What is the brand center?

The brand center uses the SharePoint organization asset library (OAL) to store and manage assets in the background. The brand center app is located in a designated site within your tenant.

Note

The SharePoint brand center currently only allows one brand center for your organization, and the Global Administrator sets it up.

The brand center app lets you access and manage your organization's brand assets from one central place. By using the brand center app, you can make sure that your organization's brand identity is coherent and professional in all your communication channels. You can also save time and resources by avoiding duplication and confusion of brand assets, and by empowering your employees to create high-quality branded content.

## Setting up the brand center

To enable the brand center, a Global Administrator completes a few steps in the Microsoft 365 admin center to create or activate the brand center app.

During setup, you can choose whether to enable the [Office 365 Content Delivery Network (CDN)](/en-us/microsoft-365/enterprise/use-microsoft-365-cdn-with-spo?view=o365-worldwide), a public content delivery network (public CDN). This public CDN is required for brand fonts because it hosts the font files. Brand colors and the other brand center capabilities don't require a public CDN, and this choice doesn't change how your existing SharePoint organization assets library and template libraries are configured.

The brand center administrative experience finds the site that has your organization's existing organization asset libraries and uses that site for the brand center. If you aren't using organization asset libraries, you're prompted to create a site for the brand center.

The setup steps depend on your current tenant configuration:

- Scenario 1: Your tenant doesn't currently use the SharePoint organization assets feature.
- Scenario 2: Your tenant uses the SharePoint organization assets feature with a private CDN.
- Scenario 3: Your tenant uses the SharePoint organization assets feature with a public CDN.

![Screenshot of accessing brand center from the Microsoft 365 admin center.](sharepointonline/media/mac-brand-center.png)

### Scenario 1: Your tenant doesn't use SharePoint organization assets

For this scenario, a Global Administrator creates the brand center app:

1. In the admin center, go to **Settings &gt; Org settings**.
2. Select **Brand center**.
3. Enter a name for the brand center site, such as *Brand Guide*.
4. Under **Public CDN (optional)**, choose whether to enable the public CDN now. Enable **Public CDN (optional)** if you plan to use brand fonts. The option is turned off by default. You can enable **Public CDN (optional)** later.
5. Create the site.
6. Add site owners to the brand center site, and then share the site link with those owners to give them access to the brand center app.

### Scenario 2: Your tenant uses SharePoint Organization Assets with Private CDN

For this scenario, a Global Administrator activates the brand center app:

1. In the admin center, go to **Settings &gt; Org settings**.
2. Select **Brand center**.
3. Confirm the existing organization assets site that the brand center recognizes.
4. Under **Public CDN (optional)**, choose whether to enable the public CDN now. Enable **Public CDN (optional)** if you plan to use brand fonts. The option is turned off by default. You can enable **Public CDN (optional)** later.
5. Activate the brand center app.
6. Copy and share the brand center site link with the site owners to give them access to the app.

### Scenario 3: Your tenant uses SharePoint Organization Assets with Public CDN

For this scenario, the public CDN is already enabled, so no additional CDN action is required. A Global Administrator activates the brand center app:

1. In the admin center, go to **Settings &gt; Org settings**.
2. Select **Brand center**.
3. Confirm the existing organization assets site that the brand center recognizes.
4. Activate the brand center app for your organization.
5. Copy and share the brand center site link with the site owners to give them access to the app.

After you finish setting up your SharePoint brand center, you can control who can access the brand center app by customizing the site permissions of the brand center site. Site owners of the brand center site will be able to use the brand center app.

If you defer Public CDN during setup and later want to use brand fonts, a Global Administrator can enable Public CDN from the brand center settings in the Microsoft 365 admin center.

## Managing the brand center

The SharePoint brand center includes two levels of management: the Microsoft 365 Admin Center and the Brand Center associated SharePoint site. Within the Microsoft 365 Admin Center, the global administrator has control over the enablement of the Brand Center and easy access to the associated site with management in the SharePoint Admin Center.

From the Brand center associated site, [SharePoint site owners](/en-us/sharepoint/site-permissions#site-owners) and [above](/en-us/sharepoint/site-permissions) can update the site permissions in the SharePoint Admin Center such as adding more brand managers to the experience. You can do this by adding members to the site owners’ group. Within the app itself, the brand managers are able to upload and manage their organization’s brand assets.

| Who? | Where? | What? |
| --- | --- | --- |
| Global administrator | Microsoft 365 Admin Center | - Enablement of the brand center  -Access to the SharePoint Admin Center of the brand center site |
| - Global administrator- Site administrator- Site owner | SharePoint Admin Center | Update permissions |

## Managing brands in Multi-geo organizations

One of the challenges of managing brand assets across geographies is ensuring consistency and compliance with local regulations and cultural preferences. Brand managers need to be able to adapt their brand assets to different markets and languages, while still maintaining a unified and recognizable brand identity.

The SharePoint brand center currently only creates a single brand center app in the primary geo of a tenant. We haven’t changed anything about how this impacts the current multi-geo operations for Organization Asset Image or Template Libraries. However, for custom fonts to work across geographies, the following requirements must be met:

> 
> Each additional geography where custom fonts are wanted must have an organization asset library set up in a site that uses the Public CDN. Once these requirements are met, custom fonts show up in the **Change the Look** panel and will work in that geography.

Note

This does not impact Organization Asset Image Libraries and Template Libraries.

## Brand Assets

Every organization has a set of brand assets that are important for expressing its brand identity. Brand assets are the things that give your brand its distinctive look, sound, and feel. They include your logo, colors, fonts, images, voice, and guidelines. You use your brand assets to show your brand personality and style in all the places where you communicate with your customers, such as websites, social media, marketing materials, presentations, and products. When you use your brand assets well, you make your brand more memorable, trustworthy, and unique.

One of the challenges of managing brand assets is to ensure consistency and quality across different platforms and devices. You want your brand to look sharp and professional everywhere, without spending too much time and effort on resizing, formatting, or providing appropriate access to your users.

The SharePoint brand center makes the management of brand assets simple across the Microsoft 365 product ecosystem. This centralized management system enables both asset management along with customization for how the assets are utilized within each product.

### Brand Images

SharePoint offers a feature called the organization asset library (OAL), which allows you to store and access your brand images from a central location. You can upload and manage your organization's logos, icons, backgrounds, and other images in a centralized library that can be accessed by all your users. This way, you can ensure that your team members have access to the latest and most relevant images that reflect your brand identity and message. You can also use organization assets to create templates and themes that incorporate your images and fonts, making it easy to create professional and consistent slides and documents.

Learn more about [image asset management](/en-us/sharepoint/organization-assets-library).

### Brand Fonts

A font isn't just a way of writing. It's a visual feature that connects your content to your brand and expresses your tone and character. A font can give your content a professional, creative, friendly, or authoritative appearance, depending on the typeface, size, color, and spacing you use.

For SharePoint experiences, an organization uses the SharePoint brand center to control your organization’s fonts. This helps you make sure that your font selections are coherent and match your brand identity and guidelines.

Brand fonts require Public CDN because SharePoint uses it to host font files. If Public CDN isn't enabled, a Global Administrator must enable it before brand managers can add fonts.

Learn more about [brand fonts in the SharePoint brand center](/en-us/sharepoint/brand-fonts).

Organization font support for PowerPoint for the web is also available utilizing the organization assets infrastructure. Customers with E3 or E5 licenses can take advantage of Organization Font Support in PowerPoint for the web to edit and display their fonts.

Learn more about [brand organization fonts for PowerPoint for the web](/en-us/sharepoint/support-for-organization-fonts-in-powerpoint-for-the-web).