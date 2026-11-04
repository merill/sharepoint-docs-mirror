---
layout: Conceptual
title: Manage sharing settings for SharePoint and OneDrive in Microsoft 365 - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/turn-external-sharing-on-or-off
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-06-30T00:00:00.0000000Z
ms.reviewer: srice
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
f1.keywords: CSH
ms.topic: how-to
customer-intent: As a SharePoint administrator, I want to manage the organization-level sharing settings for SharePoint and OneDrive in Microsoft 365 so that I can control how my organization shares content externally.
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Strat_OD_share
- M365-collaboration
- essentials-manage
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
search.appverid:
- SPO160
- MET150
ms.assetid: 6288296a-b6b7-4ea4-b4ed-c297bf833e30
description: Learn how SharePoint administrators can change the organization-level sharing settings for SharePoint and OneDrive in Microsoft 365.
locale: en-us
document_id: 6ed46514-8036-a543-d690-73d48acef690
document_version_independent_id: 8542c3ce-3012-3d23-c3e4-4331dac033d2
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/turn-external-sharing-on-or-off.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: turn-external-sharing-on-or-off
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/turn-external-sharing-on-or-off.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
platformId: eef40916-011f-a629-12f4-023d799c8f3a
---

# Manage sharing settings for SharePoint and OneDrive in Microsoft 365 - SharePoint in Microsoft 365 | Microsoft Learn

As a SharePoint Administrator in Microsoft 365, you can change the organization-level sharing settings for SharePoint and OneDrive. These settings control sharing at the organization level. You can configure more restrictive settings for specific sites if needed.

For end-to-end guidance on how to configure guest sharing in Microsoft 365, see:

- [Set up secure collaboration with Microsoft 365](/en-us/microsoft-365/solutions/setup-secure-collaboration-with-teams)
- [Collaborate with guests on a document](/en-us/microsoft-365/solutions/collaborate-on-documents)
- [Collaborate with guests in a site](/en-us/microsoft-365/solutions/collaborate-in-site)
- [Collaborate with guests in a team](/en-us/microsoft-365/solutions/collaborate-as-team)

To change the sharing settings for a site after you set the organization-level sharing settings, see [Change sharing settings for a site](change-external-sharing-site). To learn how to change the external sharing setting for a specific user's OneDrive, see [Change the external sharing setting for a user's OneDrive](/en-us/onedrive/user-external-sharing-settings).

Tip

