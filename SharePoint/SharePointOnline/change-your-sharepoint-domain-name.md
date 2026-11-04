---
layout: Conceptual
title: Change your SharePoint domain name - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/change-your-sharepoint-domain-name
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-07-29T00:00:00.0000000Z
ms.reviewer: anfra
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
customer_intent: As a SharePoint Administrator, I want to change my SharePoint domain name so that it matches my organization's rebranding or name change.
f1.keywords:
- CSH
ms.topic: how-to
ms.custom:
- SPOTADNS
- O365M_DomainsWizAdd_SPOUseMultiServices
- O365M_DomainsProp_SPO
- O365E_DomainsWizAdd_SPOUseMultiServices
- O365E_DomainsProp_SPO
- O365E_DomainsMain_PublicWebsite
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Strat_OD_admin
- M365-collaboration
- M365-SAM
search.appverid:
- SPO160
- MOE150
- MED150
- MBS150
- BCS160
- MET150
ms.assetid: 576325ad-8c40-4fe8-8a63-68c3b7d536cf
description: Learn how to change the domain name in your SharePoint and OneDrive URLs.
locale: en-us
document_id: 2454cb9a-dfa4-9c8a-3671-3150d49f74c7
document_version_independent_id: e0a4a71a-aa4d-1066-8f76-742c3411f06c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/change-your-sharepoint-domain-name.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: change-your-sharepoint-domain-name
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/change-your-sharepoint-domain-name.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
platformId: 5d2e3dff-ef87-b966-ef89-3881428776a0
---

# Change your SharePoint domain name - SharePoint in Microsoft 365 | Microsoft Learn

When you first sign up for Microsoft 365, you create an `onmicrosoft.com` domain. Even if you later add a custom domain, all your SharePoint and OneDrive URLs use the original `onmicrosoft.com` domain.

If your organization is going through a rebranding, merger, or acquisition and needs to change the domain in your SharePoint and OneDrive URLs, you can change the domain name by using PowerShell. For example, if your organization name changes from Contoso to Fabrikam, you can change your SharePoint URLs from `contoso.sharepoint.com` to `fabrikam.sharepoint.com`.

Important

