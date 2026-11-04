---
layout: Conceptual
title: Set default organization version limits - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/set-default-org-version-limits
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: rekamath
ms.author: ruihu
author: maggierui
manager: jtremper
ms.date: 2024-10-03T00:00:00.0000000Z
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
search.appverid:
- SPO160
- SPS150
- MET150
description: This article provides guidance on how admins can set default organization version limits for new document libraries and OneDrive accounts.
locale: en-us
document_id: 3899cd39-e62d-ab2a-ad57-047a3d74141d
document_version_independent_id: fb5724f6-6b20-623f-1230-352a496e8690
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/set-default-org-version-limits.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: set-default-org-version-limits
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/set-default-org-version-limits.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/c0439c36-80e3-415f-8e4c-6951e3f1b136
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/2812d699-d85f-4a7f-839d-44e218b35d24
platformId: 27f73168-0717-78af-5bf6-2fc3487f04cc
---

# Set default organization version limits - SharePoint in Microsoft 365 | Microsoft Learn

Organization-level version settings define the default version storage limits that apply on all new document libraries created across all existing or newly created SharePoint sites and new OneDrive Accounts. This setting allows admins to define the global default version history limits that apply across the organization to ensure consistent version storage use and restore options.

**Example Scenario**

Take an example of Contoso with an existing marketing site with a set of libraries set to 500 major version limits. When the admin updates the organization version limits to 'Automatic' library, version limits for document libraries are set in the following ways:

- **Library version limits on existing marketing site**: Version limits on all new libraries created in the marketing site are set to the organization limits of Automatic. Version limits on existing libraries remain unchanged that is, limits aren't updated to Automatic.
- **Library version limits on new legal site**: When a new legal site is created, version limits on all libraries created on the legal site are set to the organization version limits.