As a companion to this article, see our [Microsoft Sharepoint setup guide](https://go.microsoft.com/fwlink/?linkid=2273603) to review best practices and understand the deployment process from site creation to data migration. Features include protection labels, data loss prevention policies, and file activity auditing. For a customized experience based on your environment, you can access the [Set up SharePoint in Microsoft 365 guide](https://go.microsoft.com/fwlink/?linkid=2274437) in the Microsoft 365 admin center.

### How do SharePoint and OneDrive integrate with Microsoft Entra B2B?

SharePoint and OneDrive use two external sharing models:

- SharePoint external authentication
- SharePoint and OneDrive integration with Microsoft Entra B2B

When you use Microsoft Entra B2B integration, Microsoft Entra external collaboration settings, such as [guest invite settings and collaboration restrictions](/en-us/azure/active-directory/external-identities/external-collaboration-settings-configure), apply.

The following table shows the differences between the two sharing models.

| Sharing method | Files and folders | Sites |
| --- | --- | --- |
| SharePoint external authentication(Microsoft Entra B2B integration not enabled) | No guest account created (see the note following this table)Microsoft Entra settings don't apply | N/A(Microsoft Entra B2B always used) |
| Microsoft Entra B2B integration enabled | Guest account always createdMicrosoft Entra settings apply | Guest account always createdMicrosoft Entra settings apply |

Note

A guest account might already exist from another sharing workflow, such as sharing a team, in which case it's used for sharing.

For information on how to enable or disable Microsoft Entra B2B integration, see [SharePoint and OneDrive integration with Microsoft Entra B2B](sharepoint-azureb2b-integration).

## Change organization-level external sharing setting

1. In the SharePoint admin center, expand **Policies**, and then select **Sharing**.

    [![Screenshot showing sharing settings for SharePoint and OneDrive in the SharePoint admin center.](sharepointonline/media/turn-external-sharing-on-or-off/sharing-settings.png)](sharepointonline/media/turn-external-sharing-on-or-off/sharing-settings.png#lightbox)
2. Under **External sharing**, set your sharing level for SharePoint and OneDrive. Keep these points in mind:

    - The SharePoint setting applies to all site types, including sites connected to Microsoft 365 groups and teams. Groups and Teams guest sharing settings also affect connected SharePoint sites.
    - The OneDrive setting can be more restrictive than the SharePoint setting, but not more permissive.
    - External sharing settings are for your organization overall. Each site has its own sharing setting that you can set independently, though it must be at the same or more restrictive setting as the organization. See [Change the external sharing setting for a site](change-external-sharing-site) for more information.
3. Expand **More external sharing settings** and then select the options you want to use.

    See More external sharing settings (in this article).
4. Select **Save**.

Important

[Microsoft Entra external collaboration settings](/en-us/azure/active-directory/external-identities/external-collaboration-settings-configure) determine who can invite guests in your organization for site sharing (always) and file and folder sharing (if Azure B2B collaboration is enabled). Be sure to review Microsoft Entra guest access settings as part of your SharePoint and OneDrive sharing setup.

## External sharing options

The following table describes sharing options for SharePoint and OneDrive.

| Option | Description |
| --- | --- |
| **Anyone** | Allow users to share files and folders by using links that anyone who has the link can access the files or folders without authenticating. This setting also allows users to share sites with new and existing guests who authenticate. If you select this setting, you can restrict the Anyone links so that they must expire within a specific number of days, or so that they can give only View permission.[File requests](https://support.office.com/article/f54aa7f8-2589-4421-b351-d415fc3b83af) requires that OneDrive be set to **Anyone** and edit permissions for **Anyone** links be enabled. OneDrive settings other than **Anyone** disable file requests.See [Best practices for sharing files and folders with unauthenticated users](/en-us/Office365/Enterprise/best-practices-anonymous-sharing) for more information. |
| **New and existing guests** | Require people who receive invitations to sign in with their work or school account (if their organization uses Microsoft 365) or a Microsoft account, or to provide a code to verify their identity. Users can share with guests already in your organization's directory, and they can send invitations to people who are added to the directory if they sign in. For more info about verification codes, see [Secure external sharing in SharePoint](what-s-new-in-sharing-in-targeted-release) |
| **Existing guests** | Allow sharing only with guests who are already in your directory. These guests might exist in your directory because they previously accepted sharing invitations or because they were manually added, such as through [Azure B2B collaboration](/en-us/azure/active-directory/b2b/what-is-b2b). (To see the guests in your organization, go to the [Guests page in the Microsoft 365 admin center](https://admin.microsoft.com/Adminportal/Home#/GuestUsers)). |
| **Only people in your organization** | Turn off external sharing. |

Note

If you turn off external sharing for your organization and later turn it back on, guests regain access. If you know that external sharing was previously turned on and in use for specific sites and you don't want guests to regain access, first turn off external sharing for those specific sites.

If you restrict or turn off external sharing, guests typically lose access within one hour of the change.

## More external sharing settings

| Setting | Description |
| --- | --- |
| **Limit external sharing by domain** | This setting is useful if you want to limit sharing with particular partners, or help prevent sharing with people at certain organizations. The organization-level setting on this page affects all SharePoint sites and each user's OneDrive. To use this setting, list the domains (maximum of 5,000) in the box, using the format *domain.com*. To list multiple domains, press Enter after adding each domain. You can also limit external sharing by domain by using the [Set-SPOTenant](/en-us/powershell/module/sharepoint-online/Set-SPOTenant) Microsoft PowerShell cmdlet with `-SharingDomainRestrictionMode` and either `-SharingAllowedDomainList` or `-SharingBlockedDomainList`. For information about limiting external sharing by domain at the site level, see [Restricted domains sharing](restricted-domains-sharing). [Allowed or blocked domains in Microsoft Entra ID](/en-us/azure/active-directory/external-identities/allow-deny-list) also affect SharePoint and OneDrive site sharing (always) and file and folder sharing (if Azure B2B collaboration is enabled). Be sure to review Microsoft Entra collaboration restrictions as part of your SharePoint and OneDrive sharing setup. |
| **Allow only users in specific security groups to share externally** | See [Manage security groups](manage-security-groups). |
| **Allow guests to share items they don't own** | By default, guests must have full control permission to share items externally. |
| **Guest access to a site or OneDrive will expire automatically after this many days** | Administrators can set an expiration time for guest access. Each guest who's invited to the site or with whom individual files and folders are shared has access for some days. For more information visit, [Manage guest expiration for a site](https://support.microsoft.com/en-us/office/manage-guest-expiration-for-a-site-25bee24f-42ad-4ee8-8402-4186eed74dea) |
| **People who use a verification code must reauthenticate after this many days** | If people who use a verification code select to "stay signed in" in the browser, they must prove they can still access the account they used to redeem the sharing invitation by entering a code sent to that account. See [Secure external sharing recipient experience](/en-us/sharepoint/what-s-new-in-sharing-in-targeted-release).If Azure B2B collaboration is enabled, the [Microsoft Entra setting](/en-us/azure/active-directory/external-identities/one-time-passcode) is used instead of this setting. |
| **File and folder links** | Specifies options to show by default when a user creates a sharing link. |
| **Specific people** | This option is most restrictive and impedes broad internal sharing. If you allow external sharing, this option lets users share with specific people outside the organization. |
| **Only people in your organization** | If links are forwarded, they work for anyone in the organization. This option is best if your organization shares broadly internally and rarely shares externally. |
| **Anyone with the link** | This option is available only if your external sharing setting is set to **Anyone**. Forwarded links work internally or externally, but you can't track who has access to shared items or who has accessed shared items. This option is best for friction-free sharing if most files and folders in SharePoint and OneDrive aren't sensitive. If you select **Anyone with the link**, but the site or OneDrive is set to allow sharing only with guests who sign in or provide a verification code, the default link is **Only people in your organization**. Users need to change the link type to **Specific people** to share files and folders in the site or OneDrive externally. |

## Advanced settings for "Anyone" links

![Screenshot of the advanced settings for anyone links in the new SharePoint admin center.](sharepointonline/media/advanced-settings-anyone-links.png)

**Link expiration** - You can require all **Anyone** links to expire, and specify the maximum number of days allowed. If you change the expiration time, existing links keep their current expiration time if the new setting is longer, or update to the new setting if the new setting is shorter.

**Link permissions** - You can restrict **Anyone** links so that they can only provide view permission for files or folders.

To use the *Request Files* feature, set the link permissions to **View, edit, and upload** or **View and Upload** for folders.

## Show owners the names of people who viewed their files in OneDrive

This setting controls whether the owner of a shared file can see on the file card the people who only view (and don't edit) the file in OneDrive. The file card appears when users hover over a file name or thumbnail in OneDrive. The info includes the number of views on the file, the number of people who viewed it, and the list of people who viewed it. To learn more about the file card, see [See files you shared in OneDrive](https://support.office.com/article/6b67b82b-9c5c-4348-ab10-fd5b0d8df76c).

Note

This setting is selected by default. If you clear it, file viewer info is still recorded and available to you to audit as an admin. OneDrive owners can also still see people who viewed their shared Office files by opening the files from Office.com or from the Office desktop apps.

## Let site owners choose to display the names of people who viewed files or pages in SharePoint

This setting specifies whether site owners can allow users who have access to a file, page, or news post to see on the file card who viewed the item.

![Screenshot of viewer information on the file card for a document.](sharepointonline/media/8ff30cde-b358-4b35-9f9d-77cb01c69f09.png)

This setting is turned on by default at the organization level and off at the site level for existing sites. Viewer information shows only when the setting is on at both the organization and site level. Turn on this feature only on team sites that don't have sensitive information. [Learn how site owners can turn on this feature](https://support.office.com/article/ee26dde0-c30e-4eca-b1c3-38922c450967).

Note

Historical data is included when this setting is enabled. Likewise, if the setting is turned off and back on at the organization level or site level, the views during the off period are included in the history.

## Use short links for sharing files and folders

Use a shorter link format for sharing files and folders. This format is useful if you have integrations that require a shorter URL.

## Need more help?

![Ask a question](/en-us/office/media/icons/pngs/users-group-blue-32.png) If you have technical questions about this topic, you might find it helpful to post them on the [SharePoint discussion forum](https://social.technet.microsoft.com/Forums/sharepoint/home?forum=onlineservicessharepoint). It's a great resource for finding others who have worked with similar issues or who have encountered the same situation.

For help on security and permissions, see these [YouTube videos from SharePoint community experts](https://www.youtube.com/playlist?list=PLKurDp05sqD0oE3KnohD69dkP5fHmrfuN).