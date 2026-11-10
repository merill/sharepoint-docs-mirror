---
layout: Conceptual
title: Review application access with App Intelligence - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/app-intelligence
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
description: Learn how SharePoint administrators can prioritize and investigate non-Microsoft app access with App Intelligence.
author: kadambg
ms.author: kadgoswami
ms.reviewer: stephkent
manager: jmcdowe
ms.service: sharepoint-online
ms.topic: how-to
ms.date: 2026-11-06T00:00:00.0000000Z
locale: en-us
document_id: 244b699e-c1fe-1410-ee65-3e7e9202aee4
document_version_independent_id: 7091d017-2c53-8329-2ffb-dcf5adcf07a5
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/app-intelligence.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: app-intelligence
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/app-intelligence.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 15ccacfd-9166-37e5-9b6a-b01c37bebf92
---

# Review application access with App Intelligence - SharePoint in Microsoft 365 | Microsoft Learn

App Intelligence helps SharePoint administrators review how non-Microsoft applications access SharePoint content. It brings together available application permissions, behavior evidence, and resource reach to help you prioritize applications for review and understand what action to take next.

App Intelligence provides information to support your review. It doesn't determine whether an application is malicious or change the application's permissions.

## Availability and prerequisites

App Intelligence availability, required administrator role, and licensing depend on the current release and your tenant. Confirm that the feature is available to your organization and that your account has the required permissions before you use it.

App Intelligence depends on available assessment data. Activity might not be available immediately, and results are limited to the assessment window and data sources shown in the experience.

## Review applications with App Intelligence

1. In the SharePoint admin center, open **App Intelligence**.
2. In the Copilot pane, select **Review priority apps** to identify applications that might need immediate review.
3. Review the results. An assessment can include the application, likely behavior, sites reached, resource impact, reasons for review, and the assessment window, depending on the available data.

