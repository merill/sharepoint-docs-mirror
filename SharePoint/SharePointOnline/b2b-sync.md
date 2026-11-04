---
layout: Conceptual
title: B2B Sync for SharePoint and OneDrive - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/b2b-sync
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-12-19T00:00:00.0000000Z
ms.reviewer: wsproule
ms.author: v-mactran
author: MachelleTranMSFT
manager: jtremper
audience: Admin
customer-intent: As a SharePoint Administrator, I want to set up B2B Sync so that users can sync folders shared by other organizations.
f1.keywords:
- NOCSH
ms.topic: article
ms.service: onedrive
ms.localizationpriority: medium
ms.collection:
- Strat_OD_admin
- M365-collaboration
ms.custom:
- admindeeplinkSPO
- onedrive-toc
- has-azure-ad-ps-ref
search.appverid:
- ODB160
- ODB150
- MET150
description: 'Learn how the OneDrive sync app allows users to sync folders shared by users in other organizations. '
locale: en-us
document_id: 551144b4-b57a-251c-79ef-7bbddfd60e16
document_version_independent_id: 2eab7898-16c7-d764-2334-fb561b34c8fb
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/b2b-sync.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: b2b-sync
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/b2b-sync.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
platformId: c7a24645-786d-922a-6109-c87e34d68296
---

# B2B Sync for SharePoint and OneDrive - SharePoint in Microsoft 365 | Microsoft Learn

B2B Sync in the OneDrive sync app allows users to sync libraries or folders in Microsoft SharePoint or Microsoft OneDrive that are shared from other organizations. This scenario is often referred to as Business-to-Business (B2B) Collaboration.

Microsoft Entra guest accounts are essential for B2B Collaboration. A guest account at one organization links to a member account at another organization. Once created, a guest account allows Microsoft 365 services like OneDrive and SharePoint to grant a guest permission to sites and folders, just like a member within the organization. Because the accounts at two organizations are linked, users only need to remember the username and password for their own organization's account. A single sign-in enables access to content from their own organization and from any other organizations that created guest accounts for them.

Important

We recommend that you enable [SharePoint and OneDrive integration with Microsoft Entra B2B](/en-us/sharepoint/sharepoint-azureb2b-integration) to help ensure that the required Microsoft Entra guest account for the share recipient is created in your organization's directory.

## What are the requirements for B2B Sync?

For people outside your organization to sync shared libraries and folders:

- You must enable external sharing for your organization.
- You must enable external sharing for the site or OneDrive.
- You must share the content with people outside the organization at the site or folder level. If a folder is shared, it must be through a link that requires sign-in.
- Sharing recipients must have a Microsoft 365 work or school account (in Microsoft Entra ID) in the same cloud as the content tenant - Microsoft Azure Commercial, Microsoft Azure Government, or Microsoft Azure China 21Vianet. (Microsoft Azure Commercial contains the Microsoft 365 commercial and GCC cloud environments, and Microsoft Azure Government contains the GCC High and DoD cloud environments.)
- Any Microsoft Entra Conditional Access policies must be compatible with guests. See Conditional Access policies for more information on external access and compatibility.
- Microsoft Authentication Library must not be enabled if using builds before 19.086.

This article gives an overview of the B2B Sync experience and describes these requirements in more detail.

## What are the known issues?

- Sync between users in different clouds isn't supported For example, content shared from a tenant in Microsoft Azure China 21Vianet isn't synched for a user with a Microsoft Azure Commercial cloud.
- On the Mac, Files On-Demand thumbnails won't display from external organization's sites. Thumbnails display correctly for files from the user's own organization.
- On the Mac, if the guest account was created with a different email address format than the form they're using with the sync app, the external site's content can't be synced. For example, first.last@fabrikam.com vs alias@fabrikam.com.
- On Mac, the external content can be placed on the local computer in the user's own organization's folder instead of one with the external organization's name.
- Interactive authentication UI for guest accounts from an external organization isn't supported by the sync client.

## How does the B2B Sync experience work?

Here's an example of what happens after someone at "Contoso" shares a site or folder with someone at "Fabrikam":

1. The Fabrikam recipient receives an email like the following.

    ![A sharing invitation email](sharepointonline/media/sharing-invitation.png)
2. When the recipient selects the link in the email to go to the shared item, they need to select "Organizational account" to sign in with their Fabrikam account. Behind the scenes, this creates the Contoso guest account in Microsoft Entra ID.

    ![Accepting an invitation](sharepointonline/media/accept-invitation.png)
