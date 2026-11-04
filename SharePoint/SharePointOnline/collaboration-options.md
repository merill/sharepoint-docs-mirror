---
layout: Conceptual
title: Plan sharing and collaboration options in SharePoint and OneDrive - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/collaboration-options
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2022-06-10T00:00:00.0000000Z
ms.reviewer: srice
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords: NOCSH
ms.topic: article
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection: 
ms.custom: intro-get-started
search.appverid: MET150
description: Plan the sharing and collaboration options that you want to implement as part of rolling out SharePoint and OneDrive.
locale: en-us
document_id: ea40ff0e-ab00-c876-0945-16890824c3e0
document_version_independent_id: 6a4b60ab-eb93-b215-e6cd-b97ba33e0e10
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/collaboration-options.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: collaboration-options
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/collaboration-options.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: c688d4a9-2d54-434b-f1f2-e81d8e6dba32
---

# Plan sharing and collaboration options in SharePoint and OneDrive - SharePoint in Microsoft 365 | Microsoft Learn

SharePoint and OneDrive provide a platform for collaboration through file and folder storage and sharing.

As you plan your SharePoint and OneDrive rollout, these are the primary decision areas around collaboration:

- **Site creation** - do you want to allow your users to create SharePoint sites or do you want to manage this through IT or a business process?
- **External sharing** - do you want to allow users to share files, folders, or sites with people outside your organization?
- **File and folder sharing defaults** - what sharing defaults do you want to use to make sharing easy while you help protect sensitive information?

For details about collaboration governance in Microsoft 365, see [What is collaboration governance?](/en-us/microsoft-365/solutions/collaboration-governance-overview).

For an in-depth look at file collaboration in SharePoint, see [Intro to file collaboration in Microsoft 365, powered by SharePoint](/en-us/sharepoint/intro-to-file-collaboration) and [File collaboration in SharePoint with Microsoft 365](/en-us/sharepoint/deploy-file-collaboration).

Keep in mind that the settings you choose for collaboration in SharePoint can also affect Teams. For more information, see [Overview of Teams and SharePoint integration](teams-connected-sites).

## Site creation and lifecycle

By default, users can create new team sites and communication sites in SharePoint and shared libraries in OneDrive. We recommend keeping this setting and using [expiration policies](/en-us/microsoft-365/solutions/microsoft-365-groups-expiration-policy) to manage the number of unused sites.

If you don't want to allow users to create sites directly, you can disable user site creation. For details, see [Manage site creation in SharePoint](/en-us/sharepoint/manage-site-creation).

Even if you turn off sites creation for users in SharePoint, they can still create Microsoft 365 group-connected team sites by creating a Microsoft 365 group or any of its related services, such as a team in Microsoft Teams. If you don't want to allow users to create Microsoft 365 Groups or related services, including group-connected team sites, see [Manage who can create Microsoft 365 Groups](/en-us/microsoft-365/solutions/manage-creation-of-groups).

As part of your SharePoint rollout, we recommend that you create your own custom guidance for SharePoint site owners on how sites are set up and managed in your organization. See [Create guidelines for site usage](sites-usage-guidelines) for more information.

## External sharing

External sharing in SharePoint and OneDrive uses [Microsoft Entra B2B collaboration](/en-us/azure/active-directory/external-identities/what-is-b2b) to create guest accounts for people outside the organization. Guests can be given access to SharePoint sites or to individual files and folders in SharePoint and OneDrive.

External sharing is enabled by default in Microsoft 365, including SharePoint and OneDrive. We recommend leaving external sharing enabled. Microsoft 365 external sharing options can provide a more secure and governable sharing environment than sending attachments through email or using consumer sharing services.

Use the [Sharing page in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185222) to configure your sharing options. For details, see [Manage sharing settings](/en-us/sharepoint/turn-external-sharing-on-or-off).

For details about how to configure guest collaboration in SharePoint sites, see [Collaborate with guests in a site](/en-us/microsoft-365/solutions/collaborate-in-site).

### Organization level sharing settings

The organization level sharing settings for SharePoint and OneDrive provide a default setting for sites and OneDrive libraries. Individual sites can be locked down further, but cannot be made more permissive than, the organizational settings.

A key decision for your SharePoint and OneDrive rollout is who content can be shared with:

- **Anyone** - Users can share files and folders using links that don't require sign-in.
- **New and existing guests** - Guests are added to the directory when an item is shared and must sign in or provide a verification code to access the content.
- **Existing guests** - Users can only share with guests already in your organization's directory. (This setting is not recommended because guests can be added to the directory in various ways outside of SharePoint and OneDrive.)
- **Only people in your organization** - No external sharing is allowed.

These settings can be set separately for SharePoint and OneDrive, though the OneDrive setting cannot be more permissive than the SharePoint setting.

Important decisions:

- Do you want to allow external sharing? If not, choose the **Only people in your organization** option.
- Do you want to allow users to create sharing links that allow unauthenticated (anonymous) people to access files or folders? If so, choose **Anyone**.

### External sharing restrictions

You can restrict external sharing with these options:

- Restrict which domains users can share with.
- Limit external sharing to people in a specific security group.
- Expire guest access after a specified period.
- Require reauthentication after a specified period for users using a verification code.

If you want to restrict which domains users can share with, you can choose the **Limit external sharing by domain** setting. For details, see [Restrict sharing of SharePoint and OneDrive content by domain](/en-us/sharepoint/restricted-domains-sharing). Note that this setting only affects SharePoint and OneDrive. If you want to set this for all the services in Microsoft 365, you can configure the restriction in Microsoft Entra ID. See [Allow or block invitations to B2B users from specific organizations](/en-us/azure/active-directory/external-identities/allow-deny-list) for details.

If you don't want all of your users to be able to share externally, you can restrict external sharing to specific security groups. Choose the **Allow only users in specific security groups to share externally** option and choose the groups you want to allow.

If you want guest access to expire after a given period, use the **Guest access to a site or OneDrive will expire automatically after this many days** setting. The users who shared the content will have the option to extend the expiration by the period you specify before guests lose access. For more information see, [Manage guest expiration for a site](https://support.microsoft.com/office/25bee24f-42ad-4ee8-8402-4186eed74dea).

Guests with non-Microsoft email addresses, such as Gmail, are sent a verification code when they attempt to access shared content. You can require that these guests reauthenticate after a specified period. Use the **People who use a verification code must reauthenticate after this many days** setting to configure this.

## File and folder sharing

To create an easy sharing experience for your users while reducing the risk of oversharing, you can choose from these options for file and folder sharing links:

- Choose the default link type that users see when they share a file or folder.
- Choose if the default sharing link allows recipients to edit the files.
- Choose if *Anyone* links expire after a given period.
- Choose if *Anyone* links allow recipients to edit the files.

When users share a file or folder, they can choose from several types of sharing links that offer different levels of permissions. You can choose which link type is shown by default:

- *Specific people* links require the user to specify a list of people who will have access to the file or folder.
- *Only people in your organization* links provide access to the file or folder to anyone in your organization who has the link.
- *Anyone* links (if you've enabled them in your organization level sharing settings) provide anonymous access to anyone who has the link, including people outside your organization.

You can also choose the default permission level - view or edit - for sharing links.

These options can also be configured for individual sites. See [Change the sharing settings for a site](/en-us/sharepoint/change-external-sharing-site) for details.

If you've enabled *Anyone* links, you can choose if these links should expire after a given period and if they should allow edit access or just view access.