---
layout: Conceptual
title: Create a SharePoint site ownership policy - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/site-ownership-policy
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-05-14T00:00:00.0000000Z
ms.reviewer: anupam.francis
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- M365-sam
ms.custom: 
search.appverid: MET150
ms.assetid: 0ecb2cf5-8882-42b3-a6e9-be6bda30899c
description: Learn how to create a SharePoint site ownership policy to manage site ownerships at scale and automate compliance.
locale: en-us
document_id: cb616d25-4228-a93a-3ad8-8c19b209dc54
document_version_independent_id: 629b400f-da41-cff6-6c26-ae5ead82d99d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/site-ownership-policy.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: site-ownership-policy
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/site-ownership-policy.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 772ef454-7521-74a9-0bfa-4893dd2dbb55
---

# Create a SharePoint site ownership policy - SharePoint in Microsoft 365 | Microsoft Learn

Site ownership policies help you identify sites that don't meet your organization's ownership requirements. Use these policies to define ownership criteria, notify responsible users when sites become noncompliant, and take enforcement actions when ownership issues aren't resolved.

For an overview of SharePoint site lifecycle management policies and how site ownership policies work alongside inactive site and site attestation policies, see [Overview of SharePoint site lifecycle management](site-lifecycle-management).

[![Screenshot of site lifecycle management policies in the SharePoint admin center.](sharepointonline/media/site-lifecycle-management/site-lifecycle-management-policies.png)](sharepointonline/media/site-lifecycle-management/site-lifecycle-management-policies.png#lightbox)

This article describes how site ownership policies evaluate ownership requirements, how to create and configure a policy, and how to monitor policy execution.

## Prerequisites

See [SharePoint Advanced Management prerequisites](sharepoint-advanced-management-prerequisites).

## Create a site ownership policy

To create a site ownership policy, follow these steps:

1. As a SharePoint administrator, go to the SharePoint admin center and sign in.
2. In the navigation pane, expand **Policies**, and then select **Site lifecycle management**.

    [![Screenshot of ownership policy being created in SharePoint admin center dashboard.](sharepointonline/media/site-ownership-policy/1-create-site-ownership-policy.png)](sharepointonline/media/site-ownership-policy/1-create-site-ownership-policy.png#lightbox)
3. Under **Site ownership policies**, select **Open**. Then, select **+ Create policy**.
4. On **Manage ownership of sites**, review the information, and then select **Next**.

    [![Screenshot of ownership policy created in SharePoint admin center dashboard.](sharepointonline/media/site-ownership-policy/2-create-site-ownership-policy.png)](sharepointonline/media/site-ownership-policy/2-create-site-ownership-policy.png#lightbox)
5. On **Set policy scope**, choose your policy scope parameters, and then select **Next**.

    [![Screenshot of site ownership policy with set policy scope in SharePoint admin center dashboard.](sharepointonline/media/site-ownership-policy/3-create-site-ownership-policy.png)](sharepointonline/media/site-ownership-policy/3-create-site-ownership-policy.png#lightbox)

    If you select **Upload a CSV file with a list of up to 10,000 URLs**, you can upload a list of site URLs of select sites for the policy.

    [![Screenshot showing the Upload a CSV file dialog box.](sharepointonline/media/site-lifecycle-management/upload-csv-site-list.png)](sharepointonline/media/site-lifecycle-management/upload-csv-site-list.png#lightbox)

    Tip

    - You can export the site list from the SharePoint active sites page.
    - Ensure the CSV file uses the same format of the sample CSV file, that it has no duplicate URLs, and that the URLs are valid and complete.
    - Ensure the URLs listed in CSV file belong to your tenant's domain.
6. On **Configure policy**, specify criteria for your policy, and then select **Next**.

    [![Screenshot of ownership policy configuration page in SharePoint admin center dashboard.](sharepointonline/media/site-ownership-policy/4-create-site-ownership-policy.png)](sharepointonline/media/site-ownership-policy/4-create-site-ownership-policy.png#lightbox)

    If you plan to exclude users or groups, see important information in the section, Excluding users or groups (in this article).
7. On **Finish**, specify a name and description for your policy, select a policy mode, and then select **Finish**.

    [![Screenshot of ownership policy with notifications options selected.](sharepointonline/media/site-ownership-policy/5-create-site-ownership-policy.png)](sharepointonline/media/site-ownership-policy/5-create-site-ownership-policy.png#lightbox)

    If you select **Active mode**, your policy runs monthly, generates a report, and notifies site owners or site administrator about potential issues, depending on policy configuration.
8. After your policy is created, select **Done**.

You can view and manage your policy by selecting **Site ownership policies** in the **Site lifecycle management** dashboard.

## Define ownership criteria

When you create a site ownership policy, define the ownership criteria that sites must meet. You can determine:

- Whether ownership is determined by site owners, site administrators, or both.
- The minimum number of owners or administrators required for a site.

For example, setting the minimum owner count to `2` identifies sites that have only a single owner and require remediation.

When the policy runs, it identifies sites that don't meet the configured ownership requirements and generates a report. Active policies can also notify selected recipients.

## Overlapping policies of same policy type

When more than one policy of the same policy type includes the same site, SharePoint helps reduce duplicate notifications by using stored site-level policy history.

If a notification was sent within the last 30 days from any policy of that type, and the site remains uncertified, no further notifications are sent and the policy execution report shows the site's status as "Notified by another policy."

For example, if a site is covered by two different inactive site policies and receives a notification email from the first policy, the second policy doesn't send additional notifications within the next 30 days if the site remains uncertified.

We recommend that policies of the same type don't have overlapping scopes. If sites fall under multiple policies of the same type, notification schedules and enforcement actions can become difficult to predict.

## Overlapping policies of different types

Policies of different types operate independently for notification purposes. Notification history is tracked separately for each policy type.

For example, if a site falls within the scope of both a Site Ownership policy and an Inactive site policy, site owners may receive notifications from both policies when the respective policy conditions are met.

Enforcement actions are evaluated independently by each policy. If a policy applies an enforcement action that changes the site's state, the site may no longer qualify for processing by other policies:

- If a policy places the site in a read-only (locked) state, the site is no longer included in the scope of other policies.
- If a policy archives the site, the site reaches a terminal state and is no longer considered for enforcement by other policies.

When multiple policy types target the same site, the enforcement action from the policy whose conditions are satisfied first is applied first.

## Disabling or deleting a policy

Disabling or deleting a policy stops future activities from that policy, including notifications and enforcement actions. It doesn't automatically reverse previously applied actions.

Notification history is maintained at the site level separately for each policy type. As a result, disabling or deleting one policy doesn't affect notification history associated with other policy types that continue to target the site.

For policies of the same type, stored notification history (including notification count and last notification date) is retained even after a policy is disabled or deleted. This history naturally resets after the site has been absent from the scope of that policy type for 90 days.

If notification history needs to be reset sooner, contact Microsoft Support to determine whether the stored notification state can be cleared.

Important

To ensure predictable behavior, avoid creating overlapping policies of the same type that target the same sites. While SharePoint suppresses duplicate notifications where possible, overlapping policies can make notification timing and enforcement outcomes harder to interpret.

## Policy modes

Site ownership policies support two operating modes:

- **Simulation mode** – Runs the policy once and generates a report without ongoing enforcement.
- **Active mode** – Runs monthly, generates reports, sends notifications, and can apply enforcement actions based on policy configuration.

Note

Site lifecycle policies in simulation mode are now available in GCCH and DoD environments as of November 17, 2025.

For more information about policy modes across site lifecycle management policies, see [Overview of SharePoint site lifecycle management](site-lifecycle-management).

## Policy scope

You can create different site ownership policies for different groups of sites across your organization. When configuring scope, select sites based on:

- Site templates
- Site creation sources
- Sensitivity labels
- Retention policies
- Retention holds

You can also exclude up to 100 specific site URLs.

Note

The following sites are excluded from site ownership policies:

- OneDrive sites
- Sites created by system users
- App catalog sites
- Root sites
- Home sites
- Tenant admin sites

## Resolve user ID mismatches before running a policy

Before you run a site ownership policy, resolve any user ID mismatches to help ensure accurate ownership evaluation. User ID mismatches can occur when you delete and later recreate a user account, which leaves site ownership references associated with an obsolete identifier.

See [Fix site user ID mismatch in SharePoint or OneDrive](/en-us/troubleshoot/sharepoint/sharing-and-permissions/fix-site-user-id-mismatch).

## Configure ownership notifications

During policy configuration, choose who should receive notifications when ownership requirements aren't met. The configured recipient categories are cumulative eligible recipient sets, not an ordered fallback chain. You can notify:

- **Current site owners:** If you set the minimum owner or admin count to two and the site has an existing site owner, the owner receives an email notification asking them to add another owner.
- **Current site admins:** If you set the minimum owner or admin count to two and the site has an existing site administrator, the administrator receives an email notification asking them to add another owner.
- **Managers of previous owners or admins:** If an owner or administrator of a site leaves the organization, their managers are informed that the site needs an owner for effective management. If managers are members of a site, they can accept ownership. If they're visitors or don't have access to the site, they can coordinate with SharePoint administrators to find the next best owner.

    - As a user's details are deleted from the system 30 days after leaving the organization, managers might get only one notification about the site.
    - If the policy runs after 30 days of a user's leaving the organization, manager information isn't available, and notifications can't be sent.
    - For a Teams site, the "manager of the previous site owner" notification works only for users added directly to the SharePoint site owner. If the user was added from a Microsoft 365 Group, the notification isn't sent. This limitation exists because of how user information is retained after an account is deleted. To improve the chances of successfully sending notifications, select at least three options.
- **Active site members:** Based on policy configuration, the policy sends emails to the most recent active members of a site to accept ownership.

    - To ensure relevance and recency, read or write activity performed by a site member on a site in the last 180 days is considered as an activity.
    - Any user with last activity beyond 180 days isn't considered for these notifications.
    - External and guest users aren't considered for these notifications to accept ownership.

    Note

    If a site has no one to notify as per the email recipients provided during policy configuration, the count is provided in the summary. You can triage the sites and determine the next course of action.

### Customize email notifications

Administrators can customize the email messages that [site lifecycle management policies](site-lifecycle-management) send when site issues require attention.

Customizing email content helps improve the read-through rate of the emails, which effectively improves response efficiency and contributes to better governance across the tenant.

You can customize emails in the configure step. When you select **Customize email to be sent**, the customization window opens as shown in the following screenshot:

![Screenshot showing the email customization window with fields for sender, subject, message, policy guideline URL, and policy guideline description text.](sharepointonline/media/site-lifecycle-management/customize-email.jpg)

The following table describes the sections you can customize:

| Customizable section | Description |
| --- | --- |
| **Sender** | You must configure a custom domain in the Microsoft 365 admin center before you can use the email customization feature. For more information, see [Choose which domain to use for your email](/en-us/microsoft-365/admin/email/select-domain-to-use-for-email-from-microsoft-365-products). |
| **Subject** (up to 100 characters) | Use `$UserDisplayName` to insert the user's name and `$SiteName` to insert the name of the site. |
| **Message** (up to 500 characters) | Use `$UserDisplayName` to insert the user's name, `$SiteName` to insert the name of the site, and `$SiteUrl` to insert the URL of the site. |
| **Policy guideline URL** | Only valid HTTP links are allowed. |
| **Policy guideline description text** | The default value is the placeholder text. |

To customize emails for existing policies, follow these steps:

1. Select an existing policy.
2. Select **Edit configuration**.
3. Find the email customization option.

Note

If you don't configure email customization for a policy, the system continues to send default emails from `noreply@sharepoint.com`.

### What to do if you can't customize email messages

You can't customize emails if the custom domain setting isn't configured or is turned off.

You must configure the **Send email notifications from your domain** setting in the Microsoft 365 admin center before you can customize emails. If you don't configure this setting, you see a warning message at the top of the policy list, as shown in the following image:

[![Screenshot showing a warning message that appears when the custom domain setting is turned off, indicating that email customization isn't available.](sharepointonline/media/site-lifecycle-management/custom-email-turned-off-warning.png)](sharepointonline/media/site-lifecycle-management/custom-email-turned-off-warning.png#lightbox)

You might also see the warning message during the configuration step, as shown in the following screenshot:

[![Screenshot showing warning message during configuration.](sharepointonline/media/site-lifecycle-management/custom-email-turned-off-warning-during-config.png)](sharepointonline/media/site-lifecycle-management/custom-email-turned-off-warning-during-config.png#lightbox)

If you previously customized emails in one or more policies, but later turn off the **Send email notifications from your domain** setting in the Microsoft 365 admin center, you see the message bar in the policy list, and a warning message in the email customization window, as shown in the following screenshot:

[![Screenshot showing a warning message when the custom domain setting is turned off after email messages were previously customizes.](sharepointonline/media/site-lifecycle-management/custom-email-turned-off-warning-window.png)](sharepointonline/media/site-lifecycle-management/custom-email-turned-off-warning-window.png#lightbox)

Note

Only someone who has the Global Administrator role can configure domain settings in the Microsoft 365 admin center.

## Review ownership notifications

The active policy sends ownership policy notifications when it detects sites that don't meet ownership requirements. Recipients can take actions directly from the email to help resolve ownership issues.

Important

Site lifecycle management policies use Outlook Actionable Messages to enable recipients to take actions directly from email.

- Ensure required Outlook versions are deployed.
- US Government cloud customers must complete additional actionable message configuration.
- For troubleshooting guidance, see the Outlook Actionable Messages documentation.

## Excluding users or groups

You can exclude specific users, Microsoft 365 Groups, or security groups from receiving [site lifecycle management](site-lifecycle-management) requests and notifications, even if they're site owners or site admins for sites that are included in a policy.

**Key behaviors**:

- Exclusions are used only to determine notification recipients.
- Excluding a user or group doesn't change site permissions or ownership, and doesn't exclude the site from lifecycle policy evaluation
- Sites continue to be evaluated by the policy as usual.

**Limits**:

- You can add up to 100 entries to the exclusion list.
- Each entry can be an individual user, a Microsoft 365 Group, or a security group
- The 100-entry limit applies to the number of entries, not the number of users within a group. For example, a group with more than 100 members counts as one entry.

**Group exclusion behavior (important)**:

- When a group is added to the exclusion list for a policy, that group is excluded from notifications only when the group is directly added to the site or is a nested group within other groups that are directly added to the site.
- A member of an excluded group might still receive a notification if they're directly added to the site or are part of some other group that is directly added to the site.

## Enforcement actions

Note

Hard enforcement actions, such as locking a site or setting it to read-only, apply only to ownerless (zero owner) sites, where there's no accountable party and the governance risk is highest. Applying such enforcements to sites with an active owner can be disruptive and could unintentionally impact business workflows. As a result, this policy is designed to nudge rather than disrupt. Single owner sites receive notifications and reports that encourage restoration of the minimum owner count, without blocking access. If the site owner takes no action in such cases (nonownerless, but still in violation sites), after the third notification, there's a three-month cool-off period after which notifications resume.

The following table summarizes how the site ownership policy behaves, based on the selected enforcement action:

| Enforcement action | Policy behavior |
| --- | --- |
| **Do nothing** | The specified recipients receive monthly notifications for three months. After this period, the policy sends no notifications for the next three months. If the site remains in violation of ownership criteria after six months, monthly notifications resume. The policy execution report lists sites in violation as unactioned. You can download this report and filter out sites marked as unactioned. |
| **Read-only access** | The specified recipients receive monthly notifications for three months.- If the notification recipients don't address site ownership during this period and the site continues to be ownerless, it goes into read-only mode. - If the notification recipients don't address site ownership during this period but the site has at least one owner, after the third notification, there's a three-month cool-off period, after which notifications resume. |
| **Archive sites after mandatory read-only period** | The specified recipients receive monthly notifications for three months. - If the notification recipients don't address site ownership during this period, and the site continues to be ownerless, the site goes into a read-only mode for the configured number of months. After the configured number of months, the site gets archived through [Microsoft 365 Archive](/en-us/microsoft-365/archive/archive-setup). Archival must be enabled for the tenant in the Microsoft 365 admin center.- If the notification recipients don't address site ownership during this period but the site has at least one owner, after the third notification, there's a three-month cool-off period, after which notifications resume. |

## Read-only mode

A site ownership policy that you configure with the read-only enforcement action sends extra notifications to inform the specified recipients when there's no response.

When a site goes into read-only mode, a notification is sent.

[![Screenshot of Site lifecycle management read-only mode notification.](sharepointonline/media/site-lifecycle-management/9-inactive-site-policy-read-only-mode.png)](sharepointonline/media/site-lifecycle-management/9-inactive-site-policy-read-only-mode.png#lightbox)

If a site is in read-only mode, the following banner is added to the site:

[![Screenshot of Site lifecycle management read-only mode banner at the top of a SharePoint site.](sharepointonline/media/site-lifecycle-management/10-inactive-site-policy-read-only-mode-banner.png)](sharepointonline/media/site-lifecycle-management/10-inactive-site-policy-read-only-mode-banner.png#lightbox)

### Important points about read-only or locked sites

For sites that are in a read-only or locked state, the following behaviors are expected.

- **Unlocked sites**: Always included in policy scope
- **Read-only sites locked by the same policy type**:

    - Included in scope
    - Report indicates the site was previously actioned by this policy
- **Read-only sites locked by a different policy type**:

    - Excluded from policy scope
    - Another policy already owns and governs this site
- **Read-only sites externally locked** (locked because of reasons other than [site lifecycle management](/en-us/sharepoint/site-lifecycle-management)):

    - Included in scope
    - External locks do not prevent the site from being evaluated by the policy
- **No-access (fully locked) sites**:

    - Included in scope, but no enforcement action is taken
    - The policy skips action because the site is already in a no access locked state

These are default behaviors that can't be modified through policy configurations.

### Remove a site from read-only mode

To remove a site from read-only mode in [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219), go to the **Active sites** page, select the site, and then select **Unlock** from the site page panel.

Site owners can't remove a site from read-only mode and must contact the tenant admin to remove read-only mode.

[![Screenshot of Site lifecycle management site page in SharePoint admin center.](sharepointonline/media/site-lifecycle-management/11-inactive-site-policy-read-only-mode-site-page.png)](sharepointonline/media/site-lifecycle-management/11-inactive-site-policy-read-only-mode-site-page.png#lightbox)

### Unarchive a site

To unarchive a site in [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219), expand **Sites** and select **Archived sites**. Select the site you want to unarchive and select **Reactivate**.

Note

Only tenant admins can reactivate an archived site.

## Reporting

Each policy run generates a report that shows sites that don't meet the configured ownership requirements. The report summarizes:

- Ownership compliance status
- Notification history
- Enforcement actions
- Ownership configuration details
- Site metadata

[![Screenshot of ownership policy report.](sharepointonline/media/site-ownership-policy/6-create-site-ownership-policy-reporting.png)](sharepointonline/media/site-ownership-policy/6-create-site-ownership-policy-reporting.png#lightbox)

Select **Download report** to download the detailed report in a .csv format. The following table describes the information included in the policy execution report:

| Column | Description |
| --- | --- |
| **Site name** | Name of the site |
| **URL** | URL of the site |
| **Template** | Template of the site |
| **Sensitivity label** | Sensitivity label of the site |
| **Retention policy** | Indicates if any retention policy is applied to the site |
| **Site lock state** | State of site access **before** the policy runs (Unlock/Read-Only/No access) |
| **Minimum owners or admins configured** | Minimum owner or admin count you configured while creating the policy |
| **Number of site owners** | Total count of site owners for the site |
| **Email address of site owners** | Email addresses of all site owners |
| **Number of site admins** | Total count of site administrators for the site |
| **Email address of site admins** | Email addresses of all site administrators |
| **Managers of previous owners or admins** | Email addresses of the managers of previous owners or admins (if this option was configured during policy set-up) |
| **Active members** | Email addresses of the active site members (if this option was configured during policy set-up) |
| **Total notifications count** | Total notifications sent so far by any policy under the same policy template |
| **Action status** | Status of the site [First/second/third notification sent, Site in read-only mode, Site archived, Action taken by another policy] |
| **Action taken on (UTC)** | Date on which the enforcement action was taken (date when site was archived or put in read-only mode) |
| **Last activity date (UTC)** | Date of last activity detected across SharePoint site and connected workloads |
| **Site creation date (UTC)** | Date when the site was created |
| **Storage used (GB)** | Storage consumed by the site |
| **Duration in read-only (days)** | Number of days the site is in the enforced read-only state |

## Set up actionable emails for SLM policies in US Government cloud environments

In US Government Cloud (GCC High and DoD) environments, a tenant administrator must complete an extra, one-time setup for SharePoint [site lifecycle management](site-lifecycle-management) (SLM) policies to use [actionable messages](/en-us/outlook/actionable-messages/). This step helps ensure that policy notification emails display and function correctly. For example, site admins and site owners can take actions directly from email.

Unlike other commercial cloud environments, GCC High and DoD tenants require explicit administrator approval of the actionable message provider before it can send interactive email messages. Without this approval, SLM policy emails are delivered, but action buttons don't function as expected.

Important

You must be a Global Administrator or Exchange Administrator in the tenant to set up actionable messages.

### Approve the SLM actionable message provider

1. Go to the [Outlook Actionable Messages – Connectors admin portal for GCCH or DoD](https://outlook.office365.us/connectors/oam/Admin) and sign in.
2. In the **Provider Status** filter, select **Approved by Microsoft – Pending Your Approval**.
3. Locate the provider named `InactiveSiteOAMProviderGCCH`.
4. Select the provider, and then select **Approve**.

After you approve the provider, the SLM policy notifications send actionable messages.

Note

This approval applies only to SLM policy notifications. Other applications or services that use actionable messages might require separate approval.

### Ensure actionable messages are enabled for the tenant

[Site lifecycle management policies](site-lifecycle-management) use Outlook actionable messages to enable site owners or site administrators to take necessary actions by using links within email messages.

- For notifications to render properly, make sure your organization meets the [Outlook version requirements](/en-us/outlook/actionable-messages/).
- To troubleshoot rendering problems, see [frequently asked questions](/en-us/outlook/actionable-messages/actionable-messages-faq).

### Troubleshooting actionable messages

If actionable messages don't work as expected, try these steps:

- Make sure that the `InactiveSiteOAMProviderGCCH` provider is in an approved state.
- Allow sufficient time. It can take up to 24 hours for changes to propagate.