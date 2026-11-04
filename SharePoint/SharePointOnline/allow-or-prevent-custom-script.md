---
layout: Conceptual
title: Allow or prevent custom scripts in SharePoint sites - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/allow-or-prevent-custom-script
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: lucaband
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 2026-02-03T00:00:00.0000000Z
audience: Admin
f1.keywords:
- CSH
ms.topic: how-to
ms.custom:
- O365M_NoScript
- O365E_NoScript
- admindeeplinkSPO
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- M365-sam
search.appverid:
- SPO160
- ODB160
- ODB150
- BSA160
- MET150
description: Learn how to allow or block custom scripts on SharePoint sites to manage security and enable or restrict advanced features for your organization.
locale: en-us
document_id: aa561c35-c73d-32d1-a553-5c96ce179a8c
document_version_independent_id: 819af39f-8ee0-e7f8-f591-09d464225e50
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/allow-or-prevent-custom-script.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: allow-or-prevent-custom-script
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/allow-or-prevent-custom-script.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 7d7eddad-94b1-6630-c8b1-af8ec334a53c
---

# Allow or prevent custom scripts in SharePoint sites - SharePoint in Microsoft 365 | Microsoft Learn

As a [SharePoint Administrator](sharepoint-admin-role) in Microsoft 365, you can temporarily allow the use of custom scripts in SharePoint sites. By using custom scripts, users can operate with some classic features, like using the script editor web part. Users can also change the look, feel, and behavior of sites and pages to meet organizational objectives or individual needs.

If you allow custom script, all users who have *Add and Customize Pages* permission to a site or page can add any script they want. By default, users who create sites are site owners and, therefore, have this permission.

Note

