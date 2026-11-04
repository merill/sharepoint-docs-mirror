---
layout: Conceptual
title: Control access from unmanaged devices - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/control-access-from-unmanaged-devices
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-01-26T00:00:00.0000000Z
ms.reviewer: samust
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
f1.keywords: CSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Strat_SP_admin
- M365-collaboration
- M365-sam
search.appverid:
- SPO160
- MET150
- BSA160
ms.assetid: 5ae550c4-bd20-4257-847b-5c20fb053622
description: Learn how administrators can block or limit access to SharePoint and OneDrive content on devices that aren't compliant or joined to a domain.
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
locale: en-us
document_id: 2f2abda5-9273-1a56-91b6-e4e77d5706b0
document_version_independent_id: 6a85f2a5-b892-55f7-b49a-4ab15f1e8b73
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/control-access-from-unmanaged-devices.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: control-access-from-unmanaged-devices
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/control-access-from-unmanaged-devices.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: b2162a22-7fc8-934d-3b43-f6bf17bb6e50
---

# Control access from unmanaged devices - SharePoint in Microsoft 365 | Microsoft Learn

With at least the permissions of a [SharePoint Administrator](sharepoint-admin-role) in Microsoft 365, you can block or limit access to SharePoint and OneDrive content from unmanaged devices (those not [hybrid AD joined](/en-us/azure/active-directory/devices/overview#hybrid-azure-ad-joined-devices) or compliant in Intune). You can block or limit access for:

- All users in the organization or only some users or security groups.
- All sites in the organization or only some sites.

### What happens when access is blocked or limited?

Blocking access helps provide security but comes at the cost of usability and productivity. When access is blocked, users see the following error:

> 
> Access Denied. Due to organization policy, you can't access this resource from this untrusted device.

![The experience when access is blocked](sharepointonline/media/unmanaged-device-access-blocked.png)

Limiting access allows users to remain productive while addressing the risk of accidental data loss on unmanaged devices. When you limit access, users on managed devices have full access (unless they use one of the browser and operating system combinations listed in [Supported browsers](/en-us/azure/active-directory/conditional-access/concept-conditional-access-conditions#supported-browsers)). Users on unmanaged devices have browser-only access with no ability to download, print, or sync files. They also won't be able to access content through apps, including the Microsoft Office desktop apps. When you limit access, you can choose to allow or block editing files in the browser. When web access is limited, users see the following message at the top of sites.

![The experience when web access is limited](sharepointonline/media/unmanaged-device-limited-web-access.png)

Note

- Blocking or limiting access on unmanaged devices relies on Microsoft Entra Conditional Access policies. [Learn about Microsoft Entra ID licensing](https://azure.microsoft.com/pricing/details/active-directory/) For an overview of conditional access in Microsoft Entra ID, see [Conditional access in Microsoft Entra ID](/en-us/azure/active-directory/conditional-access/overview).
- For info about recommended SharePoint access policies, see [Policy recommendations for securing SharePoint sites and files](/en-us/microsoft-365/enterprise/sharepoint-file-access-policies).
- If you limit access on unmanaged devices, users on managed devices must use one of the [supported OS and browser combinations](/en-us/azure/active-directory/conditional-access/technical-reference#client-apps-condition), or they will also have limited access.
- Because Microsoft Entra ID doesn't offer [Multi-Geo Capabilities](https://www.microsoft.com/en-us/microsoft-365/business/multi-geo-capabilities), blocking or limiting unmanaged devices impact all Geos within the Microsoft 365 tenant.

## How do I control device access across Microsoft 365?

The procedures in this article only affect SharePoint access by unmanaged devices. If you want to expand control of unmanaged devices beyond SharePoint, you can [Create a Microsoft Entra Conditional Access policy for all apps and services in your organization](/en-us/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device) instead. To configure this policy specifically for [Microsoft 365 services](/en-us/azure/active-directory/conditional-access/concept-conditional-access-cloud-apps#office-365), select the **Office 365** cloud app under **Cloud apps or actions**.

![Screenshot of the Office 365 cloud app in a Microsoft Entra Conditional Access policy](sharepointonline/media/azure-ca-office365-policy.png)

Using a policy that affects all Microsoft 365 services can lead to better security and a better experience for your users. For example, when you block access to unmanaged devices in SharePoint only, users can access the chat in a team with an unmanaged device, but will lose access when they try to access the **Files** tab. Using the Office 365 cloud app helps avoid issues with [service dependencies](/en-us/azure/active-directory/conditional-access/service-dependencies).

## How do I block access?

1. Go to [**Access control** in the new SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185071), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the Access control page.
2. Select **Unmanaged devices**.

    ![The Unmanaged devices pane in the SharePoint admin center](sharepointonline/media/unmanaged-devices-block-access.png)
3. Select **Block access**, and then select **Save**.

    Important

    - Selecting this option disables any previous conditional access policies you created from this page, and creates a new conditional access policy that applies to all users. Any customizations you made to previous policies won't be carried over.
    - It can take up to 24 hours for the policy to take effect. It won't take effect for users who are already signed in from unmanaged devices.
    - If you block access from unmanaged devices, we recommend also blocking access from apps that don't use modern authentication. Some third-party apps and versions of Office prior to Office 2013 don't use modern authentication and can't enforce device-based restrictions. This means they allow users to bypass conditional access policies that you configure in Azure. In [**Access control** in the new SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185071), select **Apps that don't use modern authentication**, select **Block access**, and then select **Save**.

## How do I limit access?

1. Go to [**Access control** in the new SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185071), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

    Note

    If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and select **Policies** to expand, then select **Access Control**.
2. Select **Unmanaged devices**.
3. Select **Allow limited, web-only access**, and then select **Save**. (Note that selecting this option disables any previous conditional access policies you created from this page and create a new conditional access policy that applies to all users. Any customizations you made to previous policies won't be carried over.)

    ![The Unmanaged devices pane in the new SharePoint admin center](sharepointonline/media/unmanaged-devices-limit-access.png)

    If you revert back to **Allow Full Access**, it could take up to 24 hours for the changes to take effect.

    Important

    - If you limit access from unmanaged devices, we recommend also blocking access from apps that don't use modern authentication. Some third-party apps and versions of Office prior to Office 2013 don't use modern authentication and can't enforce device-based restrictions. This means they allow users to bypass conditional access policies that you configure in Azure. In [**Access control** in the new SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185071), select **Apps that don't use modern authentication**, select **Block access**, and then select **Save**.
    - If you limit access and edit a site from an unmanaged device, image web parts won't display images that you upload to the site assets library or directly to the web part. To work around this issue, you can use this [SPList API](/en-us/previous-versions/office/sharepoint-server/mt796229%28v%3Doffice.15%29) to exempt the block download policy on the site assets library. This allows the web part to download images from the site assets library.
    - When Access Control for Unmanaged Devices in SharePoint is set to **Allow limited, web-only access**, SharePoint files can't be downloaded but they can be previewed. The previews of Office files work in SharePoint but the previews don't work in Microsoft Viva Engage.

## How do I limit access using PowerShell?

1. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    Note

    If you installed a previous version of the SharePoint Online Management Shell, go to **Add or remove programs**, and uninstall **SharePoint Online Management Shell**.
2. Connect to SharePoint with at least the permissions of a [SharePoint Administrator](sharepoint-admin-role) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
3. Run the following command:

    ```PowerShell
    Set-SPOTenant -ConditionalAccessPolicy AllowLimitedAccess
    ```

    Note

    By default, this policy allows users to view and edit files in their web browser. To change this, see [Advanced configurations](control-access-from-unmanaged-devices#what-are-the-advanced-configurations-for-limiting-access).

## How do I block or limit access to a specific SharePoint site or OneDrive?

To block or limit access to specific sites, follow these steps. If you have configured the organization-wide policy, the site-level setting you specify must be at least as restrictive as the organization-level setting.

1. Manually create a policy in the Microsoft Entra admin center by following the steps in [Use app-enforced restrictions](app-enforced-restrictions).
2. Set the site-level setting by using PowerShell, or a [sensitivity label](/en-us/microsoft-365/compliance/sensitivity-labels):

    - To use PowerShell, continue to the next step.
    - To use a sensitivity label, see the following instructions and specify the label setting for **Access from unmanaged devices**: [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](/en-us/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).
3. To use PowerShell: [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    Note

    If you installed a previous version of the SharePoint Online Management Shell, go to **Add or remove programs** and uninstall **SharePoint Online Management Shell**.
4. Connect to SharePoint with at least the permissions of a [SharePoint Administrator](sharepoint-admin-role) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
5. Run one of the following commands.

    To block access to a single site:

    ```PowerShell
    Set-SPOSite -Identity https://<SharePoint online URL>/sites/<name of site or OneDrive account> -ConditionalAccessPolicy BlockAccess
    ```

    To limit access to a single site:

    ```PowerShell
    Set-SPOSite -Identity https://<SharePoint online URL>/sites/<name of site or OneDrive account> -ConditionalAccessPolicy AllowLimitedAccess
    ```

    To update multiple sites at once, use the following command as an example:

    ```PowerShell
    Get-SPOSite -IncludePersonalSite $true -Limit all -Filter "Url -like '-my.sharepoint.com/personal/'" | Set-SPOSite -ConditionalAccessPolicy AllowLimitedAccess
    ```

    This example gets the OneDrive for every user and passes it as an array to Set-SPOSite to limit access.

Note

By default, a setting that includes web access allows users to view and edit files in their web browser. To change this, see [Advanced configurations](control-access-from-unmanaged-devices#what-are-the-advanced-configurations-for-limiting-access).

## What are the advanced configurations for limiting access?

You can use the following parameters with `-ConditionalAccessPolicy AllowLimitedAccess` for both the organization-wide setting and the site-level setting:

`-AllowEditing $false` Prevents users from editing Office files in the browser.

`-ReadOnlyForUnmanagedDevices $true` Makes the entire site read-only for impacted users.

`-LimitedAccessFileType OfficeOnlineFilesOnly` Allows users to preview only Office files in the browser. This option increases security but may be a barrier to user productivity.

`-LimitedAccessFileType WebPreviewableFiles` (default) Allows users to preview Office files in the browser. This option optimizes for user productivity but offers less security for files that aren't Office files. **Warning:** This option is known to cause problems with PDF and image file types because they can be required to be downloaded to the end user's machine to render in the browser. Plan the use of this control carefully. Otherwise, your users could be faced with unexpected "Access Denied" errors.

`-LimitedAccessFileType OtherFiles` Allows users to download files that can't be previewed, such as .zip and .exe. This option offers less security. If this mode is enabled, then for downloading files like .zip or .exe, you can copy the url of the file and paste in browser (example: `https://contoso.sharepoint.com/:u:/r/sites/test/Shared%20Documents/test1.zip`).

The `AllowDownlownloadingNonWebViewableFiles` parameter is no longer supported. Use `LimitedAccessFileType` instead.

People outside the organization will be affected when you use conditional access policies to block or limit access from unmanaged devices. If users have shared items with specific people (who must enter a verification code sent to their email address), you can exempt them from this policy by running the following command.

```powershell
Set-SPOTenant -ApplyAppEnforcedRestrictionsToAdHocRecipients $false
```

Note

"Anyone" links (shareable links that don't require sign-in) aren't affected by these policies. People who have an "Anyone" link to a file or folder will be able to download the item. For all sites where you enable conditional access policies, you should disable "Anyone" links.

## How does this affect apps?

Blocking access and blocking download may impact the user experience in some apps, including some Office apps. We recommend that you turn on the policy for some users and test the experience with the apps used in your organization. In Office, make sure to check the behavior in Power Apps and Power Automate when your policy is on.

Note

Apps that run in "app-only" mode in the service, like antivirus apps and search crawlers, are exempted from the policy.

If you're using classic SharePoint site templates, site images may not render correctly. This is because the policy prevents the original image files from being downloaded to the browser.

For new tenants, apps using an ACS app-only access token is disabled by default. We recommend using the Microsoft Entra ID app-only model which is modern and more secure. But you can change the behavior by running `set-spotenant -DisableCustomAppAuthentication $false` (needs the latest SharePoint admin PowerShell).

## Need more help?

[SharePoint Q&A](/en-us/answers/topics/office-sharepoint-online.html)