[![Screenshot of the App Intelligence preview showing a Copilot response with priority applications, site reach, likely behavior, and resource impact.](sharepointonline/learn-article-assets/priority-apps-v2.png)](sharepointonline/learn-article-assets/priority-apps-v2.png#lightbox)

### Assess privileged access

To focus on applications with broad permissions, select **Assess privileged access**. Review each application's permission scope and evidence.

Permissions describe what an application is allowed to access. They don't prove that it used all of that access.

Privileged-access results are based on available SharePoint and OneDrive access signals, such as:

- Permission breadth (for example, broad or tenant-wide scopes)
- Access model (for example, app-only access)
- Effective reach (for example, sites reached and sensitive sites reached)
- Available activity evidence in the assessment window

[![Screenshot of the App Intelligence preview showing applications with broad permissions, access models, sites reached, and evidence modes.](sharepointonline/learn-article-assets/privileged-access-v2.png)](sharepointonline/learn-article-assets/privileged-access-v2.png#lightbox)

### Understand why an application needs review

To investigate a result, ask why the application needs review or why it has a high resource impact. Check whether each explanation is based on permissions, observed activity, or both. Review the assessment window and data availability before acting.

App Intelligence can use different evidence modes:

- **Capability only:** Permissions indicate what an application can do. They don't prove that it performed those actions.
- **Observed behavior:** Available activity data indicates what the application did during the stated assessment window. It might not represent all activity.
- **Mixed:** The explanation uses both permission and activity evidence.

[![Screenshot of the App Intelligence preview explaining the difference between application capability and observed behavior.](sharepointonline/learn-article-assets/evidence-types-v2.png)](sharepointonline/learn-article-assets/evidence-types-v2.png#lightbox)

### How App Intelligence prioritizes applications for review

The **Review priority apps** result is a review queue, not a malware verdict. Prioritization uses available evidence, including:

- Permission breadth and access model
- Effective resource reach (for example, total sites and sensitive sites reached)
- Observed activity patterns in the assessment window
- Available context and evidence quality (including missing or stale data)
- Current review state from the assessment run

Each prioritized app includes reasons to explain why it was surfaced for review.

### How resource impact is determined

Resource impact—such as **High**, **Medium**, **Low**, or **Needs Data**—helps you prioritize review. It's based on available permission capability, observed activity, effective reach, sensitivity context, and evidence completeness in the assessment window.

Resource impact isn't a universal security score. **Low** doesn't mean an application is approved or risk-free, and **Needs Data** doesn't mean there was no activity.

Likely behavior is an interpretation of available evidence, not a verified statement of an application's business purpose. Missing or conflicting information can require further review.

### Export an assessment

To review exported results, select **View assessment report** and then **Download CSV**. The report can include applications requiring review, likely behavior, permission scope and evidence mode, resource impact, sites reached, assessment reasons, missing data, and the assessment window.

[![Screenshot of the App Intelligence preview showing an assessment report and a Download CSV action.](sharepointonline/learn-article-assets/export-assessment-v2.png)](sharepointonline/learn-article-assets/export-assessment-v2.png#lightbox)

## Actions

After you review the assessment results, you can take follow-up actions.

### Notify app owners

Use **Notify app owners** when you need business confirmation before making a governance decision.

1. Select one or more applications that require owner validation.
2. Select **Notify app owners**.
3. Review the resolved recipients and message.
4. Select **Send**.

App Intelligence uses owner information available in Microsoft Entra. If owner contact details aren't available, App Intelligence doesn't guess recipients.

Sending a notification requests validation only. It doesn't automatically change, restrict, or revoke application access.

### App restrictions

Use **App restrictions** when you decide an app should have reduced access to SharePoint content.

1. Select one or more applications.
2. Select **App restrictions**.
3. Review the app list, policy scope, and expected impact.
4. Confirm the restriction action by using the supported restriction workflow in SharePoint.

App restrictions are an explicit administrator action. App Intelligence doesn't apply restrictions automatically as part of assessment or notification.

## Data and coverage

App Intelligence relies on available SharePoint application-access information. The existing App Insights reports use audit data for `FileAccessed`, `FileDownloaded`, `FileModified`, and `FileUploaded` events. They don't include every audit event. Data collection and reporting delays can affect what is available.

The assessment window shown in the experience defines the period covered by a result. An absence of activity in that window doesn't establish that an application never accessed content.

For more information about the existing report workflow, see [Generate App Insights reports](app-insights).

## App Intelligence FAQ

### How is App Intelligence different from App Insights?

App Insights provides reports based on audit data about non-Microsoft applications accessing SharePoint content. App Intelligence adds an assessment that helps administrators prioritize applications and interpret available permissions, activity, and reach.

### Does a high resource impact mean that an application is unsafe?

No. It indicates that the available evidence might warrant closer review. Consider the permissions, observed activity, sites reached, and assessment window before deciding what to do.

### Why can an app be prioritized when activity appears limited?

Priority can be driven by permission capability and effective reach, not only observed activity. If activity evidence is limited or unavailable, App Intelligence can still surface the app for review and indicate capability-only or incomplete evidence.

### Does privileged access mean the app is malicious?

No. Privileged access indicates broad authorized capability or elevated access patterns. It doesn't prove harmful behavior. Use the explanation, evidence mode, and assessment window to interpret the result.

### Is resource impact a numeric risk score?

No. Resource impact is an explainable assessment level (**High**, **Medium**, **Low**, or **Needs Data**) based on available evidence. It's designed to support prioritization and review decisions.

### Is App Intelligence enforcement?

No. App Intelligence is advisory. It helps administrators understand available evidence and prioritize review actions; policy and access decisions still require administrator judgment.

### Does App Intelligence change application permissions?

No. App Intelligence helps you review available evidence. It doesn't change application grants or replace Microsoft Entra application-permission management.

### What if activity or other information is missing?

The assessment can be limited by unavailable or stale data. Treat **Needs Data** as a reason to investigate further, not as proof that there was no activity or that the application is unsafe.