---
layout: Conceptual
title: Deploy Restrict Known Folder Move from Office Group Policy - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/restrict-known-folder-move-office-group-policy
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-04-21T00:00:00.0000000Z
ms.reviewer: nirupama.m
manager: jtremper
ms.author: v-mactran
author: MachelleTranMSFT
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: onedrive
ms.localizationpriority: medium
ms.custom:
- has-azure-ad-ps-ref
ms.collection:
- M365-collaboration
- Highpri
- Tier2
search.appverid: 
description: Learn how to deploy the Restrict Known Folder Move from Office Group Policy to prevent Office apps from prompting users to back up files to OneDrive.
locale: en-us
document_id: bf90c5a4-61fd-37a3-f362-e75cf2b41f2d
document_version_independent_id: f1d15809-e40b-48f9-c9ce-9e01968024a0
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/restrict-known-folder-move-office-group-policy.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: restrict-known-folder-move-office-group-policy
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/restrict-known-folder-move-office-group-policy.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/19e6356c-ba1e-4d22-9557-6222c183f04d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/01e6eca5-e701-4cd9-a21f-56c9258f473e
platformId: 25fd249a-a2a0-b44d-add0-6ae283b2c487
---

# Deploy Restrict Known Folder Move from Office Group Policy - SharePoint in Microsoft 365 | Microsoft Learn

The Restrict Known Folder Move from Office (Restrict KFM from Office) Group Policy allows administrators to control whether Office apps display prompts encouraging users to back up their files to Microsoft OneDrive.

When this policy is enabled and deployed, Office doesn't display the message bar, even if users are eligible for the Known Folder Move (KFM) feature. This policy applies only to Office apps and doesn't affect other OneDrive or KFM configurations. It's available in the [Administrative Template files for Microsoft Office](https://www.microsoft.com/download/details.aspx?id=49030) (version 5497.1000 or newer).

Tip

- Enable this policy if you don’t want users to see prompts to back up their files.
- If KFM is blocked in your organization, the message bar doesn't appear, even if users are eligible.
- Microsoft respects existing policies that block KFM and doesn't display prompts in those environments.

## What users see when eligible

When the policy isn't enabled, eligible users might see a message bar in Microsoft Word, Excel, and PowerPoint (Windows desktop versions) prompting them to enroll in [OneDrive Known Folder Move (KFM)](/en-us/sharepoint/redirect-known-folders). The message bar allows users to select folders to back up to OneDrive.

Important

If users aren't enrolled in KFM, they might see the message:**"BACK UP THIS DOCUMENT: Share and work with others in this and other files using OneDrive."**

Selecting **Open OneDrive** lets users choose which folders to back up.

By enabling and deploying the **Restrict KFM from Office** Group Policy, administrators can prevent these prompts and maintain control over KFM adoption.

## When the Message Bar isn't displayed

The message bar doesn't appear under the following conditions:

- The user is already enrolled in KFM.
- OneDrive isn't provisioned, installed, or running.
- The policy [Prevent users from moving their Windows known folders to OneDrive](/en-us/sharepoint/use-group-policy#prevent-users-from-moving-their-windows-known-folders-to-onedrive) is enabled.
- The **Restrict KFM from Office** policy is enabled.

## Deployment methods

### Option 1: Deploy via Group Policy (Active Directory or hybrid environments)

If you're using Active Directory, Microsoft Entra, or a hybrid environment, you can deploy the policy using [Group Policy Objects (GPOs)](/en-us/previous-versions/windows/desktop/policy/group-policy-objects).

1. Download the [Administrative Template files (ADMX/ADML) for Microsoft Office](https://www.microsoft.com/download/details.aspx?id=49030).
2. Select **Download**, then choose the 32-bit (x86), 64-bit (x64), or both versions.
3. Select **Next**, then choose a location to save the file.
4. Run the downloaded **admintemplates\_XXXXXXX\_en-us.exe** and follow the prompts to extract the files.
5. After extracting, you'll see **admin** and **admx** folders.
6. On your Active Directory server:
    - Copy the `.admx` files into **%SYSTEMROOT%\PolicyDefinitions**
    - Copy the corresponding language `.adml` files into **%SYSTEMROOT%\PolicyDefinitions[Language-CountryRegion]**
        - For example, copy U.S. English `.adml` files into the `en-us` folder.
7. Open **Group Policy Management**.
8. Under **Domains**, select the appropriate policy (for example, **Default Domain Policy**) and choose **Edit**.
9. In the Group Policy Management Editor, go to:**User Configuration** &gt; **Policies** &gt; **Administrative Templates: Policy Definitions** &gt; **All Settings**
10. Locate **Restrict KFM from Office**, right-click it, and select **Edit**.
11. Change the setting from **Not Configured** to **Enabled**, then select **Apply** and **OK**.
12. The policy setting should now display as **Enabled**.

[![Screenshot shows comment being added to the Restrict KFM from Office tool.](sharepointonline/media/restrict-kfm-from-office/0-restrict-kfm-from-office-group-policy-editor.jpg)](sharepointonline/media/restrict-kfm-from-office/0-restrict-kfm-from-office-group-policy-editor.jpg#lightbox)

[![Screenshot that shows the disabling KFM pop ups via the Group Policy Management editor.](sharepointonline/media/restrict-kfm-from-office/1-restrict-kfm-from-office-group-policy-editor-all-settings.jpg)](sharepointonline/media/restrict-kfm-from-office/1-restrict-kfm-from-office-group-policy-editor-all-settings.jpg#lightbox)

Note

It might take up to 24 hours for the policy to take effect.

### Option 2: Deploy via Cloud Policy service

You can also deploy this policy using the [Cloud Policy service for Microsoft 365](https://config.office.com/officeSettings/officePolicies). This method works even if the device isn't domain-joined. When a user signs into Microsoft 365 Apps for Enterprise on a device, the policy settings roam to that device. See [Overview of Cloud Policy](/en-us/microsoft-365-apps/admin-center/overview-cloud-policy) to learn more about cloud policies for Microsoft 356 Apps.

To deploy the policy:

1. Sign in to the [Microsoft 365 Apps admin center](https://config.office.com/) with administrative credentials.
2. Under **Customization**, select **Policy Management**.
3. On the **Policy configurations** page, select **Create**.
4. On the **Start with the basics** page, enter a **Name** (required) and **Description** (optional), then select **Next**.
5. On the **Choose the scope**page, select whether the policy applies to:
    - All users
    - Specific groups
    - Users accessing Office for the web anonymously
6. If applying to specific groups, select **Add Groups** and choose the relevant groups.

Note

Adding multiple groups to a single policy configuration allows for the same group to be included in multiple policy configurations, facilitating a more streamlined and efficient policy management process.

1. Select **Next**.
2. On the **Configure Settings**page:
    - Search for **Restrict KFM from Office** or use a filter.
    - Set the configuration to **Enabled**, then select **Apply**.
3. Review your selections and choose **Create**.
4. Select **Done**.

[![screenshot of KFM configuration settings](sharepointonline/media/restrict-kfm-from-office/2-restrict-kfm-from-office-group-policy-configure-cloud-policy.jpg)](sharepointonline/media/restrict-kfm-from-office/2-restrict-kfm-from-office-group-policy-configure-cloud-policy.jpg#lightbox)

Once configured, the policy will apply to eligible users the next time they sign in to Microsoft 365 Apps on any device.