- When the rename operation begins, all sites in the tenant queue for individual renames to the new domain. While the renaming is happening, sites that are on the original domain are temporarily inaccessible. Once each site is renamed to the new domain, it becomes accessible again.
- The standard version of the renaming feature is currently available to organizations that have no more than 10,000 total sites, which includes SharePoint sites, OneDrive accounts, and SharePoint Embedded containers combined.
- Advanced Tenant Rename is available to organizations with any number of sites, provided they have [SharePoint Advanced Management](advanced-management). See the section [Advanced Tenant Rename](change-your-sharepoint-domain-name#what-is-advanced-tenant-rename) in this article.
- The domain name change affects only SharePoint and OneDrive URLs. It doesn't impact email addresses.
- For information about changing a site address, like from `https://contoso.sharepoint.com/sites/sample1` to `https://contoso.sharepoint.com/sites/sample2`, see [Change a site address](change-site-address).
- The domain rename feature isn't available for organizations who have set up multigeo. This limitation includes tenants that were enabled during a trial or a paid offering in the past.
- If your organization uses special clouds or government clouds (such as GCC, GCC High, DoD, and so on), or if you have a `.de` domain, you can't change your domain name.
- When you rename your SharePoint domain, Microsoft creates a redirect at the previous address, which expires one year after the rename.
- You can only rename your SharePoint domain up to two times during the lifetime of your tenant. You can't schedule another SharePoint domain rename within 30 days after a previous rename completes.
- Changing your SharePoint domain name back to the original name after you rename it isn't supported. For example, if you change your SharePoint domain from `contoso.sharepoint.com` to `fabrikam.sharepoint.com`, changing it back to `contoso.sharepoint.com` isn't supported.
- Before starting a tenant rename, verify that no sites are blocked from being renamed. If more than 10% of sites fail to rename to the new domain, the tenant rename operation goes into a suspended state. To determine whether a tenant rename is suspended, see the section Monitor the status of the rename (in this article). If this occurs, submit a support request using [Restore Tenant Rename Suspension](https://admin.microsoft.com/AdminPortal/?searchSolutions=Restore%20Tenant%20Rename%20suspension) to resume the operation.
- A redirect site is created for each site rename and each redirect takes 0.15 MB. So, an organization should readily have an amount of storage equal or greater than 0.15 MB times the number of sites on the tenant before renaming.

## Limitations of changing a SharePoint domain name

### Low impact

| App or feature | Limitation | Action required |
| --- | --- | --- |
| Hub site menu items | Although the menu items continue to work, the process doesn't change items that contain absolute URLs. | Edit the menu items and if necessary, change the URLs to the new domain name. |
| Office "Recent" and "Pinned" lists | These lists update over time depending on usage. | None |
| Office.com | The URLs at `https://www.office.com` can take 24 hours to update. | None |
| OneDrive | Only the domain name portion in URLs is changed. The relative path based on the User Principal Name (UPN) isn't changed. | None |
| OneDrive sync app (OneDrive.exe) | Requires version 17.3.6943.0625 or later for all users. | Make sure the URLs "oneclient.sfx.ms" and "g.live.com." aren't blocked, and that all computers in your organization can reach them to apply updates. |
| OneDrive sync app (OneDrive.exe) | The organization name displayed in Office apps isn't changed. (For example, the app displays the old folder name C:\Users\Sophia\OneDrive – Contoso) | Users can disconnect and reconnect their account in the Office app. |
| OneNote | Requires a recent version of OneNote. | Make sure all users have the following versions installed:  OneNote desktop app: Version 16.0.8326.2096 or later.  OneNote for Windows 10: Version 16.0.8431.1006 or later.  OneNote mobile app: Version 16.0.8431.1011 or later. |
| OneNote | While the domain name is being changed, users might receive a notebook sync error. | None |
| SharePoint mobile apps | Requires a recent version of the mobile app. | Make sure all users have the following versions installed:iOS: 4.20.0 or later.  Android: 3.21.0 or later. |
| SharePoint mobile apps | While the domain name is being changed, users might receive a notebook sync error. | None |
| Search and Delve | The search index takes a while to reflect new URL changes. | None. As a benchmark, sites with under 100,000 documents are often updated in three days. For sites with over 100,000 documents, the updates can take a few weeks to months depending on traffic. |
| Search and Delve | Search results might not be complete or might return results for the original URLs until the search index is updated. | None |
| SharePoint content | Although content (such as text on pages) that includes the domain name continues to work, the process doesn't update it to display the new name. | Search for the old domain name and edit content to display the new domain name. |

### Medium impact

| App or feature | Limitation | Action required |
| --- | --- | --- |
| Custom apps and Group Policy objects | Absolute URLs embedded in these apps and objects aren't changed. | Edit custom apps and Active Directory Group Policy objects that contain absolute URLs and, if necessary, change the URLs to the new domain name. Confirm with app publishers that apps don't contain absolute URLs. |
| Custom and non-Microsoft apps | Some apps might not process the HTTP 308 redirect correctly. | Edit custom apps and work with app publishers to ensure that they handle HTTP 308 responses correctly. |
| Delve | It can take 24 hours before people profiles can be viewed. | None |
| eDiscovery | Holds can't be removed until you update the URLs. | In the Microsoft Purview portal, change the eDiscovery hold URLs to the new domain name. |
| InfoPath forms | Forms that use a SharePoint connection as a data source don't work. | Reconnect these forms to SharePoint. |
| Loop | Existing workspaces can't be shared and new pages can't be added to them. | No action is available. |
| Microsoft 365 Archive | Archived OneDrive accounts and SharePoint sites are renamed to the new domain. However, archived SharePoint sites connected to Teams channels or Microsoft 365 groups aren't renamed. | Reactivate archived SharePoint sites connected to Teams channels or Microsoft 365 groups before the rename. |
| Microsoft Forms | Forms that have the option to upload attachments in responses don't work. | Remove the upload button and add it again in the form. |
| Office apps | While the domain name is being changed, users might experience an error when saving Word, Excel, and PowerPoint documents that are located in a site or OneDrive. | Attempt to save the document again and if necessary change the URL of the **Save** location. |
| OneDrive | The Quick access links in OneDrive and SharePoint don't work in some cases. | No action is available. |
| OneDrive app in Teams | Accessing the app returns a 404 error. | Until a fix is released, to resolve the error:  1. Create a 1:1 chat with another user.  2. In the message box, select **Actions and apps** &gt; **Attach file** &gt; **Upload from this device**. 3. Select a file you send to the other user, then select **Open**. 4. Press **Enter** to send the file or select **Send**. After sending the file, navigate to the OneDrive app in Teams. |
| Power Automate | Request sign-off flows that use SharePoint as a connection don't work. | Remove and re-create the Request sign-off flow. |
| Power Automate | Any flows deployed as solutions with managed layers that use SharePoint as a connection don't work. | Remove and re-create the flows. |
| Power Automate | Some regular flows don't work after the rename. | As part of the rename operation, updates to Power Automate are attempted but a small subset might fail due to service issues. For any flows identified that don't work, manually update the URL. |
| Power BI | Power BI reports using SharePoint connections as a data source don't work. | Before changing your domain name, download the Power BI reports that are using SharePoint connections as a data source as a `.pbix` file. After you change the domain name, edit the connections in the Power BI Desktop app and republish the report.  Power BI reports that aren't created or maintained in the Power BI Desktop app need to be recreated. |
| Project Online | Workflows that are in flight don't complete and are orphaned.  New workflow instances can't be initiated.  Association to previous workflow instances isn't available and are orphaned. | Before changing your domain name, make sure all in flight workflows are completed. After you change the domain name, republish the workflows. You can then reset them to in flight in Project Web App by going to **PWA Settings** &gt; **Change or Restart Workflows**. |
| Project Online | URLs embedded in workflows aren't changed. For example, if a workflow contains the embedded URL `contoso.sharepoint.com`, it isn't changed. This might impact the functionality of the workflow. | Workflows that contain URLs referring to the original domain name might need to be updated to the new name. |
| Project Online | References to PWA sites in Project Online at `https://project.microsoft.com` don't work. | In Project Online at `https://project.microsoft.com`, change the URL of the PWA sites under **Settings** &gt; **My PWA Site**. |
| Project Online | Custom Excel Reports that use Microsoft Project Data connections as a data source don't work. | These reports need to be reconnected. |
| Project Pro | The app doesn't work until you update the URL of the PWA site. | Before changing your domain name, make sure that all projects that are checked out in Project Pro are checked in. After you change the domain name, change the URL of the PWA site under **File** &gt; **Info** &gt; **Manage Accounts**. |
| SharePoint 2013 workflows | Workflows that are in flight don't complete and are orphaned.  New 2013 Workflow instances can't be initiated. Association to previous workflow instances isn't available and these workflows are orphaned. | Before changing your domain name, make sure all in-flight workflows are completed. After you change the domain name, republish the workflows. |
| SharePoint 2013 workflows | URLs embedded in workflows aren't changed. For example, if a workflow contains the embedded URL `contoso.sharepoint.com`, it isn't changed. This configuration might impact the functionality of the workflow. | Workflows that contain URLs referring to the original domain name might need to be updated to the new name. |
| SharePoint add-ins | Add-ins might not function as expected. | The add-ins might need to be republished. Review the App configuration settings in Microsoft Entra ID for the add-in and update any URLs to the new domain name.  For SPFx applications, in Microsoft Entra ID update the Authentication URLs to the new domain for the SharePoint Online Client Extensibility Web Application Principal. |
| SharePoint hub sites | Sites registered as hub sites don't work. | Unregister and register the affected sites as hub sites in the SharePoint admin center after the rename. |
| SharePoint web parts | Some web parts might not function as expected. | The web parts might rely on direct URL references. Update the web parts with the new URLs. |
| Site customizations and embedded code | Absolute URLs embedded in SharePoint customizations aren't updated. | Edit customizations that contain absolute URLs and if necessary, change the URLs to the new domain name. |
| Teams on the web and Teams desktop app | The first time someone tries to access the **Files** tab for a team or private channel, they receive an error. The tab works for all users afterwards. | None |
| Teams on the web and Teams desktop app | It can take 72 hours for meeting notes to work (for both current and previous meetings). | None |
| Teams on the web and Teams desktop app | On the **Files** tab, any folders added by using **Add cloud storage** (which point to another SharePoint site) don't work. | Remove and re-add the folders. |
| Teams on the web and Teams desktop app | Document libraries and SharePoint Lists added as tabs don't work. | Remove and re-add the tabs. |
| Teams on the web and Teams desktop app | Embedded images in Wikis aren't displayed. | Edit the `Wiki.mht` file located in the SharePoint Site Teams Wiki Data library and if necessary, change the URLs of the embedded images to the new domain name. |
| Teams on the web and Teams desktop app | Personal Wikis don't work. | In a one-on-one or group chat, attach and send a file to the chat. |
| Non-Microsoft apps including backup solutions | Absolute URLs embedded in non-Microsoft apps (including backup solutions) aren't changed. | Confirm with app publishers (including backup solutions) that they support tenant renames. |
| Isolated web parts and full page apps | Isolated components aren't updated and stop working. | Solutions that contain isolated components need to be republished in the tenant app catalog. The solution starts working again after republishing. |

### High impact

| App or feature | Limitation | Action required |
| --- | --- | --- |
| Alternate URLs | If your tenant still has alternate URLs configured, you can't change your domain name. | Remove alternate URLs before you can schedule a rename. Contact Microsoft for support getting them removed. |
| Business Productivity Online Suite (BPOS) sites | If your tenant still has Microsoft Business Productivity Online Suite (BPOS) sites remaining in it, you can't change your domain name. | Remove BPOS sites and its configuration before scheduling tenant renaming. Submit a support request by selecting [Rename a SharePoint Tenant with BPOS sites](https://admin.microsoft.com/AdminPortal/?searchSolutions=Rename%20a%20SharePoint%20Tenant%20with%20BPOS%20sites). |
| Deleted sites | You can't restore any sites that you deleted after the change. | Before changing your domain name, review the Deleted sites page in the SharePoint admin center and restore any sites that you want to keep. |
| Historical German cloud (.de) tenants | If your tenant was originally in the German cloud with a .de domain, you can't change your domain name. This limitation applies even if your tenant was later migrated to the regular cloud but still retains the .de domain. | No action available. |
| Locked sites and OneDrive accounts | Locked OneDrive and SharePoint sites (the LockState is NoAccess) are renamed to the new domain. However, locked SharePoint sites connected to Teams channels or Microsoft 365 groups aren't renamed. | Before changing your domain name, review any sites connected to Teams channels or Microsoft 365 groups that are locked to determine if the lock should be removed. [Lock and unlock sites](manage-lock-status) |
| Multi-Geo configurations | You can't change your SharePoint domain name if your organization is currently set up for Microsoft 365 Multi-Geo or was previously set up for it. | No action available. |
| Point-in-time restoration | You can't restore a site to a previous time before the domain name change. | No action available. |
| Root site replacement | You can't replace your [root site](modern-root-site) (using either the SharePoint admin center or the PowerShell cmdlet Invoke-SPOSiteSwap) between the time you schedule your domain name change and when it completes. | Replace your root site before you schedule the domain name change or after it completes. |
| SharePoint public sites | If your tenant contains old SharePoint public sites, you can't change your SharePoint domain name. | Remove public sites on the tenant before scheduling tenant renaming. Submit a support request by selecting [Rename a SharePoint Tenant with Public site](https://admin.microsoft.com/AdminPortal/?searchSolutions=Rename%20a%20SharePoint%20Tenant%20with%20Public%20site). |
| Special and government clouds | If your organization uses special clouds or government clouds (GCC, GCC High, DoD, and so on), you can't change your domain name. | No action available. |
| Vanity domain configurations | If your SharePoint domain is, for example, `teams.contoso.com` (versus `contoso.sharepoint.com`), you can't change your domain name. | No action available. |
| Licenses | Purchase or update to licensing doesn't take effect during Rename | Wait until Rename completes |
| Admin Roles | Creating or updating Admin Roles doesn't take effect during Rename | Wait until Rename completes |
| Storage | Purchase or update to Storage doesn't take effect during Rename | Wait until Rename completes |

## What is Advanced Tenant Rename?

If you want to rename an organization with more than 10,000 total sites or want greater control over the rename operation, you must use Advanced Tenant Rename. It supports changing the SharePoint domain on tenants with any number of sites and has the ability for admins to prioritize up to 4,000 sites in their organization for early execution within the overall rename. This priority execution allows select business-critical or high-visibility sites to complete first and reduces any risk or concerns with its impact on daily operations.

Advanced Tenant Rename is a part of [SharePoint Advanced Management](advanced-management).

### What are the prerequisites?

Advanced Tenant Rename currently supports tenants that meet the following conditions:

- Meet [Prerequisites for SharePoint Advanced Management](sharepoint-advanced-management-prerequisites).
- Your organization doesn't have Microsoft 365 Multi Geo enabled.
- Your organization doesn't use government clouds, including GCC, GCC High, and DoD.
- Your organization doesn't use vanity domains (from an earlier MTE offering).

### How do I prioritize sites when renaming domain?

By using Advanced Tenant Rename, you can prioritize up to 4,000 sites for early execution. This list can include both OneDrive and SharePoint sites, but it excludes root sites (for example, `contoso.sharepoint.com`, `contoso-admin.sharepoint.com`, `contoso-my.sharepoint.com`).

The prioritized sites are processed first among all the sites in your organization. This priority gives them the opportunity to complete their renames sooner. Plan your tenant rename to start at the beginning of a low-impact period (such as weekends or holidays) and prioritize those sites that you believe are important to have accessible at the start of the next business day.

To manage prioritization, use the following PowerShell cmdlets.

- [Set-SPOTenantRenameSitePrioritization](/en-us/powershell/module/microsoft.online.sharepoint.powershell/set-spotenantrenamesiteprioritization?view=sharepoint-ps&amp;preserve-view=true) – Prioritize the specified site for early execution.
- [Remove-SPOTenantRenameSitePrioritization](/en-us/powershell/module/microsoft.online.sharepoint.powershell/remove-spotenantrenamesiteprioritization?view=sharepoint-ps&amp;preserve-view=true) – Remove prioritization for the specified site.
- [Get-SPOTenantRenameSitePrioritization](/en-us/powershell/module/sharepoint-online/get-spotenantrenamesiteprioritization) – View the current list of prioritized sites.

Use the PowerShell cmdlets for prioritization after you schedule the tenant rename. You can make changes to the list of prioritized sites up to two hours before the scheduled start time of the rename. Once the rename starts, the system doesn't accept further changes.

## Step 1: How do I add the new domain name?

1. Check the availability of the new domain you want. For example, if you want your SharePoint and OneDrive URLs to begin with `fabrikam.sharepoint.com`, enter `https://fabrikam.sharepoint.com` in a browser. If you get a message that the address couldn't be found (404), it's probably available. If you get a sign-in screen or a message that your username couldn't be found in the fabrikam.sharepoint.com directory, the domain is taken and you need to try a different one. If another customer already registered the domain, Microsoft can't provide any information or contact the customer.

    -or-

    If you own the domain for another subscription, you need to [delete that tenant in Microsoft Entra ID](/en-us/azure/active-directory/enterprise-users/directory-delete-howto). Deleting a tenant typically takes three days to complete and to make the domain available.

    Warning

    Don't use the domain to test this procedure in a test environment first. If you do, you won't be able to use the domain for your production environment.
2. [Add your new `.onmicrosoft.com` domain using the Domains page in the Microsoft 365 admin center](/en-us/microsoft-365/admin/setup/add-or-replace-your-onmicrosoftcom-domain#add-a-new-onmicrosoftcom-domain).

    - Don't use the **Add domain** option directly present in the Domains page, since that option doesn't create a `.onmicrosoft.com` domain. Use the steps in the specified link to correctly create one.
    - Don't make this domain your fallback domain.
3. Go back to the Domains page and check that the newly added `.onmicrosoft.com` domain appears in a **Healthy** state.

## Step 2: Use Microsoft PowerShell to rename your domain

Warning

- When the change of the SharePoint domain starts, sites that remain on the original domain are temporarily inaccessible. As each site gets renamed to the new domain, it becomes accessible again.
- Changing your SharePoint domain name might take several hours to days depending on the number of sites and OneDrive users that you have. Make this change during a period of low usage, such as a weekend, and tell users to avoid accessing SharePoint and OneDrive content during the change. In addition, any actions that create new OneDrive libraries and sites, such as creating a new team or private channel in Microsoft Teams, are temporarily blocked during the rename.
- Don't plan any UPN changes or renames while the change of your SharePoint domain name is in progress. Wait until after the domain name change is complete.

1. **REQUIRED** - [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251). If you installed a previous version of the SharePoint Online Management Shell, go to **Add or remove programs** and uninstall SharePoint Online Management Shell. Review the System Requirements and Install Instructions. The app isn't supported on Mac.
2. Connect to SharePoint as at least a [SharePoint Administrator](sharepoint-admin-role) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

    Run this command:

    ```powershell
    Connect-SPOService -Url "https://contoso-admin.sharepoint.com"
    ```
3. Run the following command to specify the new domain name:

    ```PowerShell
    Start-SPOTenantRename -DomainName <DomainName> -ScheduledDateTime <YYYY-MM-DDTHH:MM:SS> [-WhatIf] [-Confirm] 
    ```

    Where "DomainName" is the part before "sharepoint.com" or "onmicrosoft.com" and "ScheduledDateTime" is at least 24 hours in the future, but not more than 30 days. The time you enter is based on the current date and time of the computer you're using.

    Here's an example:

    ```powershell
    Start-SPOTenantRename -DomainName "fabrikam" -ScheduledDateTime "2021-12-31T10:25:00"
    ```

    If that PowerShell command isn't found or returns nothing, make sure you installed the latest SharePoint Online Management Shell. Before installing the latest version, you might need to uninstall all previous versions by running the following command:

    ```powershell
    Uninstall-Module Microsoft.Online.SharePoint.PowerShell -Force -AllVersions
    ```

    For more information, see [Start-SPOTenantRename](/en-us/powershell/module/sharepoint-online/start-spotenantrename).

    To cancel a rename before it starts, you can run the following command:

    ```powershell
    Stop-SPOTenantRename
    ```

    For more information, see [Stop-SPOTenantRename](/en-us/powershell/module/microsoft.online.sharepoint.powershell/stop-spotenantrename).

## Step 3: Prioritize sites (premium)

If you purchase SharePoint Advanced Management licenses for all users when you schedule your rename, the process automatically considers Advanced Tenant Rename and gives you the ability to prioritize sites.

Use the `Set-SPOTenantRenameSitePrioritization` cmdlet to prioritize individual sites. For example, to prioritize a site named *projectx*, run the following command:

```powershell
Set-SPOTenantRenameSitePrioritization -SiteUrl https://contoso.sharepoint.com/sites/projectx
```

If you already identified the list of sites you want prioritized and want to perform the Set operation in bulk, put the list in a CSV file and then use PowerShell to import it and iteratively execute the cmdlets. The file should have a single column with the title `SiteUrl`, and every subsequent row should be the full URL of the desired site.

Here's an example:

```powershell
Import-Csv <Path> | ForEach-Object {Set-SPOTenantRenameSitePrioritization -SiteUrl  $_.SiteUrl}
```

If you attempt this operation with a file that has all 4,000 sites in it, the complete execution of this cmdlet can take approximately 4-6 hours. If you want shorter waiting times, split your list of sites and run the command in batches.

To view the list of sites currently prioritized, run the following command:

```powershell
Get-SPOTenantRenameSitePrioritization
```

To remove prioritization for a site, run the following command:

```powershell
Remove-SPOTenantRenameSitePrioritization
```

For example, to remove prioritization for the `projectx` site, run the following command:

```powershell
Remove-SPOTenantRenameSitePrioritization -SiteUrl https://contoso.sharepoint.com/sites/projectx
```

Prioritizing a site isn't a guarantee that the site rename finishes first. Several factors can affect processing times, and the system processes multiple site renames in parallel. Prioritized sites have a higher chance of completing first.

## Step 4: Monitor the status of the rename

To check the status of the rename operation, run the following command:

```powershell
Get-SPOTenantRenameStatus
```

Make sure you open a new PowerShell window to sign in again. The date and time shown with this command is in UTC time but follows the local format of the system where the cmdlet is run.

For more information, see [Get-SPOTenantRenameStatus](/en-us/powershell/module/sharepoint-online/get-spotenantrenamestatus).

During and after the rename, you can get the state of a site by running the following command:

```powershell
Get-SPOSiteRenameState
```

For more information about this cmdlet, see [Get-SPOSiteRenameState](/en-us/powershell/module/sharepoint-online/get-spositerenamestate).

To verify success of the rename operation, review the status of the rename operation, and the count of renamed sites in comparison to total sites. The count of sites that can't be renamed to the new domain is shown in the **Attention Required** field.

To get more information on these sites, run the following command:

```powershell
Get-SPOSiteRenameState
``

Pass the `RenameJobID` listed in the tenant rename status as the `ParentOperationID`, and the status (such as Success, Failed, or Suspended). If you want to export these results to a CSV file, you can use the follownig cmdlet:

```powershell
Export-Csv
```

Here's an example:

```powershell
Get-SPOSiteRenameState -ParentOperationID <RenameJobID> -State Failed | Export-Csv -Path <Path>
```

## Step 5: Review features and settings after the rename

1. Review any firewall rules that might block access to the new domain.
2. Review organization browser settings to make sure the new domain is a trusted location. This action includes reviewing any Group Policy settings that might control browser settings.
3. Review any non-Microsoft apps, custom apps, and scripts that access SharePoint. They might need to be modified to use the new domain.
4. If you have custom SharePoint Framework solutions that require access to an API, check the API access page in the SharePoint admin center to ensure that SharePoint Framework components can use the new domain name.

## Troubleshooting

- [Frequently asked questions](/en-us/sharepoint/troubleshoot/administration/domain-rename-faq)
- [Errors and how to fix them](/en-us/sharepoint/troubleshoot/administration/errors-when-renaming)