---
layout: Conceptual
title: Restrict OneDrive access by security group - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/limit-access
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-07-01T00:00:00.0000000Z
ms.reviewer: nibandyo
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
customer-intent: As a SharePoint administrator, I want to restrict all OneDrive access to specific security groups.
f1.keywords:
- CSH
ms.topic: how-to
ms.service: onedrive
ms.localizationpriority: medium
ms.collection:
- Strat_OD_admin
- Highpri
- Tier2
- M365-sam
- M365-collaboration
- essentials-compliance
- essentials-security
search.appverid: 
ms.assetid: 
ms.custom:
- admindeeplinkSPO
- onedrive-toc
description: Learn how to allow only users in specified security groups to access the OneDrive service.
locale: en-us
document_id: 33c02128-4157-692a-e161-7208faf41756
document_version_independent_id: 8e50bb47-75c6-09d3-d751-59f69adb3d8c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/limit-access.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: limit-access
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/limit-access.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
platformId: 5ca64f04-a19a-9a62-aef7-d5440cb549ab
---

# Restrict OneDrive access by security group - SharePoint in Microsoft 365 | Microsoft Learn

You can restrict access and sharing of OneDrive content to users in specified Microsoft Entra ID security groups. Even if other users outside of these security groups are licensed for OneDrive, they won't have access to their own OneDrive or any shared OneDrive content when this policy is in effect. OneDrive access restriction at tenant level is applied when a user attempts to open a OneDrive or a file.

You can use this to prevent new users from accessing any OneDrive content. For example, you can restrict OneDrive access and sharing to your new users, guest or frontline users.

Users who aren't members of the specified security group can still see files in organization-wide search and Copilot experiences if they have existing permissions to the file prior to the policy configuration. However they won't be able to open the file or OneDrive if they aren't part of the specified security group.

[![Screenshot of restricted access control for OneDrive.](sharepointonline/media/sam-overview/4-restricted-access-control-onedrive.png)](sharepointonline/media/sam-overview/4-restricted-access-control-onedrive.png#lightbox)

Note

If you want to prevent oversharing of OneDrive content also for users with existing permissions, we recommend you to enforce OneDrive site access restriction to an individual user's OneDrive. For more information, see [Restrict access to a user's OneDrive content to people in a security group](onedrive-site-access-restriction).

## What you need to restrict OneDrive access?

See [Prerequisites for SharePoint Advanced Management](sharepoint-advanced-management-prerequisites).

## Specify security groups for OneDrive access

To enable this feature:

1. Go to [Access control in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185071), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.
2. Select **Restrict OneDrive access**.
3. Select **Restrict OneDrive access to only users in specified security groups**.

    [![Restrict OneDrive access on the Access control page in the SharePoint admin center](sharepointonline/media/restrictonedriveaccess.png)](sharepointonline/media/restrictonedriveaccess.png#lightbox)
4. Add the security groups (maximum of 10) you want to be able to use OneDrive.
5. Select **Save**.

Important

Users who aren't members of the specified security groups lose access to their own OneDrive and any shared OneDrive content. Sharing of content is allowed only for the specified security group or members of the specified security group.

## Configure learn more link for access denial error page

Configure your learn more link to inform users who were denied access to a OneDrive site due to the OneDrive access restriction policy. With this customizable error link, you can provide more information and guidance to your users.

Note

The learn more link is a tenant-level setting that applies to all OneDrive sites.

To configure the link, run the following command in SharePoint PowerShell:

```powershell
Set-SPOTenant -RestrictedAccessControlForOneDriveErrorHelpLink "<Learn more URL>"
```

To fetch the value of the link, run the following command:

```powershell
Get-SPOTenant | select RestrictedAccessControlForOneDriveErrorHelpLink 
```

The configured learn more link is launched when the user selects the **Know more about your organization's policies here** link.

## Audit events

[Audit events](/en-us/microsoft-365/compliance/audit-log-activities) are available in Microsoft Purview portal to help you monitor restricted access control activities. Audit events are logged for the following activities:

- Enabled Restricted OneDrive access and sharing
- Disabled Restricted OneDrive access and sharing