3. The recipient may need to enter their Fabrikam username or password, and then they can view the shared item. If they don't want to sync everything that was shared, they can browse to the library or folder they want to sync. To set up syncing, they need to select the Sync button.

    ![The Sync button in a SharePoint document library](sharepointonline/media/sync-button.png)
4. The guest's browser displays up a message asking if they want to open "Microsoft OneDrive," and they'll need to allow this.
5. If this is the first time the guest has used the sync app with their Fabrikam account, they need to sign in. The email address is automatically set to the Fabrikam account used in the previous steps. The guest needs to select "Sign in."
6. The guest might be able to sign in to the sync app without entering their Fabrikam password if they're signed in to Windows with the same account. Otherwise they need to enter their password.
7. The guest confirms where they want to sync the shared item on their computer.

    Note

    The content is placed in a folder whose name includes the name of the organization ("SharePoint - Contoso" in this example). If the user is syncing SharePoint content from Fabrikam as well, they'll also have a "SharePoint - Fabrikam" folder.
8. The guest continues through OneDrive sync app setup.
9. After the guest completes setup, the site will begin syncing. The user can select the blue cloud icon in the notification area to open the OneDrive sync activity center and see the files syncing, open the local folder with the files, or open the SharePoint site in a web browser.

## How do I enable external sharing for my organization?

To allow users at your organization to share with their partners at other organizations, you must enable external sharing at the organization level. You must be a Global Administrator or SharePoint Administrator in Microsoft 365 to do this. After you enable external sharing at the organization level, you can restrict it site by site. A site's settings can be the same as the organization setting, or more restrictive, but not more permissive.

You can change your organization-level sharing settings in two different places (both control the same thing):

