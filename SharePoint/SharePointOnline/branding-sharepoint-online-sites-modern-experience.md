---
layout: Conceptual
title: Branding your SharePoint site - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/branding-sharepoint-online-sites-modern-experience
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-06-24T00:00:00.0000000Z
ms.reviewer: cathed
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
ms.collection:
- Strat_SP_modern
- M365-collaboration
- enabler-strategic
- m365initiative-spsites
ms.custom:
- seo-marvel-apr2020
search.appverid:
- SPO160
- MET150
description: Learn about branding your sites in the SharePoint modern experience to match your company or organizational brand.
locale: en-us
document_id: fe029ff2-3230-3320-aef5-9f16ab9464cc
document_version_independent_id: d791f3f6-257f-9a9b-461f-a12693d4bfde
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/branding-sharepoint-online-sites-modern-experience.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: branding-sharepoint-online-sites-modern-experience
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/branding-sharepoint-online-sites-modern-experience.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: b9dd9d52-20de-4c03-73ca-303687bf5a79
---

# Branding your SharePoint site - SharePoint in Microsoft 365 | Microsoft Learn

In the modern SharePoint experience, you can easily [change the look](https://support.office.com/article/06bbadc3-6b04-4a60-9d14-894f6a170818) and feel of your site to match your company or organizational brand. You can customize the logo, colors, and navigation – often without writing a single line of code. Branding can be applied at the site level, to a group of sites, or to all sites within your organization.

![Branding site](sharepointonline/media/branding-sharepoint-online-sites-modern-experience_image1.png)

Note

Branding your SharePoint site will not change the overall look of your Microsoft 365 service. For more info about branding Microsoft 365, see [Customize the Microsoft 365 theme for your organization](/en-us/office365/admin/setup/customize-your-organization-theme).

## Site branding in the classic experience

In the classic SharePoint experience, there's a set of default themes that can require a considerable amount of customization to get them to match your organization's brand. Also, they aren't responsive, making the experience on different devices inconsistent. Most site branding requires the use of custom master pages or alternate CSS configurations. Master pages provide a great deal of flexibility, but they can be problematic. For example, anytime updates are made to SharePoint, any customizations made to the master page may no longer work or may not work the way you expect them to. SharePoint [ignores these customizations](/en-us/sharepoint/dev/transform/modernize-branding) unless you're running in classic experience mode because they're incompatible with the modern user interface. To avoid this situation, use only the recommended modern approaches to brand your SharePoint sites.

## Modern site branding

SharePoint includes an updated set of default site themes that are responsive and look great on any device. With site themes, you can customize your site's logo and colors to match your brand. Site templates provide specific layouts and other functionality for your site. More branding can be achieved using custom themes or site templates without worrying about something breaking when SharePoint is updated. [Custom themes](/en-us/sharepoint/dev/declarative-customization/site-theming/sharepoint-site-theming-overview) let you create more color schemes beyond the defaults. [Custom site templates](/en-us/sharepoint/dev/declarative-customization/site-design-overview) let you control the site theme and other customizations like the site navigation, default applications, and other settings. Custom themes or site templates can be applied to a new site when it's created or applied to an existing site or group of sites.

### Branding hub sites

When you brand a [SharePoint hub site](https://support.office.com/article/fe26ae84-14b7-45b6-a6d1-948b3966427f), you can set it so the site branding is applied to any sites that [associate with it](https://support.office.com/article/ae0009fd-af04-4d3d-917d-88edb43efc05). This includes any site theme or site template used by the hub site. This allows you to apply common navigation and branding across a set of sites and use accent colors to emphasize elements that need to stand out.

Note

Custom themes and logos in SharePoint *does not* automatically apply to group-connected team sites that are associated to a hub that has a custom theme applied. For group-connected team sites, you need to manually apply the custom theme or logo.

## Classic experience vs. modern experience

The following is a summary of the differences between branding a site in the classic experience vs. branding in the modern SharePoint experience.

| Classic experience | Modern experience |
| --- | --- |
| Unresponsive, OOB themes that you can customize | Responsive themes that look great on any device and can be customized to match your brand |
| Use custom master pages and CSS that are ignored in the modern experience | Use the [SharePoint Framework](/en-us/sharepoint/dev/spfx/sharepoint-framework-overview) to add headers and footers. Site templates and tenant settings offer some custom options |

## Before you begin

Some things to consider before branding your classic experience sites in SharePoint are:

- Do you need a consistent brand across all sites or will different divisions, departments, or groups in your organization have their own?
- You should compile a list of all current sites, what site templates they use, any customizations that have been made to the master pages or CSS, and decide which of these customizations you need to keep. You can run the [SharePoint "Modern" user interface experience scanner](https://github.com/SharePoint/PnP-Tools/tree/master/Solutions/SharePoint.UIExperience.Scanner) which does a deep analysis of all the sites in your organization and create reports that give you details about sites that have incompatible master pages or alternate CSS settings. [SharePoint handles branding differently](/en-us/sharepoint/dev/transform/modernize-branding) for classic site templates such as the publishing site. You want to [troubleshoot any custom theme issues](/en-us/sharepoint/dev/declarative-customization/site-theming/sharepoint-site-theming-overview#troubleshoot-custom-theme-issues) you run into.
- What areas do you want to customize (logo, colors, fonts, header/footer, navigation)?
- Who in your organization can brand a site? You'll need to make sure that they have site designer permissions or above to make these changes.

## Ready to brand your classic SharePoint site using the modern experience?

Check out the below resources that provide more details about how to use the modern SharePoint experience to brand your site.

[Change the look of your SharePoint site.](https://support.office.com/article/06bbadc3-6b04-4a60-9d14-894f6a170818)

[SharePoint site theming](/en-us/sharepoint/dev/declarative-customization/site-theming/sharepoint-site-theming-overview)

[Modernize site branding.](/en-us/sharepoint/dev/transform/modernize-branding)

[Modernize your classic SharePoint sites.](/en-us/sharepoint/dev/transform/modernize-classic-sites)

[JSON schema](/en-us/sharepoint/dev/declarative-customization/site-theming/sharepoint-site-theming-json-schema)