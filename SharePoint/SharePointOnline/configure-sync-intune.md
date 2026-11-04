---
layout: Conceptual
title: Configure settings with Intune - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/configure-sync-intune
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-04-10T00:00:00.0000000Z
ms.reviewer: scott.breen
ms.author: v-mactran
author: MachelleTranMSFT
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: onedrive
ms.localizationpriority: medium
ms.collection:
- Strat_OD_admin
- M365-collaboration
- onedrive-toc
search.appverid:
- MET150
- ODB160
- MOE150
- MED150
- MBS150
- ODB150
description: In this article, you learn how to configure the Microsoft OneDrive sync app by using settings catalog in Microsoft Intune.
locale: en-us
document_id: 5819c062-ce62-d10b-6337-adddce29bbd5
document_version_independent_id: ab2a560f-9389-b3cc-c9b7-459ff34d9b52
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/configure-sync-intune.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: configure-sync-intune
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/configure-sync-intune.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/a72e95ff-4b4f-4cc1-90c6-7dcba67ff05f
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/24dc3ccd-591a-4415-a1fe-8759afafcb12
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 018905a8-c866-ccca-6cc7-a6ab4da28364
---

# Configure settings with Intune - SharePoint in Microsoft 365 | Microsoft Learn

Profiles in Microsoft Intune let you configure settings and push them to devices in your organization. The settings catalog built into Microsoft Intune make configuring the Microsoft OneDrive sync app easier than ever.

## Create a profile

1. Sign in to the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Select **Devices** &gt; **Configuration** &gt; **Create**.
3. Enter the following properties:

    - **Platform**: Select **Windows 10 and later**.
    - **Profile type**: Select **Settings catalog**.
4. Select **Create**.
5. In **Basics**, enter the following properties:

    - **Name**: Enter a descriptive name for the profile. Name your profiles so you can easily identify them later. For example, a good profile name is **Windows: OneDrive**.
    - **Description**: Enter a description for the profile. This setting is optional, but recommended.
6. Select **Next**.
7. In **Configuration settings**, select **Add settings**.
8. In the settings picker, select **OneDrive** to see all the available settings.
9. Select any setting you want to configure. Or, choose **Select all these settings**. After you add your settings, close the settings picker. For info about these settings, see [Use OneDrive policies](use-group-policy). For info about the recommended settings, see [Recommended sync app configuration](ideal-state-configuration).

    [![A screenshot showing the configuration of the Intune settings catalog policy for OneDrive.](sharepointonline/media/intune-settings-catalog.png)](sharepointonline/media/intune-settings-catalog.png#lightbox)
10. Configure the settings the way you want, and then select **OK**.

    Note

    Some settings require entering your tenant ID. [Learn how to find it](find-your-office-365-tenant-id). When you're done, select **Next**.
11. Select scope tags, and then select **Next**. For information about scope tags, see [Use role based access controls (RBAC) and scope tags for distributed IT](/en-us/intune/intune-service/fundamentals/scope-tags).
12. In **Assignments**, include or exclude the profile from selected groups. For info about assigning profiles, see [Assign user and device profiles](/en-us/intune/intune-service/configuration/device-profile-assign).

    Note

    If the profile is assigned to user groups, then configured Administrative Template Files (ADMX) settings apply to any device that the user enrolls, and signs in to. If the profile is assigned to device groups, then configured ADMX settings apply to any user that signs into that device. This assignment happens if the ADMX setting is a computer configuration (`HKEY_LOCAL_MACHINE`), or a user configuration (`HKEY_CURRENT_USER`). With some settings, a computer setting assigned to a user can also affect the experience of other users on that device.

    For more info, see [User groups vs. device groups](/en-us/intune/intune-service/configuration/device-profile-assign).

    When you're done, select **Next**.
13. In **Review + create**, review your settings. When you select **Create**, your changes are saved, and the profile is assigned. The policy is also shown in the profiles list.