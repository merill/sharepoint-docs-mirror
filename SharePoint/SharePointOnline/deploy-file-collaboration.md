---
layout: Conceptual
title: Plan and deploy a file collaboration environment - SharePoint - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/deploy-file-collaboration
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-01-22T00:00:00.0000000Z
ms.reviewer: 
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
f1.keywords: NOCSH
ms.topic: concept-article
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Strat_SP_admin
- M365-collaboration
- essentials-security
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
search.appverid: MET150
description: In this article, you learn about planning and deploying a secure and productive file collaboration environment in SharePoint in Microsoft 365.
locale: en-us
document_id: 0bd782a6-36d8-d7d6-f30b-f54dc960c069
document_version_independent_id: 9666c599-3457-c9ce-9b36-acf2157f0908
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/deploy-file-collaboration.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: deploy-file-collaboration
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/deploy-file-collaboration.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 041e1de3-02da-0f0b-7281-0121f08faa1a
---

# Plan and deploy a file collaboration environment - SharePoint - SharePoint in Microsoft 365 | Microsoft Learn

By using Microsoft 365 services, you can create a secure and productive file collaboration environment for your users. SharePoint powers much of this environment, but the capabilities of file collaboration in Microsoft 365 go beyond the traditional SharePoint site. Teams, OneDrive, and various governance and security options all play a role in creating a rich environment where users can collaborate easily and where your organization's sensitive content remains secure.

In the following sections, you find the options and decisions that you as an administrator should consider when setting up a collaboration environment:

- How SharePoint relates to other collaboration services in Microsoft 365, including OneDrive, Microsoft 365 Groups, and Teams.
- How you can create an intuitive and productive collaboration environment for your users.
- How you can protect your organization's data by managing access through permissions, data classifications, governance rules, and monitoring.

This article is part of the broader Microsoft 365 collaboration story:

- [Secure collaboration with Microsoft 365](/en-us/microsoft-365/solutions/setup-secure-collaboration-with-teams)
- [Collaboration governance](/en-us/microsoft-365/solutions/collaboration-governance-overview)
- [Meetings, webinars, and live events](/en-us/microsoftteams/quick-start-meetings-live-events)

Download the [Microsoft Teams and related productivity services in Microsoft 365 for IT architects](/en-us/microsoft-365/solutions/productivity-illustrations) poster and refer to it while you read this article. This poster provides detailed illustrations of how the collaboration services in Microsoft 365 relate to each other and interact.

## Creating a successful collaboration experience

Choose technical implementation options for file collaboration in Microsoft 365 that balance what can seem to be contradictory requirements:

- Protecting your intellectual property
- Enabling self-service
- Creating a smooth user experience

### Protecting your intellectual property

Several options discussed later in this article can help you protect your intellectual property. These options include limiting who can share files, applying governance policies by using sensitivity labels, and managing the devices that users use to access content.

Consider a balanced approach when choosing options:

A configuration that allows users to share content freely can lead to accidental sharing of confidential data. However, a user experience that's difficult to use or too restrictive can lead to users finding alternative collaboration options that circumvent your governance policies, ultimately leading to even greater risk.

By using a combination of features – depending on the sensitivity of your data – you can create a collaboration environment that's easy to use and provides the security and auditing controls that you need.

**Enabling self-service**

In Microsoft 365, allow users to create Teams, Microsoft 365 Groups, and SharePoint sites as needed. Use sensitivity labels to enforce permissions governance, take advantage of compliance features that protect your content, and use expiration and renewal policies to make sure unused sites don't accumulate.

By choosing options that favor user self-service, you can minimize the impact on your IT staff while creating an easier experience for your users.

**Creating a smooth user experience**

The key to creating a smooth user experience is to avoid creating barriers for your users that they don't understand or that they must escalate to your help desk. For example, turning external sharing off for a site might cause user confusion or frustration. Labeling the site and its contents as confidential and using data loss prevention policy tips and emails to educate your users in your governance policies can lead to a smoother experience for them.

## SharePoint, Microsoft 365 Groups, and Teams

In SharePoint in Microsoft 365, each SharePoint team site is part of a Microsoft 365 group. A Microsoft 365 group is a single permissions group that's associated with various Microsoft 365 services, including a SharePoint site, an instance of Planner, a mailbox, a shared calendar, and others. When you add owners or members to the Microsoft 365 group, they get access to the SharePoint site along with the other connected services.

While you can continue to manage SharePoint site permissions separately by using SharePoint groups, manage permissions for SharePoint by adding people to or removing them from the associated Microsoft 365 group. This approach provides easier administration and gives users access to a host of related services that they can use for better collaboration.

