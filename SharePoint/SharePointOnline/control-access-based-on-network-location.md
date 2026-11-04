---
layout: Conceptual
title: Network location-based access to SharePoint and OneDrive - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/control-access-based-on-network-location
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2024-05-02T00:00:00.0000000Z
ms.reviewer: samust
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
customer-intent: As a SharePoint Administrator, I want to control access to SharePoint and OneDrive data based on network location so that I can secure my organization's data.
f1.keywords:
- CSH
- network location
- IP address
- access control
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Strat_SP_admin
- M365-collaboration
- M365-sam
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
search.appverid:
- SPO160
- BSA160
- GSP150
- MET150
ms.assetid: b5a5f1f1-1174-4c6b-91d0-9273a6b6971f
description: Learn how to control access to SharePoint and OneDrive data based on network location.
locale: en-us
document_id: 4128fad9-2907-9f45-592f-2336dbd25ee3
document_version_independent_id: 6e105343-1f95-c061-dc48-187c2fb6870d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/control-access-based-on-network-location.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: control-access-based-on-network-location
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/control-access-based-on-network-location.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
platformId: 5c374b32-8261-1f04-3113-885883dee489
---

# Network location-based access to SharePoint and OneDrive - SharePoint in Microsoft 365 | Microsoft Learn

As an IT admin, you can control access to SharePoint and OneDrive resources in Microsoft 365 based on defined network locations that you trust. This is also known as a location-based policy.

To do this, you define a trusted network boundary by specifying one or more authorized IP address ranges. Any user who attempts to access SharePoint and OneDrive from outside this network boundary (using a web browser, desktop app, or mobile app on any device) is blocked.

![Access restricted message in browser](sharepointonline/media/7efa9e14-cd9e-4369-8f24-c218c222025d.png)

## What should I consider before setting a location-based policy?

Here are some important considerations for setting a location-based policy:

- **External sharing**: If you share files and folders with guests who authenticate, they can't access the resources outside of the defined IP address range.
- **Access from first and third-party apps**: Normally, you can access a SharePoint document from apps like Exchange, Viva Engage, Skype, Teams, Planner, Power Automate, PowerBI, Power Apps, OneNote, and so on. When you enable a location-based policy, apps that don't support location-based policies are blocked. The only apps that currently support location-based policies are Teams, Viva Engage, and Exchange. This means that all other apps are blocked, even when these apps are hosted within the trusted network boundary. This is because SharePoint can't determine whether a user of these apps is within the trusted boundary.

    Note

    We recommend that when you enable a location-based policy for SharePoint, you configure the same policy and IP address ranges for Exchange and Viva Engage. SharePoint relies on these services to enforce that the users of these apps are within the trusted IP range. For protecting access to SharePoint via the Office.com portal, we recommend using the Microsoft Entra Conditional Access policy for "Office 365" and configuring the trusted IP range there.
- **Access from dynamic IP ranges**: Several services and providers host apps which have dynamic originating IP addresses. For example, a service that accesses SharePoint while running from one Azure data center might start running from a different data center due to a failover condition or other reason, thus dynamically changing its IP address. The location-based conditional access policy relies on fixed, trusted IP address ranges. If you can't determine the IP address range up front, location-based policy might not be an option for your environment.

## How do I set a location-based policy in the SharePoint admin center?

Note

It can take up to 15 minutes for these settings to take effect.

1. Go to [**Access control** in the new SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185071), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

Note

If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the Access control page.

1. Select **Network location**, and turn on **Allow access only from specific IP address ranges**.

    ![The Network location panel](sharepointonline/media/access-control-network-location.png)
2. Enter IP addresses and address ranges separated by commas.

    Important

    Make sure you include your own IP address so you don't lock yourself out. This setting not only restricts access to OneDrive and SharePoint sites, but also to the OneDrive and SharePoint admin centers, and to running PowerShell cmdlets. If you lock yourself out and can't connect from an IP address within a range you specified, you will need to contact Support for help. If you save overlapping IP addresses, your users will see a generic error message with a correlation ID that points to "The input IP allow list has overlaps."

Note

To set a location-based policy by using PowerShell, run Set-SPOTenant with the -IPAddressAllowList parameter. For more info, see [Set-SPOTenant](/en-us/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps&amp;preserve-view=true).