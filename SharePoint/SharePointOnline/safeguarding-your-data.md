---
layout: Conceptual
title: Cloud data security measures in SharePoint & OneDrive - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/safeguarding-your-data
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.reviewer: mswann
manager: dansimp
ms.author: deniseb
author: denisebmsft
ms.date: 2025-01-13T00:00:00.0000000Z
audience: Admin
f1.keywords:
- NOCSH
ms.topic: article
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Strat_SP_admin
- M365-collaboration
- essentials-security
- M365-sam
ms.custom:
- seo-marvel-mar2020
search.appverid:
- SPO160
- ODB160
- MET150
ms.assetid: 5aa038e8-8ff0-4704-9e6a-fd72af0a2035
description: Learn what Microsoft does to protect your data in SharePoint and OneDrive, and steps you can take to increase security
locale: en-us
document_id: a9f3baf1-62a6-348a-8f7d-25ba27d7b292
document_version_independent_id: 520aaaa6-1d41-9712-0dd6-67a8ff586f3b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/safeguarding-your-data.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: safeguarding-your-data
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/safeguarding-your-data.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
platformId: 1d0f0991-f67b-ebe7-c962-49f413eadfbb
---

# Cloud data security measures in SharePoint & OneDrive - SharePoint in Microsoft 365 | Microsoft Learn

You control your data. When you put your data in SharePoint and OneDrive for Microsoft 365, you remain the owner of the data. For more info about the ownership of your data, see [Microsoft 365 Privacy by Design](https://www.microsoft.com/trustcenter/privacy/privacy-overview).

## How we treat your data

Microsoft engineers administer SharePoint and OneDrive using a PowerShell console that requires two-factor authentication. We perform day-to-day tasks by running workflows so we can rapidly respond to new situations. Check-ins to the service require code review and management approval.

No engineer has standing access to the service. When engineers need access, they must request it. Eligibility is checked, and if engineer access is approved, it's only for a limited time. In rare cases where Microsoft engineers need access to content (for example, if you submit a support ticket because a user can't access an important file that we believe is damaged), the engineers must check in a specific workflow that requires business justification and manager approval. An audit event is generated that you can view in the Microsoft 365 admin center. You can also turn on a feature called Customer Lockbox, so you need to approve the request. The engineer gets access only to the file in question. To learn how to turn on or off Customer Lockbox and approve and deny requests, see [Microsoft Purview Customer Lockbox Requests](/en-us/office365/admin/manage/customer-lockbox-requests).

## How you can safeguard your data

One of the most important things you can do to safeguard your data is to require two-factor authentication for your identities in Microsoft 365. This prevents credentials from being used without a second factor and mitigates the impact of compromised passwords. The second factor can be made through a phone call, text message, or app. When you roll out two-factor authentication, start with your Global Administrators, and then other admins and site collection admins. For info about how to do this, see [Set up multi-factor authentication for Microsoft 365 users](/en-us/office365/admin/security-and-compliance/set-up-multi-factor-authentication).

Other things we recommend to increase security:

- Use Microsoft Entra device-based conditional access to block or limit access on unmanaged devices like airport or hotel kiosks. See [Control access from unmanaged devices](control-access-from-unmanaged-devices).
- Create policies to sign users out of Microsoft 365 web sessions after a period of inactivity. For information, see [Sign out inactive users](sign-out-inactive-users).
- Evaluate the need for IP-based sessions. These simulate the access model of an on-premises deployment. Read more at [Control access based on network location or app](/en-us/onedrive/control-access-based-on-network-location-or-app).
- Empower workers to share broadly but safely. You can require sign-in or use links that expire or grant limited privileges. See [Manage external sharing for your SharePoint environment](external-sharing-overview).
- Prevent accidental exposure of sensitive content. Create DLP policies to identify documents and prevent them from being shared. See [Learn about data loss prevention](/en-us/microsoft-365/compliance/dlp-learn-about-dlp).

## Protected in transit and at rest

### Protected in transit

When data transits into the service from clients, and between datacenters, it's protected using best-in-class encryption. For info, see [Data Encryption in OneDrive and SharePoint](/en-us/office365/securitycompliance/data-encryption-in-odb-and-spo). We only permit secure access. We won't make authenticated connections over HTTP but, instead, redirect to HTTPS.

### Protected at rest

**Physical protection**: Only a limited number of essential personnel can gain access to datacenters. Their identities are verified with multiple factors of authentication, including smart cards and biometrics. There are on-premises security officers, motion sensors, and video surveillance. Intrusion detection alerts monitor anomalous activity.

