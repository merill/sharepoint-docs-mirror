---
layout: Conceptual
title: Block download policy for SharePoint sites and OneDrive - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/block-download-from-sites
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-05-14T00:00:00.0000000Z
ms.reviewer: samust
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
customer-intent: As a SharePoint Administrator, I want to block download of files from SharePoint sites and OneDrive to prevent data loss.
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Strat_SP_admin
- Highpri
- Tier2
- M365-sam
- M365-collaboration
- trust-pod
search.appverid:
- SPO160
- MET150
- BSA160
description: Learn how administrators can block download of files from a SharePoint and OneDrive without using conditional access policies.
locale: en-us
document_id: acbfb458-2ccd-84ed-b5dd-9493f6d5c003
document_version_independent_id: a7db833e-2f56-e147-8f84-ccf1a86ed71a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/block-download-from-sites.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: block-download-from-sites
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/block-download-from-sites.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
platformId: f0a28de9-f3fd-b0ea-230f-e529b54ad46c
---

# Block download policy for SharePoint sites and OneDrive - SharePoint in Microsoft 365 | Microsoft Learn

As a SharePoint Administrator in Microsoft 365, you can use the PowerShell ([Set-SPOSite](/en-us/powershell/module/microsoft.online.sharepoint.powershell/set-sposite?view=sharepoint-ps&amp;preserve-view=true)) to block the download of files from SharePoint sites or OneDrive. This feature allows you to control access without using Microsoft Entra Conditional Access policies. You can set this feature for individual sites, but not at the organization level.

When you deploy a policy to block downloads from SharePoint sites or OneDrive, it also prevents users from moving files to other SharePoint sites. File moves are also blocked through other means, such as by using Power Automate or Quick Steps.

Blocking file downloads allows users to remain productive while reducing the risk of accidental data loss. Users have browser-only access with no ability to download, print, or sync files. They also can't access content through apps, including the Microsoft 365 Apps (like Word, Excel, PowerPoint, and so on). When web access is limited, users see this message at the top of sites, "Your organization doesn't allow you to download, print, or sync from this site. For help, contact your It department."

You can also block the download of Microsoft Teams meeting recording files. See [Block the download of Teams meeting recording files from SharePoint or OneDrive](/en-us/microsoftteams/block-download-meeting-recording).

## Before you begin

Make sure your organization meets the [SharePoint Advanced Management prerequisites](sharepoint-advanced-management-prerequisites), including requirements for [SharePoint Online PowerShell module](sharepoint-advanced-management-prerequisites#sharepoint-online-powershell-module).

## Use PowerShell to set a block downloads policy

In PowerShell, run the following command:

```PowerShell
Set-SPOSite -Identity <SiteURL> -BlockDownloadPolicy $true
```

Here's an example showing a site URL:

```powershell
Set-SPOSite -Identity https://contoso.sharepoint.com/sites/research -BlockDownloadPolicy $true
```

To apply this command to OneDrive, change the URL, as shown in the following example:

```powershell
Set-SPOSite -Identity https://contoso-my.sharepoint.com/personal/John -BlockDownloadPolicy $true
```

You can use certain parameters with this command, as shown in the following examples:

### Example 1: Exclude site owners from the policy so they can download content from the site

```powershell
Set-SPOSite -Identity <SiteURL> -BlockDownloadPolicy $true -ExcludeBlockDownloadPolicySiteOwners $true
```

### Example 2: Exclude users in specific groups using group IDs so they can download content from the site

```powershell
Set-SPOSite -Identity <SiteURL> -BlockDownloadPolicy $true -ExcludedBlockDownloadGroupIds <comma separated group IDs>
```

### Example 3: Exclude users in specific groups by group name so they can download content from the site

```powershell
Set-SPOSite -Identity <SiteURL> -BlockDownloadPolicy $true -ExcludeBlockDownloadSharePointGroups <comma separated group names>
```

### Example 4: Mark a site as read-only in addition to preventing downloads from the site

```powershell
Set-SPOSite -Identity <SiteURL> -BlockDownloadPolicy $true -ReadOnlyForBlockDownloadPolicy $true`
```

### Example 5: Attach the block download policy to a site sensitivity label

```PowerShell
Set-Label -Identity 'Internal' -AdvancedSettings @{BlockDownloadPolicy="true" | "false" }
```

## Understand how blocking downloads can affect apps

Blocking download might affect the user experience in some apps, including some Office apps. We recommend that you turn on the policy for some users and test the experience with the apps used in your organization. In Office, make sure to check the behavior in Power Apps and Power Automate when your policy is on.

Note

Apps that run in "app-only" mode in the service, like antivirus apps and search crawlers, are exempted from the policy.

If you're using classic SharePoint site templates, site images might not render correctly. This issue can occur because the policy prevents the original image files from being downloaded to the browser.

## Need more help?

[SharePoint Question & Answers](/en-us/answers/topics/office-sharepoint-online.html)

## Related article

[Configure a default sensitivity label for a SharePoint document library](/en-us/microsoft-365/compliance/sensitivity-labels-sharepoint-default-label)