[![Diagram of break inheritance.](sharepointonline/media/version-history/break-inheritance-at-site-level.png)](sharepointonline/media/version-history/break-inheritance-at-site-level.png#lightbox)

Important

- Changes made to organization-level version history limits apply to new SharePoint libraries and OneDrive user accounts created since the change was made. The changes can take upto 24 hours to be reflected on new libraries created.
- Changes made to organization-level version history limits will not update the limits applied to existing document libraries. To update the existing library settings, you can [set version limits for existing libraries on a site](site-version-limits) or [set version limits on a library](library-version-limits). The ability to apply version history limits to existing document libraries at the organization level is not supported.
- Changes made to the organization-level version history limits will not trim existing version history to the new limits. To delete existing versions, you can [trim existing versions from a site, library or OneDrive](library-version-limits#manage-version-history-limits-for-a-library-using-powershell). The ability to trim existing versions at the organization level is not supported.
- Default Version History limits for your organization is set to Manual version history limits with 500 major version count limit and no expiration.
- Organization-level Document Library version limit settings can be used to configure version settings on libraries only ([List template Base Type = 1](/en-us/openspecs/sharepoint_protocols/ms-wssts/8bf797af-288c-4a1d-a14b-cf5394e636cf)). List version settings, creation of major and minor versions, or content approval workflows need to be [configured at individual library or list level](https://support.microsoft.com/en-us/office/enable-and-configure-versioning-for-a-list-or-library-1555d642-23ee-446a-990a-bcab618c7a37).
- If your organization is configured for multi-geo, the Organization level version history levels can be set for each geo.

## Manage version history limits for your organization

This article describes how global and SharePoint admins in Microsoft 365 can change the default version history limits for all new SharePoint document libraries and OneDrive accounts created in the organization.

[![Diagram of sharepoint admin settings.](sharepointonline/media/version-history/sharepoint-admin-settings-2.png)](sharepointonline/media/version-history/sharepoint-admin-settings-2.png#lightbox)

On the version history limits, SharePoint Admin Setting page uses the Organization Level Version History Limits to set global default version history limits that are universally applied to all newly created document libraries in the organization.

[![Diagram of set version history limits.](sharepointonline/media/version-history/set-version-his-lim-2.png)](sharepointonline/media/version-history/set-version-his-lim-2.png#lightbox)

## Set automatic version history limits for the organization

1. Go to **Settings** in the [SharePoint admin center](/en-us/sharepoint/sharepoint-admin-role), and sign in with an account that has [administrator permissions](/en-us/sharepoint/sharepoint-admin-role) for your organization.
2. Select **Version History limits**.
3. Select **Automatically**.
4. Select **Save** and **Confirm** to apply the changes to all new libraries created.

[![Diagram of automatic version history limits.](sharepointonline/media/version-history/version-history-limits-automatic.png)](sharepointonline/media/version-history/version-history-limits-automatic.png#lightbox)

To set Automatic version history limits for all new document libraries created in your organization using PowerShell, run the following command:

```PowerShell
Set-SPOTenant -EnableAutoExpirationVersionTrim $true
```

## Set manual version count limits with no expiration

1. Go to **Settings** in the [SharePoint admin center](/en-us/sharepoint/sharepoint-admin-role), and sign in with an account that has [administrator permissions](/en-us/sharepoint/sharepoint-admin-role) for your organization.
2. Select **Version history limits**.
3. Select **Manually**.
4. Enter a value between 100 and 50,000 in the **Number of major versions** box.
5. Set the **Delete versions after this period of time** drop-down option to '**Never**.' This setting ensures that no expiration is stamped on versions.
6. Select **Save** and **Confirm** to apply the changes to all new libraries created.

[![Screenshot of manual version count limits with no expiration.](sharepointonline/media/version-history/version-history-limits-manual.png)](sharepointonline/media/version-history/version-history-limits-manual.png#lightbox)

## Set manual version count and expiration storage limits

To set count and expiration limits for all new document libraries created in your organization using SharePoint admin center:

1. Go to **Settings** in the [SharePoint admin center](/en-us/sharepoint/sharepoint-admin-role), and sign in with an account that has [administrator permissions](/en-us/sharepoint/sharepoint-admin-role) for your organization.
2. Select **Version history limits**.
3. Select **Manually**.
4. Enter a value between 100 and 50,000 in the **Number of major versions** box.
5. Select one of the preset values for **Delete versions after this period of time** drop-down option. or
6. To enter a custom value for **Delete versions after**, select the custom value from the dropbox and enter value greater than 30 days in the **Days** box and **Save**.
7. Select **Save** and **Confirm** to apply the changes to all new libraries created.

To set count and expiration limits for all new document libraries created in your organization using PowerShell, run the following command:

```PowerShell
Set-SPOTenant `
    -EnableAutoExpirationVersionTrim $false `
    -MajorVersionLimit <int> `
    -ExpireVersionsAfterDays <int, 0 for no expiration>
```

## Set file type version limit

Currently only PowerShell is supported. You can run Set-SPOTenant with the [FileTypesForVersionExpiration](/en-us/powershell/module/sharepoint-online/set-spotenant#-filetypesforversionexpiration) argument to change the limit for a specific file type.

For example, to set the version limit for audio and video files to a manual limit of 100 major versions and 30-day time limit, run the following command:

```PowerShell
Set-SPOTenant `
    -MajorVersionLimit 100 `
    -ExpireVersionsAfterDays 30 `
    -EnableAutoExpirationVersionTrim $false `
    -FileTypesForVersionExpiration @("audio", "video")
```

Or you can remove a file type version limit override by using the [RemoveVersionExpirationFileTypeOverride](/en-us/powershell/module/sharepoint-online/set-spotenant#-removeversionexpirationfiletypeoverride) argument.

For example, to remove the audio file type override, run the following command:

```PowerShell
Set-SPOTenant -RemoveVersionExpirationFileTypeOverride @("audio")
```

## Review organization version storage limits

To review the default version history limits for all new document libraries using SharePoint admin center:

1. Go to **Settings** in the [SharePoint admin center](/en-us/sharepoint/sharepoint-admin-role), and sign in with an account that has [administrator permissions](/en-us/sharepoint/sharepoint-admin-role) for your organization.
2. Select **Version history limits**.

To review the default version history limits for all new document libraries using PowerShell, run the following command:

```PowerShell
Get-SPOTenant | select EnableAutoExpirationVersionTrim, ExpireVersionsAfterDays, MajorVersionLimit
```

To review a file type version limit, select VersionPolicyFileTypeOverride property from the result of Get-SPOTenant. For example, to review the audio file type version limits, run the following command:

```PowerShell
(Get-SPOTenant).VersionPolicyFileTypeOverride["audio"]
```

## Learn More

For more information, check out the following resources:

- [Manage Version History Limits for your Organization using Set-SPOTenant](/en-us/powershell/module/sharepoint-online/set-spotenant)
- [File Type Version Limits](file-type-version-limits)