**Network protection**: The networks and identities are isolated from the Microsoft corporate network. We administer the service with dedicated Active Directory domains, we have separate domains for test and production, and the production domain is divided into multiple isolated domains for reliability and security. For more information about the built-in physical and logical security from Microsoft 365, see [Built-in security from Microsoft 365](https://www.microsoft.com/security).

**Application security**: Engineers who build features follow the security development lifecycle. Automated and manual analyses help identify possible vulnerabilities. The Microsoft security response center ([Microsoft Security Response Center](https://www.microsoft.com/msrc?rtc=1)) helps triage incoming vulnerability reports and evaluate mitigations. Through the Microsoft Cloud Bug Bounty, people across the world can earn money by reporting vulnerabilities. Read more about this at [Microsoft Cloud Bug Bounty Terms](https://www.microsoft.com/msrc/bounty-microsoft-cloud?rtc=1).

**Content protection**: Your data is encrypted at the disk level using BitLocker encryption and at the file level using keys. For info, see [Data Encryption in OneDrive and SharePoint](/en-us/office365/securitycompliance/data-encryption-in-odb-and-spo). For information about using Customer Key to provide and control the keys that are used to encrypt your data at rest in Microsoft 365, see [Service encryption with Microsoft Purview Customer Key FAQ](/en-us/office365/securitycompliance/service-encryption-with-customer-key-faq).

The Microsoft 365 anti-malware engine scans documents at upload time for content matching an AV signature (updated hourly). For info, see [Virus detection in SharePoint](/en-us/office365/securitycompliance/virus-detection-in-spo). For more advanced protection, use Microsoft 365 Advanced Threat Protection (ATP). ATP analyzes content that's shared and applies threat intelligence and analysis to identify sophisticated threats. For info, see [Microsoft 365 Advanced Threat Protection](/en-us/office365/securitycompliance/office-365-atp).

To limit the risk of content being downloaded to untrusted devices:

- Limit sync to devices on the domains you specify: [Allow syncing only on computers joined to specific domains](/en-us/onedrive/allow-syncing-only-on-specific-domains).
- Use Intune to limit access to content in the OneDrive and SharePoint mobile apps: [Control access to features in the OneDrive and SharePoint mobile apps](/en-us/onedrive/control-access-to-mobile-app-features).

To manage content at rest:

- Configure IRM policies on SharePoint document libraries to limit download of content. See [Set up Information Rights Management (IRM) in SharePoint admin center](/en-us/office365/securitycompliance/set-up-irm-in-sp-admin-center).
- Evaluate the use of Azure Information Protection (AIP). Classification and labeling let you track and control how data is used. Visit [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).

## Highly available, always recoverable

Our datacenters are geo-distributed within the region and fault tolerant. Data is mirrored in at least two datacenters to mitigate the impact of a natural disaster or service-impacting outage. For more information, see [Where your Microsoft 365 customer data is stored](/en-us/microsoft-365/enterprise/o365-data-locations).

Metadata backups are kept for 14 days and can be restored to any point in time within a five-minute window.

In the case of a ransomware attack, you can use Version history ([Enable and configure versioning for a list or library](https://support.office.com/article/1555d642-23ee-446a-990a-bcab618c7a37)) to roll back, and the recycle bin or site collection recycle bin to restore ([Restore deleted items from the site collection recycle bin](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b)). If an item is removed from the site collection recycle bin, you can call support within 14 days to access a backup. For information about the new Files Restore feature that lets users restore an entire OneDrive to any point within the past 30 days, see [Restore your OneDrive](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15).

## Continuously validated

We continuously monitor our datacenters to keep them healthy and secure. This starts with inventory. An inventory agent scans each subnet looking for neighbors. For each machine, we perform a state capture.

After we have an inventory, we can monitor and remediate the health of machines. The security patch train applies patches, updates anti-virus signatures, and makes sure we have a known good configuration saved. We have role-specific logic that ensures we only patch or rotate out a certain percentage of machines at a time.

We have an automated workflow to identify machines that don't meet policies and queue them for replacement.

The Microsoft 365 "Red Team" within Microsoft is made up of intrusion specialists. They look for any opportunity to gain unauthorized access. The "Blue Team" is made up of defense engineers who focus on prevention, detection, and recovery. They build intrusion detection and response technologies. To keep up with the learnings of the security teams at Microsoft, see [Security, Compliance, and Identity Blog](https://techcommunity.microsoft.com/category/security-compliance-and-identity/blog/microsoftsecurityandcompliance).

To monitor and observe activity in your Microsoft 365 subscription:

- If you have an on-premises security operations center or SIEM, you can monitor activity with the Management Activity API. For information, see [Microsoft 365 Management APIs overview](/en-us/office/office-365-management-api/office-365-management-apis-overview). This will show you activity from across SharePoint, Exchange, Microsoft Entra ID, DLP, and more. If you don't have an on-premises security operations center or SIEM, you can use Cloud App Security. Cloud App Security uses the Management Activity API. For info, see [Overview of Microsoft 365 Cloud App Security](/en-us/office365/securitycompliance/office-365-cas-overview). Through Cloud App Security, you can report, search, and alert on activity.
- Use Microsoft Entra ID Protection. This applies machine learning to detect suspicious account behavior, for example, simultaneous sign-ins from the same user in different parts of the world. You can configure identity protection to take action to block these sign-ins. For more info, see [Microsoft Entra ID Protection](/en-us/azure/active-directory/identity-protection/overview).
- Use Secure Score to evaluate the security profile of your subscription against a known good baseline, and identify opportunities to increase protection. For more info, see [Microsoft Secure Score](/en-us/microsoft-365/security/mtp/microsoft-secure-score-new?preserve-view=true&amp;view=o365-worldwide).

## Audited and compliant

Regulatory compliance is fundamental to Microsoft 365. We make sure the service complies with regulatory and compliance standards. We also help you meet your audit and compliance obligations. The [Service Trust Portal](https://servicetrust.microsoft.com) is a one-stop-shop for compliance and trust information for Microsoft enterprise services. The portal contains reports, whitepapers, vulnerability assessments, and compliance guides. For more info about the Service Trust Portal, see [Get started with the Microsoft Service Trust Portal](/en-us/office365/securitycompliance/get-started-with-service-trust-portal).

To meet your regulatory requirements:

- Audit Microsoft 365 activity in the Security & Compliance Center: [Search the audit log in the Microsoft 365 Security & Compliance Center](/en-us/office365/securitycompliance/search-the-audit-log-in-security-and-compliance).
- Create eDiscovery cases: [Manage eDiscovery cases in the Microsoft 365 Security & Compliance Center](/en-us/office365/SecurityCompliance/ediscovery-cases).
- Apply retention policies: [Create and apply information management policies](https://support.office.com/article/eb501fe9-2ef6-4150-945a-65a6451ee9e9).