---
layout: Conceptual
title: Best practices for changing site creation time zone display in SharePoint admin center - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/caution-changing-time-zone-sharepoint-admin-center
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
description: Learn the best practices for changing the displayed creation time zone of the Active sites page in the SharePoint admin center.
author: maggierui
manager: dansimp
ms.author: ruihu
ms.service: sharepoint-online
ms.subservice: admin
ms.topic: best-practice
ms.date: 2025-10-22T00:00:00.0000000Z
audience: Admin
customer intent: As a SharePoint admin, I want to change the displayed creation time zone of the Active sites page in the SharePoint admin center so that it reflects the correct time zone for my organization.
f1.keywords: NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SP_admin
- Highpri
- Tier2
- M365-sam
- M365-collaboration
search.appverid: 
locale: en-us
document_id: a1a5b80f-eb7e-3429-5636-5bf00dd34384
document_version_independent_id: 1c593a2c-94eb-950e-dc24-e5b522f1c650
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/caution-changing-time-zone-sharepoint-admin-center.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: caution-changing-time-zone-sharepoint-admin-center
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/caution-changing-time-zone-sharepoint-admin-center.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: d58ade82-0d9e-8d44-e711-54cf3a85c1fa
---

# Best practices for changing site creation time zone display in SharePoint admin center - SharePoint in Microsoft 365 | Microsoft Learn

As a SharePoint admin, sometimes you may have the need to change the displayed creation time zone of the **Active sites** page in the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219). Instead of changing the time zone setting of the SharePoint admin center itself, we recommend using [user-level settings](https://support.microsoft.com/office/change-your-personal-language-and-region-settings-caa1fccc-bcdb-42f3-9e5b-45957647ffd7) for time zone and locale change.

[![Screenshot showing creation dates in SharePoint admin center.](sharepointonline/media/spac/creation-dates-sharepoint-admin-center.png)](sharepointonline/media/spac/creation-dates-sharepoint-admin-center.png#lightbox)

## What can happen when you change the time zone in SharePoint admin center

You can change the time zone for the SharePoint admin center by adding `"_layouts/15/regionalsetting.aspx"` to the end of your admin center URL. For example: `https://contoso-admin.sharepoint.com/_layouts/15/regionalsetting.aspx`.

By default, the SharePoint admin center uses Pacific Time (PST). When you create a new SharePoint site, it inherits the current time zone setting from the admin center. If you change the time zone of the SharePoint admin center after sites have already been created, new sites will use the updated time zone, but existing sites will keep their original time zone for creation dates. This can lead to confusion and reporting issues, as older sites may display creation timestamps based on the previous time zone, while newer sites reflect the new setting.

## What we recommend: use user-level settings for Time Zone and Locale

To avoid time stamp misalignments on the **Active sites** page in SharePoint admin center, we recommend using [user-level settings](https://support.microsoft.com/office/change-your-personal-language-and-region-settings-caa1fccc-bcdb-42f3-9e5b-45957647ffd7) for time zone and locale instead of directly changing the SharePoint admin center's time zone settings. User-level time zone and locale settings affect how times are displayed in Outlook, SharePoint, and other Microsoft 365 services.

Note

If your organization enforces tenant-level time zone settings, personal changes may be overridden. Changes may take a few minutes to propagate across services.