Microsoft Teams provides a hub for collaboration by bringing together all the Microsoft 365 group-related services, plus various Teams-specific services, in a single user experience with persistent chat. Teams uses the associated Microsoft 365 group to manage its permissions. Within the Teams experience, users can directly access SharePoint along with the other services without having to switch applications. This approach provides a centralized collaboration space with a single place to manage permissions. Teams uses the SharePoint site that is connected to the Microsoft 365 group for files in standard channels and creates separate SharePoint sites for each private or shared channel. For collaboration scenarios in your organization, use Teams rather than using services such as SharePoint independently.

For details about how SharePoint and Teams interact, see [Overview of Teams and SharePoint integration](/en-us/sharepoint/teams-connected-sites) and [Manage settings and permissions when SharePoint and Teams are integrated](/en-us/sharepoint/manage-teams-sharepoint-experiences).

## Collaboration in client applications

Office applications such as Word, Excel, and PowerPoint provide a wide variety of collaboration features, including coauthoring and @mentions. These applications also integrate with sensitivity labels and data loss prevention (discussed later).

Deploy Microsoft 365 Apps for enterprise. Microsoft 365 Apps for enterprise provides an always up-to-date experience for your users, with the latest features and updates delivered on a schedule that you can control.

For details about deploying Microsoft 365 Apps for enterprise, see [Deployment guide for Microsoft 365 Apps](/en-us/deployoffice/deployment-guide-microsoft-365-apps).

## OneDrive libraries

While SharePoint provides shared libraries for shared files that teams can collaborate on, users also have an individual library in OneDrive where they can store files that they own.

When a user adds a file to OneDrive, that file isn't shared with anyone else. OneDrive provides the same sharing capabilities as SharePoint, so users can share files in OneDrive as needed.

A user's individual library can be accessed from Teams, and from the OneDrive web interface and mobile application.

On devices running Windows or macOS, users can install the OneDrive sync app to sync files from both OneDrive and SharePoint to their local disk. This sync app allows them to work on files offline and also provides the convenience of opening files in their native application (such as Word or Excel) without the need of going to the web interface.

The two main decisions to consider for using OneDrive in collaboration scenarios are:

- Do you want to [allow Microsoft 365 users to share files in OneDrive with people outside your organization](turn-external-sharing-on-or-off)?
- Do you want to [restrict file sync](plan-file-sync) in any way – such as only to managed devices?

You can configure these settings in the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219).

## Securing your data

A significant part of a successful collaboration solution is making sure your organization's data remains secure. Microsoft 365 provides various features to help you keep your data secure while enabling a seamless collaboration experience for your users.

To help protect your organization's information, you can:

- **Control sharing** by configuring sharing settings for each site that are appropriate to the type of information in the site, you can create a collaboration space for users while securing your intellectual property.
- **Classify and protect information** by classifying the types of information in your organization, you can create governance policies that provide higher levels of security to information that is confidential compared to information that is meant to be shared freely.
- **Manage devices** with device management, you can control access to information based on device, location, and other parameters.
- **Monitor activity** by monitoring the collaboration activity happening in Teams and SharePoint, you can gain insights into how your organization's information is being used. You can also set alerts to flag suspicious activity.
- **Protect against threats** by using policies to detect malicious files in SharePoint, OneDrive, and Teams, you can help ensure the safety of your organization's data and network.

These options are discussed in more detail in the following sections. Depending on the needs of your organization, choose the options that give you the best balance of security and usability. If you're in a highly regulated industry or work with highly confidential data, you might want to put more of these controls in place. If your organization's information isn't sensitive, you might want to rely on basic sharing settings and malicious file alerts.

### Control sharing

The sharing settings that you configure for SharePoint and OneDrive determine who your users can collaborate with, both inside and outside your organization. Depending on your business needs and the sensitivity of your data, you can:

- Disallow sharing with people outside your organization.
- Require people outside your organization to authenticate.
- Restrict sharing to specified domains.

You can configure these settings for the entire organization, or for each site independently (except private or shared channel sites). For detailed information, see [Turn sharing on or off](turn-external-sharing-on-or-off) and [Turn sharing on or off for a site](change-external-sharing-site).

For more guidance about sharing with people outside your organization, see [Limit accidental exposure to files when sharing with guests](/en-us/microsoft-365/solutions/share-limit-accidental-exposure).

When users share files and folders, they create a shareable link that has permissions to the item. There are three primary link types:

- *Anyone* links that work for anyone and don't require sign-in
- *People in your organization* links that work for users in your organization
- *Specific people* links that work for the people specified when the link is created

For more information about these link types, see [How shareable links work in OneDrive and SharePoint in Microsoft 365](shareable-links-anyone-specific-people-organization).

#### Unauthenticated access with *Anyone* links

