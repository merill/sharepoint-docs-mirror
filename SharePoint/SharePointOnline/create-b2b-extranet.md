---
layout: Conceptual
title: Use SharePoint as a business-to-business (B2B) extranet solution - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/create-b2b-extranet
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: 
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 2026-05-07T00:00:00.0000000Z
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: overview
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- M365-collaboration
search.appverid:
- SPO160
- MOE150
- BSA160
- GSP150
- MET150
ms.assetid: 7b087413-165a-4e94-8871-4393e0b9c037
description: Learn how to use SharePoint and OneDrive in Microsoft 365 as a Business to Business (B2B) extranet solution
locale: en-us
document_id: 3d05bf3d-a92d-86ae-f5a9-8d9fe2918297
document_version_independent_id: ff487db5-cc00-c0f7-3d0a-e7874ec773a4
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/create-b2b-extranet.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: create-b2b-extranet
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/create-b2b-extranet.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: eabd393f-1d0c-4190-4732-587f8916844e
---

# Use SharePoint as a business-to-business (B2B) extranet solution - SharePoint in Microsoft 365 | Microsoft Learn

An extranet site in Microsoft SharePoint is a site that you create to let external partners access specific content and collaborate with them. Extranet sites are a way for partners to securely do business with your organization. You keep the content for your partner in one place, and they have only the content and access they need. They don't need to email the documents back and forth or use tools that aren't sanctioned by your IT department.

Traditionally, deploying a SharePoint *on-premises* extranet site involves complex configuration to establish security measures and governance, including granting access inside the corporate firewall, and expensive initial and ongoing costs.

But with Microsoft 365, partners connect directly to a members-only site in SharePoint, a team in Microsoft Teams, or a Teams shared channel without access to your on-premises environment or any other teams or sites. You can access Microsoft 365 extranet sites anywhere there's an Internet connection.

Depending on your collaboration needs, you can include Microsoft 365 groups or Microsoft Teams as part of your extranet.

## Why use Microsoft 365 for a B2B extranet?

**Time-to-value and cost savings:** A Microsoft 365 B2B extranet eliminates the need for creating a costly on-premises extranet site. No other hardware is required. Using Microsoft 365 greatly reduces the resource and labor costs. Your IT department can focus on more important tasks than creating and maintaining extranet infrastructure.

**Secure sharing:** Microsoft 365 B2B extranet provides a highly secure sharing experience with the IT governance and policies that you require, including:

- The ability to protect yourself against accidental sharing by using owner-approved sharing through Microsoft 365 Groups or Teams, which prevents users from inviting new users without approval.
- The ability to restrict partner users to a single site or team. They can't search for or view any content on sites or teams to which they aren't invited.

**Seamless collaboration:** Collaborate with your partner users as if they're part of your organization, including allowing them to chat and confer through Teams.

**Auditing and reporting**. Microsoft 365 B2B extranet offers visibility into the access of your content by external partner users. One of the key IT benefits is to be able to audit usage, including being able to see who is inviting whom and when a guest logs in to access the content. See [Search the audit log in the Microsoft Purview portal](/en-us/purview/audit-search) for more information.

**Security and governance**. Microsoft 365 features such as [Microsoft Purview Data Loss Prevention](/en-us/microsoft-365/compliance/dlp-learn-about-dlp) and [Microsoft Defender for Cloud Apps](/en-us/cloud-app-security/what-is-cloud-app-security) provide a robust feature set to help you create a secure guest sharing environment.

## Compare Microsoft 365 extranet with a traditional SharePoint on-premises extranet

| **Condition** | **Microsoft 365 extranet** | **SharePoint "on-premises" extranet** |
| --- | --- | --- |
| Firewall access required for guests | No | Yes |
| Complex network and infrastructure configuration required | No | Yes |
| Security hardening | Managed through Microsoft 365 configurations | Manually configured by IT staff |
| IT labor intensive | No | Yes |
| Ongoing maintenance needed | Minimal | Considerable |
| Other hardware needed | No | Often |
| Controlling sharing experience for the extranet | Part of Microsoft 365 sites functionality | Often requires custom solutions/apps |

## Get started

To get started setting up a SharePoint extranet site, see the following articles:

- [Collaborate with guests in a site](/en-us/Office365/Enterprise/collaborate-in-a-site) if you want to limit your extranet to a site with a Microsoft 365 Group, or [Collaborate with guests in a team](/en-us/Office365/Enterprise/collaborate-as-a-team) if you want to include a team.
- [Create a B2B extranet with managed guests](/en-us/Office365/Enterprise/b2b-extranet) if you want to delegate guest access management to specific approvers in either your organization or the partner organization.
- [Collaborate with external participants in a channel](/en-us/microsoft-365/solutions/collaborate-teams-direct-connect) if you want to use a shared channel in Teams where partners can use their existing work or school account for a single sign-on experience.
- [Limit accidental exposure to files when sharing with guests](/en-us/Office365/Enterprise/sharing-limit-accidental-exposure) and [Create a secure guest sharing environment](/en-us/Office365/Enterprise/create-a-secure-guest-sharing-environment) to learn about options for securing your guest sharing environment.