For simple ways for users to change the look and feel of a site, see [Change the look of your SharePoint site](https://support.office.com/article/06bbadc3-6b04-4a60-9d14-894f6a170818).

By default, SharePoint doesn't allow script on most sites that administrators create by using the SharePoint admin center and on all sites that are created by using the [New-SPOSite PowerShell command](/en-us/powershell/module/microsoft.online.sharepoint.powershell/new-sposite?view=sharepoint-ps&amp;preserve-view=true). The same restriction also applies to OneDrive, sites that users create themselves, modern team and communication sites, and the root site for your organization. For more information about the security implications of custom script, see [Security considerations of allowing custom script](security-considerations-of-allowing-custom-script).

Important

If your organization's SharePoint deployment was done before 2015, your custom script settings might still be set to *Not Configured*, even if, in the SharePoint admin center, they appear to be set to prevent users from running custom script. In this case, users can't copy items between SharePoint sites and between OneDrive and SharePoint. On the [Settings page in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185072), to accept the custom script settings as they appear, select **OK**, and enable cross-site copying. For more information about copying items between OneDrive and SharePoint, see [Copy files and folders between OneDrive and SharePoint sites](https://support.office.com/article/67a6323e-7fd4-4254-99a8-35613492a82f).

## How do I temporarily allow custom script on SharePoint sites?

Caution

Before you allow custom script on sites in your organization, make sure you understand the [security implications](security-considerations-of-allowing-custom-script).

To allow custom script on a particular site (previously called a *site collection*) immediately, follow these steps:

1. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    Note

    If you installed a previous version of the SharePoint Online Management Shell, go to **Add or remove programs** and uninstall **SharePoint Online Management Shell**.
2. Connect to SharePoint as a [SharePoint Administrator](sharepoint-admin-role) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
3. Run the following command.

    ```PowerShell
    Set-SPOSite <SiteURL> -DenyAddAndCustomizePages 0
    ```

    Or, use the [Set-PnPSite PowerShell cmdlet](https://pnp.github.io/powershell/cmdlets/Set-PnPSite.html) as follows:

    ```PowerShell
    Set-PnPSite -Identity <SiteURL> -NoScriptSite $false
    ```

Changes to allow custom scripts are overridden to *Not allowed* within 24 hours.

Note

You can't allow custom scripts on an individual user's OneDrive.

## How do I permanently block new custom scripts in OneDrive and SharePoint sites?

Turn on [Baseline security mode settings](/en-us/microsoft-365/baseline-security-mode/baseline-security-mode-settings).

## How do I manage custom scripts in the SharePoint admin center?

As a SharePoint administrator, use the SharePoint admin center to manage custom scripts within your organization.

1. Identify the sites that are configured to use custom scripts.
2. Change custom script settings for each site, as appropriate for your organiztion.

Alternately, you can turn on [Baseline security mode settings](/en-us/microsoft-365/baseline-security-mode/baseline-security-mode-settings) and block new custom scripts across OneDrive and SharePoint sites at once.

### Identify sites that allow custom scripts

Use the SharePoint admin center to identify SharePoint sites that are configured to allow custom scripts.

1. In the SharePoint admin center, under **Sites**, select **Active sites**.
2. Look for the **Custom script** column.

    [![Screenshot of active sites view with custom script column visible.](sharepointonline/media/232a2283-7f38-4f77-b32d-e076bbcbbb01.png)](sharepointonline/media/232a2283-7f38-4f77-b32d-e076bbcbbb01.png#lightbox)

    If you don't see the **Custom script** column in the list of sites, add it to any view.

    The **Custom script allowed sites** view is also available to provide easy access to all sites where custom script is enabled:

    [![Screenshot of the list of default views, which includes the 'custom script allowed sites' view.](sharepointonline/media/e19f29a8-601a-416a-b8fd-2f128461b52c.png)](sharepointonline/media/e19f29a8-601a-416a-b8fd-2f128461b52c.png#lightbox)

    These views show which sites are configured to allow custom scripts, even if they don't actually use custom scripts.

### Change custom script settings for a SharePoint site

1. In the SharePoint admin center, under **Sites**, select **Active sites**.
2. On the **Active sites** page, select a site.
3. Under **Settings** &gt; **Custom scripts**, specify whether to allow or block custom scripts.

    [![Screenshot of the 'Custom scripts' setting.](sharepointonline/media/7a9c6b79-db8b-4577-9a8c-978f011196a9.png)](sharepointonline/media/7a9c6b79-db8b-4577-9a8c-978f011196a9.png#lightbox)

You can control custom script settings for a specific site by deciding whether to allow or block custom script:

[![Screenshot showing the custom scripts settings.](sharepointonline/media/allow-or-prevent-custom-script/custom-scripts.png)](sharepointonline/media/allow-or-prevent-custom-script/custom-scripts.png#lightbox)

By default, any changes to custom script settings for a specific site last for a maximum of 24 hours. After that time, the setting resets to **Blocked** for that specific site.

Important

If the site is locked because it's in either the *ReadOnly* or *NoAccess* state, changes to custom scripts settings don't appear in the SharePoint admin center. However, as soon as the state of the site goes back to *Unlock*, custom script settings immediately turn to *Not allowed* before users access the site.

## What features are affected when custom scripts are blocked?

When you block users from running custom scripts on OneDrive or the classic SharePoint team sites they create, site administrators and owners can't create new items, such as templates, solutions, themes, and help file collections. If you previously allowed custom script, items that were already created still work.

The following site settings aren't available when you prevent users from running custom script:

| Site feature | Behavior | Notes |
| --- | --- | --- |
| Save Site as Template | No longer available in Site Settings | Users can still build sites from templates created before custom script was blocked. |
| Save document library as template | No longer available in Library Settings | Users can still build document libraries from templates created before custom script was blocked. |
| Save list as template | No longer available in List Settings | Users can still build lists from templates created before custom script was blocked. |
| Theme Gallery | No longer available in Site Settings | Users can still use themes created before custom script was blocked. |
| Help Settings | No longer available in Site Settings | Users can still access help file collections available before custom script was blocked. |
| Sandbox solutions | Solution Gallery is no longer available in Site Settings | Users can't add, manage, or upgrade sandbox solutions. They can still run sandbox solutions that were deployed before custom script was blocked. |
| SharePoint Designer | Pages that aren't HTML can no longer be updated.  Handling List: **Create Form** and **Custom Action** no longer work.  Subsites: **New Subsite** and **Delete Site** redirect to the **Site Settings** page in the browser.  Data Sources: **Properties** button is no longer available. | Users can still open some data sources. To open a site that doesn't allow custom script in SharePoint Designer, you must first open a site that does allow custom script. |
| Operating files that potentially include script | The following file types can't be uploaded, copied, moved, or opened in a library:`.asmx``.ascx``.aspx``.htc``.jar``.master``.swf``.xap``.xsf` | Existing files in the library aren't impacted. |
| Uploading Documents to Content Types | Access denied message when attempting to attach a document template to a Content Type. | We recommend using Document Library document templates. |
| Publishing of SharePoint 2010 Workflows | Access denied message when attempting to publish a SharePoint 2010 Workflow. |  |
| Custom Actions | Access denied message when attempting to create new custom actions. | Existing custom actions aren't impacted. |
| Design Manager | Access denied message when attempting to create new layout, master page, or design package. | Users can still use page designs created before custom script was blocked. |

By default, you can't update the [Site property bag](/en-us/sharepoint/dev/schema/propertybag-element-property-bag) when you prevent users from running custom scripts. You can change that behavior by running the following command:

```PowerShell
    Set-SPOTenant -AllowWebPropertyBagUpdateWhenDenyAddAndCustomizePagesIsEnabled $True
```

For more information, see [AllowWebPropertyBagUpdateWhenDenyAddAndCustomizePagesIsEnabeld](/en-us/powershell/module/microsoft.online.sharepoint.powershell/set-spotenant) option.

When custom scripts are blocked, the following web parts and features are unavailable to SharePoint site administrators and owners:

| Web part category | Web part |
| --- | --- |
| Business Data | Business Data Actions  Business Data Item  Business Data Item Builder  Business Data List  Business Data Related List  Excel Web Access  Indicator Details  Status List  Visio Web Access |
| Community | About This Community  Join  My Membership  Tools  What's Happening |
| Content Rollup | Categories  Project Summary  Relevant Documents  RSS Viewer  Site Aggregator  Sites in Category  Term Property  Timeline  WSRP Viewer  XML Viewer |
| Document Sets | Document Set Contents  Document Set Properties |
| Advanced | Embed |
| Forms | HTML Form Web Part |
| Media and Content | Content Editor  Script Editor  Silverlight Web Part  Page Viewer (can't set web page URL) |
| Search | Refinement  Search Box  Search Navigation  Search Results |
| Search-Driven Content | Catalog-Item Reuse |
| Social Collaboration | Contact Details  Note Board  Organization Browser  Site Feed  Tag Cloud  User Tasks |
| Master Page Gallery | Can't create or edit master pages |
| Publishing Sites | Can't create or edit master pages and page layouts |

Furthermore, [SharePoint Framework](/en-us/sharepoint/dev/spfx/sharepoint-framework-overview) web parts that have the `requiresCustomScript` value set to `true` behave as follows:

- The web part isn't available in the web part picker.
- Every instance of a web part that was added to a page when custom scripts were previously allowed no longer surfaces in those pages.

SharePoint site authors can remove web parts that no longer work while editing their pages.

## Best practices for communicating script setting changes

Before you prevent custom script on sites where you previously allowed it, communicate the change well in advance so users can understand the impact. Otherwise, users who are accustomed to changing themes or adding web parts on their sites suddenly can't make those changes. They see the following error message.

[![Screenshot of the Error message that's displayed when scripting is disabled on a site.](sharepointonline/media/sharepoint-web-part-error.png)](sharepointonline/media/sharepoint-web-part-error.png#lightbox)

Communicating the change in advance reduces user frustration and support calls.