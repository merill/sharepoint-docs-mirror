---
layout: Conceptual
title: Switch between an Enterprise Search Center and Basic in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/switch-from-enterprise-search-center-to-basic
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
ms.date: 2024-10-07T00:00:00.0000000Z
audience: Admin
f1.keywords:
- NOCSH
ms.topic: upgrade-and-migration-article
ms.service: sharepoint-online
ms.subservice: admin
ms.collection: M365-collaboration
ms.localizationpriority: medium
search.appverid:
- MET150
description: Learn how to swap your default search center from Enterprise back to Basic and vice versa.
locale: en-us
document_id: e3e4a666-0135-e88b-a13d-cde7265e653c
document_version_independent_id: 6e8f4af8-1f2c-c98e-e5a6-94150b59573d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/switch-from-enterprise-search-center-to-basic.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: switch-from-enterprise-search-center-to-basic
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/switch-from-enterprise-search-center-to-basic.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 99c4c9bf-911a-52e9-89e2-fa0e7025e653
---

# Switch between an Enterprise Search Center and Basic in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn

The Basic Search Center is a classic search experience. To offer your users a richer search experience, you can do one of the two things:

- Switch from a Basic Search Center to an Enterprise Search Center
- Rely on the modern search experience that SharePoint comes with. [Learn about differences between classic and modern search](differences-classic-modern-search) and [when to choose which search experience](get-started-with-modern-search-experience) for your organization.

If you're currently using the Enterprise Search Center, you can easily replace (swap) it with the Basic Search Center if needed. The swap results in your users seeing the classic search experience in their default search home page and default search results page. You can use the [Invoke-SPOSiteSwap](/en-us/powershell/module/sharepoint-online/invoke-spositeswap) PowerShell cmdlet to swap.

## How to use Invoke-SPOSiteSwap to swap your Search Center sites

1. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    Note

    If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell."
2. Connect to SharePoint as a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
3. Run the [Invoke-SPOSiteSwap](/en-us/powershell/module/sharepoint-online/invoke-spositeswap) cmdlet.

    ```PowerShell
    Invoke-SPOSiteSwap  
      -SourceUrl <string>
      -TargetUrl <string>
      -ArchiveUrl <string>
    ```

| Parameter | Description |
| --- | --- |
| -SourceUrl | The site you want to promote. |
| -TargetUrl | The site you want to replace. |
| -ArchiveUrl | URL that the target site is archived to. |

Here's an example of how to use these parameters when swapping an existing Enterprise Search Center to Basic:

- **For your -SourceUrl**, you need the URL of your Basic Search Center site. The site must exist before running the cmdlet. For our example, we use &lt;spam&gt;&lt;spam&gt;https://contoso.sharepoint.com/sites/SiteSearch&lt;spam&gt;&lt;spam&gt;.

You can [create a Basic Search Center site](https://support.office.com/article/449eccec-ff99-4cf3-b62e-dcfee37e8da4) from an Enterprise site template.

- **For your -TargetUrl**, you need the URL of your Enterprise Search Center site that you want to replace. For our example, we use &lt;spam&gt;&lt;spam&gt;https://contoso.sharepoint.com/search&lt;spam&gt;&lt;spam&gt;.
- **For your -ArchiveUrl**, use a Url that doesn't currently exist at the location. Your Enterprise Search Center site is archived to this site location. For our example, we use &lt;spam&gt;&lt;spam&gt;https://contoso.sharepoint.com/sites/ArchivedEntSearch&lt;spam&gt;&lt;spam&gt;.

Here's how to use the examples in the Invoke-SPOSiteSwap cmdlet:

```PowerShell
Invoke-SPOSiteSwap -SourceUrl https://contoso.sharepoint.com/sites/SearchSite -TargetUrl https://contoso.sharepoint.com/search -ArchiveUrl https://contoso.sharepoint.com/sites/ArchivedEntSearch
```

Successfully running the cmdlet would result in:

- Basic Search is the default Search Center experience. When users go to &lt;spam&gt;&lt;spam&gt;https://contoso.sharepoint.com/search&lt;spam&gt;&lt;spam&gt;, they're now using the Basic Search Center.
- The Enterprise Search Center site is no longer available as the default Search Center experience.