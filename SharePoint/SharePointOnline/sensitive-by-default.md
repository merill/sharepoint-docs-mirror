---
layout: Conceptual
title: Prevent guest access to files while DLP rules are applied - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/sensitive-by-default
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-02-24T00:00:00.0000000Z
ms.reviewer: samust
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.collection:
- M365-collaboration
- essentials-compliance
- M365-sam
ms.localizationpriority: medium
search.appverid:
- SPO160
- BSA160
- GSP150
- MET150
description: Learn how to block external sharing of newly added SharePoint and OneDrive files while they're scanned for DLP rules.
locale: en-us
document_id: 6a19bcff-df5b-bc9f-269d-482d44d70b61
document_version_independent_id: 31a35f88-d3ca-f765-7678-339ad81771f9
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/sensitive-by-default.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: sensitive-by-default
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/sensitive-by-default.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 0b8c1800-fbec-3fce-8448-99b791593bee
---

# Prevent guest access to files while DLP rules are applied - SharePoint in Microsoft 365 | Microsoft Learn

Note

Any user whose usertype is member are considered internal and users with member type Guest are only considered external.

When new files are added to SharePoint or OneDrive in Microsoft 365, it takes a while for [Microsoft Purview Data Loss Prevention (DLP) policy](/en-us/microsoft-365/compliance/dlp-learn-about-dlp) to scan the content and apply rules to help protect sensitive content. If external sharing is turned on, sensitive content could be shared and accessed by guests before the DLP rule finishes processing.

Instead of turning off external sharing entirely, you can mark the files in your organization as sensitive by default. This blocks guest access to new content until it's scanned for sensitive content and DLP policies that include content-based conditions are applied. Guests are notified that the file is being scanned if they attempt to access it during this time.

Once a file is crawled and no content that would block sharing per DLP rules is detected, guests can access the file. If the policy identifies sensitive content in the document that matches DLP rules, the normal behavior defined by those DLP rules is applied.

This feature doesn't block access to a file if:

- the content has already been crawled and no sensitive content was found that matches the conditions in any DLP rules,
- or if the file has properties that match exemptions in DLP rules that allow it to be shared.

This feature applies to newly added files in SharePoint and OneDrive. It doesn't block sharing if an existing file is changed.

## DLP rules are required for content to be shared with guests

When this feature is enabled, any content that isn't explicitly checked in a DLP policy is blocked from being externally accessed. In other words, for content to be shareable externally, it must be in a location that's covered by a DLP policy and the policies for that location must determine, after content has been crawled and identified, that the file doesn't match any rules that would prevent it from being shared. This helps prevent users from leaking sensitive files by placing them in a location not covered by DLP policies.

If you want to operate under the principle that only locations explicitly checked by DLP can be shared externally, no further action is necessary.

If you want to enable external sharing in locations not currently covered by DLP policies, you can create a DLP rule that includes all SharePoint and OneDrive locations that contain at least one rule with the "content contains" condition (for any content), and that doesn't perform any action (such as limiting or blocking the content), trigger any alerts, or generates any notifications or reports. This policy must be moved to the top of the list and not have the *stop processing more rules* option set, so it's only effective for content that doesn't match any other DLP rule. As a result of such a rule, any file in any location that doesn't match other DLP rules will be allowed for external sharing.

For information about how to create a DLP rule, see [Learn how to create and turn on a DLP policy](/en-us/microsoft-365/compliance/create-test-tune-dlp-policy).

## Mark files as sensitive by default

This feature is configured using PowerShell.

1. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    Note

    If you installed a previous version of the SharePoint Online Management Shell, go to **Add or remove programs** and uninstall "SharePoint Online Management Shell."
2. Connect to SharePoint as a [SharePoint Administrator](/en-us/sharepoint/sharepoint-admin-role) or [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
3. Run the following command:

    ```PowerShell
    Set-SPOTenant -MarkNewFilesSensitiveByDefault BlockExternalSharing 
    ```

    To disable this feature, run the following command:

    ```PowerShell
    Set-SPOTenant -MarkNewFilesSensitiveByDefault AllowExternalSharing
    ```

Note

It might take up to 60 minutes for this new setting to take effect.