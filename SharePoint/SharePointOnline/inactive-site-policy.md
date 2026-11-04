---
layout: Conceptual
title: Manage inactive sites using inactive site policies - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/inactive-site-policy
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-08-19T00:00:00.0000000Z
ms.reviewer: nvasudevan
manager: dansimp
ms.author: deniseb
author: denisebmsft
audience: Admin
customer-intent: As a SharePoint admin, I want to ensure all inactive sites are properly managed so that resources are optimized.
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.localizationpriority: medium
ms.collection:
- Highpri
- Tier2
- M365-sam
- M365-collaboration
- essentials-manage
search.appverid: 
description: Learn how to manage inactive SharePoint sites using inactive site policies at scale and automate compliance.
locale: en-us
document_id: 74e1c8e0-a61f-6b27-cf4f-226cacef6529
document_version_independent_id: 7bc82dc2-9098-8305-ec7f-0a7cd513b311
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/inactive-site-policy.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: inactive-site-policy
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/inactive-site-policy.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 800da133-d084-851c-2139-16605b36580b
---

# Manage inactive sites using inactive site policies - SharePoint in Microsoft 365 | Microsoft Learn

Inactive site policies help you identify SharePoint sites that aren't active for a specified period of time. Use these policies to notify site owners or site administrators, request confirmation that a site is still needed, and take enforcement actions when no response is received. You can configure an inactive sites policy in the SharePoint admin center.

For an overview of SharePoint site lifecycle management and the available policy types, see [Overview of SharePoint site lifecycle management policies](site-lifecycle-management).

