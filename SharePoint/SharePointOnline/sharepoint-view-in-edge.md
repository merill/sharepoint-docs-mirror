---
layout: Conceptual
title: View SharePoint files with File Explorer in Microsoft Edge - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/sharepoint-view-in-edge
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2024-11-25T00:00:00.0000000Z
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Strat_SP_admin
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
search.appverid:
- SPO160
- BSA160
- GSP150
- MET150
description: Learn about SharePoint view in File Explorer for Microsoft Edge.
locale: en-us
document_id: 2c3f9bb0-43af-b544-3fd7-71eed410cbec
document_version_independent_id: 250786b4-90f1-0eab-c15d-2f0182d69e5e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/sharepoint-view-in-edge.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: sharepoint-view-in-edge
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/sharepoint-view-in-edge.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/5287f575-02f0-405f-92b7-800456526b0c
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/06e86142-34c2-4b94-ab9c-9477c21f7152
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: df5da76b-0bc2-0726-1ee2-ab7c20694804
---

# View SharePoint files with File Explorer in Microsoft Edge - SharePoint in Microsoft 365 | Microsoft Learn

Important

In June 2022, we stopped supporting Internet Explorer 11 (IE 11) at Microsoft 365 apps and services. As a result, we no longer recommend View in File Explorer and encourage using the OneDrive sync client. The OneDrive sync client provides [Files On-Demand](https://support.office.com/article/0e6860d3-d9f3-4971-b321-7092438fb38e), which allows you to access all your files in SharePoint without using up local storage space. For info about using OneDrive to sync SharePoint files, visit [SharePoint file sync](sharepoint-sync).

By default, the View in File Explorer menu option won't be visible to you or users in the SharePoint modern document library interface. In certain cases, organizations may still need to use View in File Explorer to access modern document libraries. Starting in Microsoft Edge Stable version 93, you can enable the View in File Explorer capability on SharePoint for modern document libraries.

## Configure View in File Explorer with Microsoft Edge

Follow the steps below to use View in File Explorer in Microsoft Edge:

1. Verify that devices are on Microsoft Edge build 93 or later using [Find out which version of Microsoft Edge you have](https://support.microsoft.com/en-us/microsoft-edge/find-out-which-version-of-microsoft-edge-you-have-c726bee8-c42e-e472-e954-4cf5123497eb).
2. Ensure that Windows instances are joined to a Microsoft Active Directory domain, Windows 10 Pro, or Enterprise instances that are enrolled for device management.
3. Enable the [ConfigureViewInFileExplorer](/en-us/deployedge/microsoft-edge-policies#configureviewinfileexplorer) policy for Microsoft Edge that allows URLs with the viewinfileexplorer: scheme to open WebDAV URLs in Windows File Explorer.

    Use the options below to enable View in File Explorer using group policy or Intune:

    - **To enable by using group policy**:

        1. Configure Microsoft Edge policy settings by following the steps at [Configure Microsoft Edge policy settings on Windows](/en-us/deployedge/configure-microsoft-edge).
        2. Make sure you've downloaded the Microsoft Edge administrative template [based on the operating system version](/en-us/troubleshoot/windows-client/group-policy/create-and-manage-central-store#links-to-download-the-administrative-templates-files-based-on-the-operating-system-version) or you may not see the policy listed.
        3. Once the template is downloaded, open the Group Policy Object Editor. Right-click **Administrative Templates** in the Computer Configuration or User Configuration node and select **Add/Remove Templates** and browse to the downloaded template.
        4. When applying the policy, ensure you update the domain to your tenant domain or use **sharepoint.com** if you plan on visiting multiple SharePoint tenants.
        5. Enabling the group policy may require a refresh of client group policy settings. After changing the group policy settings, refresh the settings. From a Command Prompt, enter **GPUpdate.exe /force**.

            Following is an example of the Group Policy value:

            `[{"cookies": ["rtFa", "FedAuth"], "domain": "sharepoint.com"}]`

            For more examples, see [ConfigureViewInFileExplorer](/en-us/deployedge/microsoft-edge-policies#configureviewinfileexplorer) on Microsoft Edge policy reference.
    - **To enable by using Intune**:

        Configure Microsoft Edge policy settings by following the steps at [Configure Microsoft Edge policy settings with Microsoft Intune](/en-us/deployedge/configure-edge-with-intune).
4. Verify the policy has been enabled by opening Microsoft Edge and navigating to **Microsoft Edge://policy/**.

    Tip

    You may need to close and re-open Microsoft Edge for the policy to appear.
5. As a tenant administrator, update your SharePoint Online tenant configuration via SharePoint Online Management Shell to allow the "View in File Explorer" option to be visible in the Microsoft Edge Browser interface with these steps:

    1. Connect to SharePoint Online Management Shell by running:

        ```PowerShell
        Connect-SPOService -Url https://contoso-admin.sharepoint.com
        ```
    2. Run the following cmdlet to show the "View in File Explorer" menu option:

        ```PowerShell
        Set-SPOTenant -ViewInFileExplorerEnabled $True
        ```

        Note

        Ensure the management shell version is 16.0.21610.12000 or higher or the ViewInFileExplorerEnabled option will not be available.
6. **(Required)***View in File Explorer* requires persistent cookies to operate correctly; when you sign in, select **Yes** when the **Stay signed in?** prompt appears.

    You can locate the View in Explorer button by navigating to the **Library** &gt; select the **Library View Menu** on the right-hand side &gt; select **View In File Explorer**.

    ![Screenshot of the menu for View in File Explorer.](sharepointonline/media/view-in-file-explorer.png)

    Note

    Once the tenant setting has been enabled, it may take up to 15 minutes for the View in Explorer button to appear in the SharePoint interface.

### Troubleshooting

**How can I confirm that the ConfigureViewInFileExplorer policy has been applied?**

You can verify that the policy has been applied by navigating to **edge://policy**.

**The error message *This policy is blocked - its value will be ignored* appeared while checking to see if the policy was applied via edge://policy. What's wrong?**

This error occurs when you attempt to apply this policy to a nondomain joined device. Currently, the ConfigureViewInFileExplorer policy can only be applied to Windows instances that are joined to a Microsoft Active Directory domain, Windows 10 Pro, or Enterprise instances enrolled for device management.

[![Screenshot of the user interface of the 'This policy is blocked - its value will be ignored' error message.](sharepointonline/media/edge-error.png)](sharepointonline/media/edge-error.png#lightbox)

**What happens if I have the policy applied without the tenant setting enabled?**

If you don't enable ViewInFileExplorerEnabled via [Set-SPOTenant](/en-us/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps&amp;preserve-view=true), the View in File Explorer button won't appear in the interface of the SharePoint site.

**What happens if the tenant setting is enabled without the Edge policy applied?**

If you have enabled ViewInFileExplorerEnabled, you may see the View In File Explorer button appear in your SharePoint library, however, clicking the button results in a blank screen.

![Screenshot of a blank screen that appears when the tenant setting is enabled without the policy applied.](sharepointonline/media/edgepolicy-blank-screen.png)

**When running Set-SPOTenant -ViewInFileExplorerEnabled $True I received the error "The requested operation is part of an experimental feature that is not supported in the current environment". What's wrong?**

You may receive this error if this functionality isn't supported in your current environment. We're still rolling out functionality to all Production environments and will update this article once worldwide rollout has been completed.

## Learn More

- [Sync SharePoint and Team files with your computer](https://support.microsoft.com/office/sync-sharepoint-and-teams-files-with-your-computer-6de9ede8-5b6e-4503-80b2-6190f3354a88)
- [View and open SharePoint with File Explorer](https://support.microsoft.com/office/view-and-open-sharepoint-files-with-file-explorer-66b574bb-08b4-46b6-a6a0-435fd98194cc)
- [Troubleshoot View in File Explorer](/en-us/sharepoint/troubleshoot/lists-and-libraries/troubleshoot-issues-using-open-with-explorer)
- [Set-SPOTenant](/en-us/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps&amp;preserve-view=true)
- [OneDrive sync reports in the Apps Admin Center](/en-us/onedrive/sync-health)