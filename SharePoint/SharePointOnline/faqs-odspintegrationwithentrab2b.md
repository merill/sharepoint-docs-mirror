---
layout: Conceptual
title: 'Frequently Asked Questions: Improvements to external sharing in OneDrive and SharePoint - SharePoint in Microsoft 365 | Microsoft Learn'
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/faqs-odspintegrationwithentrab2b
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
description: FAQs for SharePoint admins about SharePoint OTP retirement and Microsoft Entra B2B integration in OneDrive and SharePoint.
author: phsristi
ms.author: phsristi
ms.service: onedrive
ms.topic: article
ms.date: 2026-09-18T00:00:00.0000000Z
manager: mibarret
ai-usage: ai-assisted
locale: en-us
document_id: b3af721d-cb73-cad4-b0c1-6ee3279e7847
document_version_independent_id: 83e5df3e-9463-28cf-06ab-d8d0f1ecc154
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/faqs-odspintegrationwithentrab2b.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: faqs-odspintegrationwithentrab2b
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/faqs-odspintegrationwithentrab2b.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
platformId: b7177057-7f02-45e4-2821-c247b6726ac3
---

# Frequently Asked Questions: Improvements to external sharing in OneDrive and SharePoint - SharePoint in Microsoft 365 | Microsoft Learn

1. **Is OTP being retired as a supported authentication method for guests?**

    SharePoint Online (SPO) one-time passcode (OTP) authentication will be retired for commercial tenants during October 2026. Microsoft Entra B2B email one-time passcode (OTP) authentication isn't being retired.

    When enabled, Microsoft Entra B2B email OTP is a fallback for guests who can't sign in through another supported authentication method. For more information, see [Email one-time passcode authentication](/en-us/entra/external-id/one-time-passcode).
2. **Can I opt out of this change?**

    No. Commercial tenants can't opt out of SharePoint OTP retirement or disable Microsoft Entra B2B integration for new external sharing.
3. **Can I choose when SharePoint OTP is retired for my tenant?**

    No. Retirement rolls out to commercial tenants during October 2026. Tenants are selected automatically, and you can't choose a specific date.
4. **Do all previously shared links need to be reshared?**

    No. External users with a matching Microsoft Entra B2B guest account in your directory retain access to previously shared links. If a guest account is missing, you can create one in Microsoft Entra B2B, or share or reshare at least one file, folder, or site to create the guest account automatically. You don't need to reshare each item individually.
5. **How can I identify guests who don't have a guest account yet?**

    At site level, use the external sharing report to get a list of guests invited via SPO OTP who do not yet have a Microsoft Entra B2B guest account. Refer to the "User E-mail" column. [Learn more](/en-us/sharepoint/sharing-reports). For guests without a Microsoft Entra B2B guest account, you can proactively create the account in your directory to retain access to all previously shared files.
6. **Do I need to enable Microsoft Entra B2B integration for my commercial tenant?**

    No. Integration is already enabled for new external sharing in commercial tenants. The `EnableAzureADB2BIntegration` setting no longer controls sharing behavior for these tenants, and the integration can't be disabled.
7. **Are duplicate guest accounts created?**

    No. If a Microsoft Entra B2B guest account already exists for a collaborator outside your organization, a duplicate is not created.
8. **Do my guest users retain access to files shared before the integration?**

    External users with a matching Microsoft Entra B2B guest account in your directory retain access. Once SharePoint OTP retirement reaches your commercial tenant during October 2026, users without a matching guest account receive access denied on previously shared **Specific people** links. See FAQ #9 for how to restore access.
9. **How is a guest account created in my directory?**

    An administrator can create a Microsoft Entra B2B guest account using the email address associated with the original sharing link. Alternatively, a user with sharing permissions can share or reshare at least one file, folder, or site with the external user. This automatically creates the guest account in Microsoft Entra B2B.

    Once a matching guest account exists, the external user can access previously shared links without each item being reshared.
10. **Is there any impact on Anyone/Anonymous links?**

    No, SPO OTP retirement and use of Entra B2B for external sharing does not impact Anyone/Anonymous links.