*Anyone* links are a great way to easily share files and folders with people outside your organization. However, if you're sharing sensitive information, this option might not be the best choice.

If you require people outside your organization to authenticate, users can't use *Anyone* links and you can audit guest activity on shared files and folders.

Though *Anyone* links don't require people outside your organization to authenticate, you can track the usage of *Anyone* links and revoke access if needed.

If you want to allow *Anyone* links, several options provide a more secure sharing experience.

You can restrict *Anyone* links to read-only. You can also set an expiration time limit, after which the link stops working.

Another option is to configure a different link type to be displayed to the user by default. This option can help minimize the chances of inappropriate sharing. For example, if you want to allow *Anyone* links but are concerned that they only be used for specific purposes, you can [set the default link type](change-default-sharing-link) to *Specific people* links or *People in your organization* links instead of *Anyone* links. Users must then explicitly select *Anyone* links when they share a file or folder.

You can also use data loss prevention to restrict *Anyone* link access to files that contain sensitive information.

#### *People in your organization* links

*People in your organization* links are a great way to share information within your organization. *People in your organization* links work for anyone in your organization, so users can share files and folders with people who aren't part of a team or members of a site. When redeemed, the link gives access to the particular file or folder and can be passed around inside the organization. This access allows for easy collaboration with stakeholders from groups that might have separate teams or sites – such as design, marketing, and support groups.

Creating a *People in your organization* link doesn't make the associated file or folder appear in search results, be accessible via Copilot, or grant access to everyone within the organization. Simply creating this link doesn't provide organizational-wide access to the content. For individuals to access the file or folder, they must possess the link and activate it through redemption. A user redeems the link by clicking on it, or in some instances, the link might be automatically redeemed when sent to someone via email, chat, or other communication methods. The link doesn't work for guests or other people outside your organization.

#### *Specific people* links

*Specific people* links are best for circumstances where users want to limit access to a file or folder. The link only works for the person specified and they must authenticate in order to use it. These links can be internal or external (if you enable guest sharing).

### Classify and protect information

Microsoft Purview Data Loss Prevention provides a way to classify your teams, groups, sites, and documents, and to create a series of conditions, actions, and exceptions to govern how they're used and shared.

By classifying your information and creating governance rules around them, you can create a collaboration environment where users can easily work with each other without accidentally or intentionally sharing sensitive information inappropriately.

With data loss prevention policies in place, you can be relatively liberal with your sharing settings for a given site and rely on data loss prevention to enforce your governance requirements. This approach provides a friendlier user experience and avoids unnecessary restrictions that users might try to work around.

For detailed information about data loss prevention, see [Learn about data loss prevention](/en-us/purview/dlp-learn-about-dlp).

#### Sensitivity labels

Sensitivity labels provide a way to classify teams, groups, sites, and documents with descriptive labels that you can use to enforce a governance workflow.

Using sensitivity labels helps your users share information safely and maintain your governance policies without needing to become experts in those policies.

For example, you could configure a policy that requires Microsoft 365 groups classified as confidential to be private rather than public. In such a case, a user creating a group, team, or SharePoint site would only see the **private** option when they choose a classification of confidential. For information about using sensitivity labels with teams, groups, and sites, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](/en-us/purview/sensitivity-labels-teams-groups-sites).

#### Conditions and actions

By using data loss protection conditions and actions, you can enforce a governance workflow when a given condition is met.

Examples include:

- If customer information is detected in a document, users can't share that document with guests.
- If a document contains the name of a confidential project, guests can't open the document even if it is shared with them.

For more information, see [Learn about data loss prevention](/en-us/purview/dlp-learn-about-dlp).

### Conditional access

Microsoft Entra Conditional Access provides extra controls to prevent users from accessing your organization's resources in risky situations, such as untrusted locations or devices that aren't up to date.

Examples include:

- Block guests from signing in from risky locations.
- Require multifactor authentication for mobile devices.

Create access policies specifically for guests to mitigate risk for people who most likely have unmanaged devices.

For detailed information, see [What is Conditional Access?](/en-us/azure/active-directory/conditional-access/overview).

## Monitoring with reports

Microsoft 365 offers a variety of reports to help you monitor site usage, document sharing, governance compliance, and a host of other events.

For information about how to view reports on SharePoint site usage, see [Microsoft 365 Reports in the Admin Center - SharePoint site usage](/en-us/microsoft-365/admin/activity-reports/sharepoint-site-usage-ww).

For information about how to view data loss prevention reports, see [View the reports for data loss prevention](/en-us/purview/dlp-learn-about-dlp#dlp-activity-explorer-and-reports).

For information on reports that can help you monitor content sharing, see [Data access governance reports for SharePoint sites](data-access-governance-reports).