- On the Sharing page in the new SharePoint admin center. For more info, see [Change the organization-level external sharing setting](/en-us/sharepoint/turn-external-sharing-on-or-off#change-the-organization-level-external-sharing-setting)
- In the Microsoft 365 admin center, on the Org settings page &gt; SharePoint.

Important

If you allow Anyone links (sometimes referred to as "anonymous access" links), these links don't create guest accounts and therefore the external share recipient won't be able to use B2B Sync when receiving that link type.

For more info, see [External sharing overview](/en-us/sharepoint/external-sharing-overview).

### Control external sharing

When you allow users to share content from your organization externally, you can use several features in Microsoft 365 to manage who has access to the content. Admins and site owners can review permissions and audit access to sites. For info, see [Searching for site content shared with people outside your organization](/en-us/microsoft-365/compliance/keyword-queries-and-search-conditions#searching-for-site-content-shared-with-external-users) and [Turn on external sharing notifications](turn-on-external-sharing-notifications). You can enable external sharing with only specific internet domains, or you can block specific domains. For info, see [Restricted domains sharing](/en-us/sharepoint/restricted-domains-sharing). You can also allow only members of specific security groups to share externally. For info, see [Turn external sharing on or off](/en-us/sharepoint/turn-external-sharing-on-or-off).

We recommend creating separate sites (site collections, not subsites) for each unit of work that you want to share externally. This way, you can clearly annotate the sites to indicate that people outside the organization have access, and avoid unintentional disclosure of information. For individual users sharing content from their OneDrive, we recommend creating separate folders for different projects or collaboration groups.

You can remove a guest's permission to a site or folder, or you can delete the guest account to remove their permission from all of your organization's content.

Important

Any synced content will remain on the user's computer after permissions have been removed.

## How do I enable external sharing for a site?

To view or change the sharing setting for any site, use the new SharePoint admin center.

1. Go to **Active sites** in the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185220), and sign in with an account that has [admin permissions](/en-us/sharepoint/sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the Active sites page.
2. Customize the view as necessary to see the External sharing column.
3. If you need to, [change the external sharing setting for a site](/en-us/sharepoint/manage-sites-in-new-admin-center#change-the-external-sharing-setting-for-a-site).

## How do I ensure Conditional Access policies are compatible?

As an admin, you can enable several kinds of conditional access policies at your tenant. When a guest accesses a tenant's content, you might need to adjust those policies for the guests to ensure they can gain access.

- Currently the sync client doesn't support interactive authentication UI when syncing external content. Any policy that would require a sign-in UI such as MFA (multifactor authentication) or TOU (terms of use) prompt, will prevent the syncing of the external content from that tenant. If a tenant admin deploys such a policy before a guest starts syncing from that tenant, the user is unable to establish the sync relationship. If the policy is deployed after a guest is syncing content from the tenant, that guest will receive an error and be unable to continue to sync from the tenant.
- Tenants may update their Terms of Use (TOU) from time to time. A policy can trigger the user to view and accept the updated TOU via an interactive authentication prompt. Since sync doesn't support external tenant sign-in UI, sync indicates it's unable to sync the external site's content.
- Device Compliance requires user machines to be managed by the tenant and then to be up to date with requirements. For guests, their machines are likely to be managed by their own organization and thus are incompatible with requiring their machines to be managed by the content sharing tenant.
- Location-based conditional access policies are typically used to enforce more requirements like MFA when the user isn't connecting from a trusted location (such as the tenant's office network). Typically in a guest scenario the client machine won't be located at the trusted locations, and since sync doesn't support MFA, you likely don't want this policy to apply to your guests.

For more information, see [Authentication and Conditional Access for External Identities](/en-us/azure/active-directory/external-identities/authentication-conditional-access).

## What are the methods of sharing?

Sites and folders can be shared in different ways in SharePoint and OneDrive:

- If users are syncing a folder, they can right-click it in File Explorer to share it.
- Users can go to the SharePoint site or folder on the web and select the Share button to share it.
- Users can share sites and folders in the SharePoint and OneDrive mobile apps.
- Admins can create guest accounts and use the admin center or PowerShell to add them to sites.

Note

For more info about these methods, see [Learn how to share a site](https://support.office.com/article/958771a8-d041-4eb8-b51c-afea2eae3658) and [Learn how to share a folder](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c).

B2B Sync works with all these methods of sharing. It has only the following requirements:

- For guests to sync shared content, the content must be shared at the site or folder level. Guests can't sync files that are shared individually (for example, from the Office apps).
- B2B sync works only when guest accounts are created in the organization, and when the recipient has a Microsoft Entra account. It doesn't work when users share by creating an Anyone link (also known as "anonymous access" link), or when they share with people who have a Microsoft account or other personal account.

### How do I add guests to SharePoint sites?

As an admin in Microsoft 365, you can share with people outside the organization by [creating guests individually in the Microsoft Entra admin center](/en-us/azure/active-directory/b2b/b2b-quickstart-add-guest-users-portal), and then adding them to a SharePoint team site individually or by adding them to a security group that already has permissions to the site you want to share. If you grant permissions by using the advanced permissions page (instead of by using the Share site button), you need to inform the guest that you've given them permission to the site. They won't receive an invitation email.

Important

If you use the advanced permissions page, we recommend granting permissions at the site level, not at the document library or folder level.

### How do I use PowerShell to bulk create guest accounts?

If you need to create and grant permissions to many guest accounts, you can use the following PowerShell script, which creates guest accounts and grants them permissions to a site. The script takes a CSV (comma-separated value) file as input, which contains a list of user display names and email addresses. For each name and email address, a guest account is created and that account is added to a security group to grant it permission. The script is designed so that you can feed the resulting output CSV as input to the script on a subsequent run. This lets you add more users to your CSV file or retry creating any failed account.

Note

Microsoft Entra ID and MSOnline PowerShell modules are deprecated as of March 30, 2024. To learn more, read the [deprecation update](https://techcommunity.microsoft.com/t5/microsoft-entra-blog/important-azure-ad-graph-retirement-and-powershell-module/ba-p/3848270). After this date, support for these modules are limited to migration assistance to Microsoft Graph PowerShell SDK and security fixes. The deprecated modules will continue to function through March, 30 2025.

We recommend migrating to [Microsoft Graph PowerShell](/en-us/powershell/microsoftgraph/overview) to interact with Microsoft Entra ID (formerly Azure AD). For common migration questions, refer to the [Migration FAQ](/en-us/powershell/azure/active-directory/migration-faq).

Be aware that versions 1.0.*x* of MSOnline may experience disruption after June 30, 2024.

As users are added to the Microsoft Entra group, they should receive an email welcoming them to the group. After running the script, you'll need to email the users with a direct link to the SharePoint site you gave them permissions to. When they select the link, they're presented with the below UI to accept the terms of the invitation. Once they accept, they're taken to the site you shared with them. At that point they can select the Sync button to begin syncing the sites files to their PC or Mac.

![Accepting a sharing invitation](sharepointonline/media/accept-invitation-message.png)

```PowerShell
# first line of InviteGuests.ps1 PowerShell script
# requires latest AzureADPreview
# Get-Module -ListAvailable AzureAD*
# Uninstall-Module AzureAD
# Uninstall-Module AzureADPreview
# Install-Module AzureADPreview

# customizable properties for this script

$csvDir = ''
$csvInput = $csvDir + 'BulkInvite.csv'
$csvOutput = $csvDir + 'BulkInviteResults.csv'

$domain = 'YourTenantOrganization.onmicrosoft.com'
$admin = "admin@$domain"
$redirectUrl = 'https://YourTenantOrganization.sharepoint.com/sites/SiteName/'
$groupName = 'SiteName'

# CSV file expected format (with the header row):
# Name,Email
# Jane Doe,jane@contoso.com

$csv = import-csv $csvInput

# will prompt for credentials for the tenantorganization admin account
# (who has permissions to send invites and add to groups)
Connect-AzureAD -TenantDomain $domain -AccountId $admin

$group = (Get-AzureADGroup -SearchString $groupName)

foreach ($row in $csv)
{
    Try
    {
        if ((Get-Member -inputobject $row -name 'error') -and `
            ($row.error -eq 'success'))
        {
            $out = $row  #nothing to do, user already invited and added to group
        }
        else
        {
            echo ("name='$($row.Name)' email='$($row.Email)'")

            $inv = (New-AzureADMSInvitation -InvitedUserEmailAddress $row.Email -InvitedUserDisplayName $row.Name `
                        -InviteRedirectUrl $redirectUrl -SendInvitationMessage $false)

            $out = $row
            $out|Add-Member -MemberType ScriptProperty -force -name 'time' -Value {$(Get-Date -Format u)}
            $out|Add-Member -MemberType ScriptProperty -force -name 'status' -Value {$inv.Status}
            $out|Add-Member -MemberType ScriptProperty -force -name 'userId' -Value {$inv.InvitedUser.Id}
            $out|Add-Member -MemberType ScriptProperty -force -name 'redeemUrl' -Value {$inv.inviteRedeemUrl}
            $out|Add-Member -MemberType ScriptProperty -force -name 'inviteId' -Value {$inv.Id}

            # this will send a welcome to the group email
            Add-AzureADGroupMember -ObjectId $group.ObjectId -RefObjectId $inv.InvitedUser.Id

            $out|Add-Member -MemberType ScriptProperty -force -name 'error' -Value {'success'}
        }
    }
    Catch
    {
        $err = $PSItem.Exception.Message
        $out|Add-Member -MemberType ScriptProperty -force -name 'error' -Value {$err}
    }
    Finally
    {
        $out | export-csv -Path $csvOutput -Append
    }
}

# for more information please see
# https://learn.microsoft.com/azure/active-directory/b2b/b2b-tutorial-bulk-invite
# end of InviteGuests.ps1 powershell script
```

For more info, see:

- [Redemption experience](/en-us/azure/active-directory/b2b/redemption-experience)
- [Add user without invite](/en-us/azure/active-directory/b2b/add-user-without-invite)

## What happens when a guest loses access?

If a person's guest account is deleted or their permission to shared content is removed, the sync app displays an error.

- A notification appears indicating that the library can't be synced.

    ![We can't sync your document library notification](sharepointonline/media/cant-sync-notification.png)
- The OneDrive icon in the notification area shows an error.

    ![OneDrive sync error icon](sharepointonline/media/onedrive-error-icon.png)

    When the guest selects the icon, they see an error banner in the activity center.

    ![OneDrive needs your attention message](sharepointonline/media/error-activity-center.png)![Request access or stop syncing library](sharepointonline/media/error-resolution.png)

## How do I prevent B2B Sync?

You can prevent users at your organization from using B2B Sync by setting a policy value on your users' Windows PC or Mac to block external sync.

The new BlockExternalSync setting is described in the adm\OneDrive.admx and OneDrive.adml files installed as part of the OneDrive sync product build 19.086.\* or higher. If you use ADM to manage your sync app policies, import the new files as you normally would in order to see the new setting.

If you're using other management systems to deploy policies to your users' Windows PCs, use the equivalent of the following command to prevent B2B Sync:

```cmd
reg add "HKLM\SOFTWARE\Policies\Microsoft\OneDrive" /v BlockExternalSync /t REG_DWORD /d 1
```

On a Mac with the Apple Store version of OneDrive, use the equivalent of the following command to prevent B2B Sync:

```cmd
defaults write com.microsoft.OneDrive-mac BlockExternalSync -bool YES
```

On a Mac with the Standalone version of OneDrive, use the equivalent of the following command to prevent B2B Sync:

```cmd
defaults write com.microsoft.OneDrive BlockExternalSync -bool YES
```