[![Screenshot of site lifecycle management policies in the SharePoint admin center.](sharepointonline/media/site-lifecycle-management/site-lifecycle-management-policies.png)](sharepointonline/media/site-lifecycle-management/site-lifecycle-management-policies.png#lightbox)

This article describes how to set up an inactive site policy with notifications and enforcement actions.

## Prerequisites for an inactive site policy

See [SharePoint Advanced Management prerequisites](sharepoint-advanced-management-prerequisites).

## How inactive site policies determine site activity

Inactive site policies evaluate activity across SharePoint and connected Microsoft 365 workloads to determine when a site was last active.

### In-scope site activities

Inactive site policies analyze activity across SharePoint and connected platforms like Teams, Viva Engage (formerly Yammer), and Exchange to detect a site's last activity.

| Platform type | Activities |
| --- | --- |
| **SharePoint** | Viewed files, edited files, shared files internally and externally, synced files, viewed pages, visited pages |
| **Viva Engage (formerly Yammer)** | Posted messages, read conversations, liked messages |
| **Teams** | Posted channel messages in a team across standard channels, posted messages in Teams and standard channels, replied to messages, mentioned in messages, reacted to messages, sent urgent messages, conducted meetings (recurring, ad hoc, one-time) |
| **Exchange** | Received emails in the Exchange mailbox |

### Scope of app activities

Inactive site policies don't consider app activity through an app token. They consider app activity through a user token only when a user agent is involved and meets the following criteria.

| Activity source | Condition when activity is considered |
| --- | --- |
| PnP PowerShell activity via user token | Is not considered |
| SharePoint Online PowerShell activity via user token | Is considered only when UserAgent parameter value is passed |
| CSOM scripting activity via user token | Is considered when script explicitly sets UserAgent value |
| Any other app activity via user token | Is considered when UserAgent exists, except in the following scenarios when - UserAgent starts with "client-request=id"/"ACTIVEMONITORING"/"SPORUNNERS" **OR** - UserAgent ends with "MSDEMO"/"MSDPLATFORM"/"SystemUsage" **OR** - UserAgent contains "GomezAgent"/"bingbot.htm"/"ms search 6.0 robot"/"http://www.monitis.com"/"ISV" |
| App activity via app token | Is not considered |

### In-scope site templates

Site lifecycle management reviews the activity of communication sites, classic sites, Teams-connected sites, and group-connected sites with the following site template types:

| Site type | Template type |
| --- | --- |
| Communication site | SitePagePublishing#0 |
| Classic sites | STS#0, STS#1, STS#2, WIKI#0, BLOG#0, SGS#0, SPS#0, SPSNEWS#0, ENTERWIKI#0, COMMUNITY#0, DEV#0, EXPRESS#0, EHS#1, EHS#2 |
| Teams-connected site | STS#3 or Group#0 |
| Group-connected site | STS#3 or Group#0 |

### Out-of-scope sites

The following sites are out of scope and excluded from site activity detection:

- OneDrive sites
- Sites created by system users
- App catalog sites
- Root sites
- Home sites
- Tenant admin sites
- Sites associated with Shared and Private Teams channels

## Policy modes

Site ownership policies support two operating modes:

- **Simulation mode** – Runs the policy once and generates a report without ongoing enforcement.
- **Active mode** – Runs monthly, generates reports, sends notifications, and can apply enforcement actions based on policy configuration.

Note

Site lifecycle policies in simulation mode are now available in GCCH and DoD environments as of November 17, 2025.

For more information about policy modes across site lifecycle management policies, see [Overview of SharePoint site lifecycle management](site-lifecycle-management).

[![Screenshot of Site lifecycle management dashboard.](sharepointonline/media/site-lifecycle-management/1-inactive-site-policy-dashboard.png)](sharepointonline/media/site-lifecycle-management/1-inactive-site-policy-dashboard.png#lightbox)

## Create an inactive site policy

1. As a SharePoint administrator, go to the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219) and sign in.
2. In the navigation pane, expand **Policies**, and then select **Site lifecycle management**.
3. Under **Inactive site policies**, select **Open**.
4. Select **+ Create policy**. Review the **Manage inactive sites** information, and then select **Next**.

    [![Screenshot of Overview page.](sharepointonline/media/site-lifecycle-management/overview.png)](sharepointonline/media/site-lifecycle-management/overview.png#lightbox)
5. On the **Set policy scope** step, choose your policy scope option, and then select **Next**.

    [![Screenshot of Scope page when selecting the option of sites at scale.](sharepointonline/media/site-lifecycle-management/scope-scale.png)](sharepointonline/media/site-lifecycle-management/scope-scale.png#lightbox)

    - If you select **Upload a CSV file with a list of up to 10,000 URLs**, you can upload a list of site URLs of select sites for the policy.

        [![Screenshot showing the Upload a CSV file dialog box.](sharepointonline/media/site-lifecycle-management/upload-csv-site-list.png)](sharepointonline/media/site-lifecycle-management/upload-csv-site-list.png#lightbox)

        Tip

        - You can export the site list from the SharePoint active sites page.
        - Ensure the CSV file uses the same format of the sample CSV file, that it has no duplicate URLs, and that the URLs are valid and complete.
        - Ensure the URLs listed in CSV file belong to your tenant's domain.
    - If you chose **Include sites with retention policies and retention holds**, this option applies only to sites that are governed by [Microsoft Purview retention policies and labels](/en-us/purview/retention?tabs=table-overriden). This setting doesn't affect the inclusion or exclusion of sites that are in a read-only or locked state.
6. On the **Configure policy** step, specify an inactivity period, who to notify, and what actions you want to take after three notifications. Then select **Next**.

    [![Screenshot of Configuration page.](sharepointonline/media/site-lifecycle-management/configuration.png)](sharepointonline/media/site-lifecycle-management/configuration.png#lightbox)

    - Choose to send emails to site owners or site admins, or both.
    - If you plan to exclude users or groups, see the section Exclude users or groups from a policy(in this article).
    - Customize the email content to provide more context and instructions to the email recipients.
    - Choose enforcement actions if there's no response from site owners or admins after three notifications.

        With any of the [SharePoint site lifecycle management policies](site-lifecycle-management), for sites that aren't certified or attested after three monthly notifications, you can take one of the following enforcement actions described in the following table:

        | Enforcement action | Policy behavior |
        | --- | --- |
        | **Do nothing** | Site owners or site admins receive monthly notifications for three months. After this period, no notifications are sent for the next three months. If the site remains unattested after six months, monthly notifications resume. The policy execution report lists unattested sites as unactioned by the site owner. You can download this report and filter out sites marked as unactioned. |
        | **Read-only access** | Site owners or site admins receive monthly notifications for three months. If the notification recipients don't mark the site as attested during this period, the site goes into read-only mode. |
        | **Archive sites after mandatory read-only period** | Site owners or site admins receive monthly notifications for three months. If the notification recipients don't mark the site as attested during this period, then the site goes into a read-only mode for a configurable duration (3, 6, 9, or 12 months). After the configured number of months, the site gets archived through [Microsoft 365 Archive](/en-us/microsoft-365/archive/archive-setup). Archival is subject to the tenant enabling Microsoft 365 Archive in the Microsoft 365 admin center. |

        The following screenshot shows an example of configuring enforcement actions for a site attestation policy:

        ![Screenshot of enforcement actions configuration for site lifecycle management policies.](sharepointonline/media/site-lifecycle-management/enforcement-actions.png)

        Note

        If you configure the policy to take an enforcement action:

        - The notifications won't be sent after policy action is successful.
        - The site and it's status are included in the monthly report.
7. On the **Finish** step, specify a name and description for your policy, and select a policy mode. Then Select **Finish**.
8. After your policy is created, select **Done**.

Once your policy is deployed, you can view and manage it in the **Site lifecycle management** &gt; **Inactive site policy** dashboard.

[![Screenshot of Finish page.](sharepointonline/media/site-lifecycle-management/finish.png)](sharepointonline/media/site-lifecycle-management/finish.png#lightbox)

## Exclude users or groups from a policy

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

## Inactive site notifications to site owners or site admins

Notifications inform SharePoint site owners or site admins when a site is inactive for a specified number of months. To keep the site, the notification recipients should select the **Certify site** button in the notification email. Once certified, Site lifecycle management doesn't check the site's activity for one year.

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

## Enforcement actions

The following table summarizes how the inactive site policy behaves based on the selected enforcement action:

| Enforcement action | Policy behavior |
| --- | --- |
| **Do nothing** | The specified recipients receive monthly notifications for three months. After this period, the policy sends no notifications for the next three months. If the site remains inactive after six months, monthly notifications resume. The policy execution report lists inactive sites as unactioned by the site owner. You can download this report and filter out sites marked as unactioned. |
| **Read-only access** | Site owners or site admins receive monthly notifications for three months. If the notification recipients don't mark the site as certified during this period, the site goes into read-only mode. |
| **Archive sites after mandatory read-only period** | Site owners or site admins receive monthly notifications for three months. If the notification recipients don't mark the site as certified during this period, then the site goes into a read-only mode for a configurable duration (3, 6, 9, or 12 months). After the configured number of months, the site gets archived through [Microsoft 365 Archive](/en-us/microsoft-365/archive/archive-setup). Microsoft 365 Archive must be enabled in the Microsoft 365 admin center. |

Important

- Site lifecycle policies use Outlook Actionable Messages to enable site owners or site admins take necessary actions within email.
- For notifications to render properly, ensure **[Outlook version requirements](/en-us/outlook/actionable-messages/)** are met in your organization.
- If you're a US Government cloud customer, see Set up actionable emails for SLM policies in US Government cloud environments (in this article).
- To troubleshoot rendering issues, refer to **[frequently asked questionnaire](/en-us/outlook/actionable-messages/actionable-messages-faq)**.
- When a site owner or site admin selects the site URL in the notification email, this action does **not** count as site activity. The site remains inactive. Additionally, any **read actions** done on the site within one hour of visiting from the email aren't considered activity. However, any **edits** made to the site count as activity and reset the inactivity status.

Tip

Before creating an inactive site policy, check for any site access restriction policies that could disrupt site attestation by the respective site owner.

## Read-only mode

An inactive site policy configured with the read-only enforcement action sends notifications to inform site owners or site admins when there's no response.

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

The policy execution report lists sites that are inactive for six months. You can download the report as a .csv file and filter out sites that site owners consider unactioned.

[![Screenshot of inactive site policy downloaded csv report.](sharepointonline/media/site-lifecycle-management/8-inactive-site-policy-downloaded-csv-report.png)](sharepointonline/media/site-lifecycle-management/8-inactive-site-policy-downloaded-csv-report.png#lightbox)

The following table describes the information included in the policy execution report:

| Column | Definition |
| --- | --- |
| **Site name** | Name of the site |
| **URL** | URL of the site |
| **Template** | Template of the site |
| **Connected to Teams** | Is it a Teams-connected site or not |
| **Sensitivity label** | Sensitivity label of the site |
| **Retention policy** | Is any retention policy applied to the site or not |
| **Site lock state** | State of site access **before** the policy runs (Unlock/Read-Only/No access) |
| **Last activity date (UTC)** | Date of last activity detected by inactive site policy across SharePoint site and connected workloads (Exchange, Viva Engage (formerly Yammer), or Teams) |
| **Site creation date (UTC)** | Date when the site was created |
| **Storage used (GB)** | Storage consumed by the site |
| **Number of site owners** | Total count of site owners for the site |
| **Email address of site owners** | Email addresses of all site owners |
| **Number of site admins** | Total count of site admins for the site |
| **Email address of site admins** | Email addresses of all site admins |
| **Action status** | Status of the site (First, second, or third notification sent; Site in read-only mode; Site archived; Action taken by another policy: read-only, archive, or notified by another policy) |
| **Total notifications count** | Total notifications sent so far by any policy under the same policy template |
| **Action taken on (UTC)** | Date on which the enforcement action was taken (date when site was archived or put in read-only mode) |
| **Duration in read-only** | Number of days the site is in the enforced read-only state |

## Overlapping policies of same policy type

When more than one policy of the same policy type includes the same site, SharePoint helps reduce duplicate notifications by using stored site-level policy history.

If a notification was sent within the last 30 days from any policy of that type, and the site remains uncertified, no further notifications are sent and the policy execution report shows the site's status as "Notified by another policy."

For example, if a site is covered by two different inactive site policies and receives a notification email from the first policy, the second policy doesn't send additional notifications within the next 30 days if the site remains uncertified.

We recommend that policies of the same type don't have overlapping scopes. If sites fall under multiple policies of the same type, notification schedules and enforcement actions can become difficult to predict.

## Overlapping policies of different types

Policies of different types operate independently for notification purposes. Notification history is tracked separately for each policy type.

For example, if a site falls within the scope of both a Site Ownership policy and an Inactive site policy, site owners might receive notifications from both policies when the respective policy conditions are met.

Enforcement actions are evaluated independently by each policy. If a policy applies an enforcement action that changes the site's state, the site might no longer qualify for processing by other policies:

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