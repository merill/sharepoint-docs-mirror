---
layout: Conceptual
title: The OneDrive sync app update process - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/sync-client-update-process
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-07-27T00:00:00.0000000Z
ms.reviewer: kangan
ms.author: v-mactran
author: MachelleTranMSFT
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: reference
ms.service: onedrive
ms.localizationpriority: medium
ms.collection:
- Strat_OD_admin
- M365-collaboration
- essentials-overview
ms.custom: onedrive-toc
search.appverid:
- ODB160
- MET150
ms.assetid: 2f748bc6-6f01-4406-a791-ec047f066d6d
description: Learn about the Production and Deferred rings for OneDrive sync app updates
locale: en-us
document_id: 2cfa335a-deb6-2ef2-6232-1347984121e1
document_version_independent_id: e0f5b223-3d5b-1415-06e8-6db004b92320
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/sync-client-update-process.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: sync-client-update-process
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/sync-client-update-process.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 55043e5a-3f5b-aca0-e3bf-757e22ae3710
---

# The OneDrive sync app update process - SharePoint in Microsoft 365 | Microsoft Learn

This article is for IT admins who manage the OneDrive sync app (OneDrive.exe) in an enterprise environment. It explains how we release updates to the sync app for Windows and the standalone sync app for Mac through rings of validation, and how the app checks for updates. If you deploy the sync app alongside Office (via the Office Deployment Tool or some other means), it continues to check for updates independent of any Office update restrictions you set.

Note

If you allow your users to sync personal OneDrive accounts, the update process described in this article and any settings you select apply to all instances of the sync app.

The sync app installed from the Mac App Store follows a separate update process. After we finish rolling out updates within the Production ring, we publish them to the Mac App Store, where they're immediately released to everyone.

## How we release updates through multiple rings

After we validate updates through rings within Microsoft, we release them to the first public ring, Insiders. To try these latest features, join the [Windows Insider program](https://insider.windows.com/) or the [Office Insider](https://products.office.com/office-insider) program. It takes about three days to roll out to this ring. Later, we release to organizations in the default update ring, Production. We roll them out to a small percentage of users in the ring at first, and slowly roll them out to everyone in the ring. This process typically takes one to two weeks. At each increase along the way, we monitor telemetry for quality assurance purposes. In the rare case when we detect an issue, we suspend the release, address the issue, and release a new update to users in the same order. After updates roll out completely within the Production ring, and remain in Production for at least 60 days, we release them to the next ring, Deferred.

| Insiders | &gt; | Production | &gt; | Deferred |
| --- | --- | --- | --- | --- |
| 1-2 times per week | &gt; | Every 1-2 weeks | &gt; | Every 2-3 months |

Important

We recommend selecting several people in your IT department as early adopters to join the Insiders ring and receive features early. We recommend leaving everyone else in the organization in the default Production ring to ensure they receive bug fixes and new features in a timely fashion. [See all our recommendations for configuring the sync app](ideal-state-configuration)

The Deferred ring provides builds that were monitored throughout the Production rollout, so fewer releases are suspended. The Deferred ring also lets you as an admin:

- Control when you deploy updates (within 60 days of their release).
- Deploy new versions from an internal network location to avoid using Internet bandwidth. (If you don't deploy an update after 60 days, it will be automatically downloaded and installed.)

However, as the slowest ring, the Deferred ring receives performance improvements, reliability fixes, and new features last.

Note

Microsoft reserves the right to bypass the 60-day grace period for critical updates.

- To learn how to set the Deferred ring for the Windows sync app using Group Policy, see [Set the sync app update ring](use-group-policy#set-the-sync-app-update-ring).
- To learn how to set it for the Mac sync app, see [Configure the new OneDrive sync app on macOS](deploy-and-configure-on-macos).
- For info about the Microsoft 365 update process, see [Overview of update channels for Microsoft 365 Apps for enterprise](/en-us/DeployOffice/overview-of-update-channels-for-office-365-proplus).

## How the sync app checks for and applies updates

The OneDrive sync app checks for available updates every 24 hours when it's running. If it stops and doesn't check for updates in more than 24 hours, the sync app checks for updates as soon as it starts. Windows also has a scheduled task that updates the sync app even when it's not running.

To determine if an update is available, the OneDrive sync app checks if:

- The latest version released to the update ring is higher than what is installed on the computer. If the installed version is too old to be updated to the current version, the sync app first updates to the minimum version within the ring.
- The update is available to the computer based on the rollout percentage we set within the ring.

If both of these conditions are true, OneDrive downloads the update to a hidden folder without any user interaction. After the download is complete, OneDrive verifies and installs it. If OneDrive is running, it stops and then restarts. Users don't need to sign in again, and they don't need administrative rights to install the update.

For info about the latest releases, see [New OneDrive sync app release notes](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).

Note

To apply sync app updates, computers in your organization must be able to reach the following: "oneclient.sfx.ms" and "g.live.com." Make sure you don't block these URLs. They're also used to enable and disable features and apply bug fixes. See [More info about the URLs and IP address ranges used in Microsoft 365](/en-us/office365/enterprise/urls-and-ip-address-ranges).

## Deploying updates in the Deferred ring

At any given time, the next planned Deferred ring release publishes on the [OneDrive sync app release notes](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0) page with a link to the corresponding installer and the version's targeted release date. On the specified date, the "Rolling out" version for the Deferred ring becomes the new minimum. All sync apps below that version automatically download the installer from the Internet and update themselves.

To deploy an updated version of the sync app for Windows, run the following command using Microsoft Endpoint Configuration Manager:

```
Execute <pathToExecutable>\OneDriveSetup.exe /update /restart
```

Where pathToExecutable is a location on the local computer or an accessible network share and OneDriveSetup.exe is the target version downloaded from the release notes page. Running this command restarts OneDrive.exe on all computers. If you don't want to restart the sync app, remove the /restart parameter. See [Deploy using Microsoft Endpoint Configuration Manager](deploy-on-windows) for tips on how to set up the Microsoft Endpoint Configuration Manager deployment package.

To deploy an updated version of the sync app for Mac, deploy the OneDrive.pkg with the target version by using your MDM solution.