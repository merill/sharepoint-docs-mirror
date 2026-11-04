---
layout: Conceptual
title: Required URLs and ports for OneDrive consumer - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/required-urls-and-ports
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: 
ms.author: v-mactran
author: MachelleTranMSFT
manager: jtremper
ms.date: 2025-03-27T00:00:00.0000000Z
audience: Admin
f1.keywords:
- NOCSH
ms.topic: reference
ms.service: onedrive
ms.localizationpriority: medium
ms.collection: M365-collaboration
search.appverid:
- ODC160
- MET150
ms.custom: onedrive-toc
ms.assetid: ce15d2cc-52ef-42cd-b738-d9c6f9b03f3a
description: Learn the FQDNs and ports to include in your allowlists to let users use the consumer version of OneDrive.
locale: en-us
document_id: 354754c2-453b-2e32-84ae-81b27c358a40
document_version_independent_id: 9b549240-2f83-fcf4-6cb7-bebd3a6fd65d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/required-urls-and-ports.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: required-urls-and-ports
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/required-urls-and-ports.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/54918a83-0404-4863-9c91-715186c1f582
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/b26f5f7a-0913-4a95-8337-ed7543902f2d
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: f0db2598-2a32-1e36-7291-6c3403cc9db9
---

# Required URLs and ports for OneDrive consumer - SharePoint in Microsoft 365 | Microsoft Learn

This reference article lists all endpoints used by the consumer version of Microsoft OneDrive. If your organization restricts computers on your network from connecting to the Internet, this article lists the Fully Qualified Domain Names (FQDNs) and ports that you should include in your outbound allowlist to ensure your computers can successfully use the consumer version of OneDrive.

Important

Filtering internet traffic requires advanced networking knowledge and isn't suitable for all customers.

**If you are looking for a listing of endpoints used by OneDrive in Microsoft 365, see [Microsoft 365 URLs and IP address ranges](/en-us/office365/enterprise/urls-and-ip-address-ranges).**

## Supported hosts and ports for OneDrive

To use OneDrive, the following endpoints need to be accessible to client computers.

| **Row** | **Destination host** | **Destination Port** |
| --- | --- | --- |
| 1 | onedrive.com  \*.onedrive.com  onedrive.live.com  login.live.com  g.live.com  spoprod-a.akamaihd.net  \*.mesh.com  p.sfx.ms  oneclient.sfx.ms  \*.microsoft.com  fabric.io  \*.crashlytics.com  vortex.data.microsoft.com  posarprodcssservice.accesscontrol.windows.net  redemptionservices.accesscontrol.windows.net  token.cp.microsoft.com/  tokensit.cp.microsoft-tst.com/  \*.office.com  \*.officeapps.live.com  \*.aria.microsoft.com  \*.mobileengagement.windows.net  \*.branch.io  \*.adjust.com  \*.servicebus.windows.net  vas.samsungapps.com  odc.officeapps.live.com  login.windows.net  login.microsoftonline.com | TCP 80, TCP 443 |
| 2 | \*.files.1drv.com  \*.onedrive.live.com  \*.\*.onedrive.live.com  storage.live.com  \*.storage.live.com  \*.\*.storage.live.com  \*.groups.office.live.com  \*.groups.photos.live.com  \*.groups.skydrive.live.com  favorites.live.com  oauth.live.com  photos.live.com  skydrive.live.com  api.live.net  apis.live.net  docs.live.net  \*.docs.live.net  policies.live.net  \*.policies.live.net  settings.live.net  \*.settings.live.net  skyapi.live.net  snapi.live.net  \*.livefilestore.com  \*.\*.livefilestore.com  storage.msn.com  \*.storage.msn.com  \*.\*.storage.msn.com | TCP 80, TCP 443 |