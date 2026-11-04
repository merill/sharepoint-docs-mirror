---
layout: Conceptual
title: Request recurring site attestations for SharePoint sites - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/request-site-attestations
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-06-26T00:00:00.0000000Z
ms.reviewer: nibandyo, deeptitakyar
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
customer-intent: As a SharePoint administrator, I want to request recurring site attestations for SharePoint sites to ensure compliance with organizational policies.
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.custom:
- has-azure-ad-ps-ref
ms.collection:
- M365-collaboration
- M365-sam
- Highpri
- Tier2
- ContentEngagementFY24
search.appverid: 
description: Learn how to create a site attestation policy to request recurring site attestations for SharePoint sites to ensure compliance with organizational policies.
locale: en-us
document_id: d05d42aa-d414-9235-7628-f329c7131134
document_version_independent_id: 0db28eae-0763-1b4a-c214-26056283f9f0
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/request-site-attestations.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: request-site-attestations
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/request-site-attestations.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 05f7f1e8-a117-eba1-1dfe-98da23118135
---

# Request recurring site attestations for SharePoint sites - SharePoint in Microsoft 365 | Microsoft Learn

Site attestation policies help you periodically verify that SharePoint sites continue to meet your organization's governance requirements. These policies request reviews from site owners or site administrators, who confirm whether a site is still needed and whether its ownership, membership, permissions, and sharing settings remain appropriate.

You can configure site attestation policies to send recurring review requests and apply enforcement actions when required reviews aren't completed.

For an overview of site lifecycle management policies, see [SharePoint site lifecycle management](site-lifecycle-management).

[![Screenshot of site lifecycle management policies in the SharePoint admin center.](sharepointonline/media/site-lifecycle-management/site-lifecycle-management-policies.png)](sharepointonline/media/site-lifecycle-management/site-lifecycle-management-policies.png#lightbox)

This article describes how to create a site attestation policy with notifications and enforcement actions.

## Requirements for a site attestation policy

See [SharePoint Advanced Management prerequisites](sharepoint-advanced-management-prerequisites).

## How a site attestation policy works

When a site attestation policy runs, SharePoint identifies sites that are due for review based on the policy configuration.

The policy sends attestation requests to designated recipients, such as site owners or site administrators. Recipients review site information and confirm that the site remains necessary and appropriately configured.

If a review isn't completed after the configured notification cycle, the policy can apply an enforcement action, depending on the policy settings.

Each policy run generates a report that administrators can use to track attestation status and monitor policy compliance.

## Create a site attestation policy

1. As a [SharePoint administrator](sharepoint-admin-role), go to the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219) and sign in.
2. In the navigation pane, expand **Policies**, and then select **Site lifecycle management**.

    [![Screenshot showing the site lifecycle management page with site attestation.](sharepointonline/media/site-lifecycle-management/site-attestation-on-site-lifecycle-page.png)](sharepointonline/media/site-lifecycle-management/site-attestation-on-site-lifecycle-page.png#lightbox)
3. Under **Site attestation policies**, select **Open**. Then select **Create a policy**.
4. On the **Overview** page of **Manage site attestation**, review the information, and then select **Next**. Then proceed to the next section.
5. To define the scope of a site attestation policy, on the **Set policy scope** page, select one of the following options:

    - **Upload a CSV file with a list of up to 10,000 URLs**; or
    - **Select sites at scale**

    [![Screenshot showing scope options for site attestation policy in SharePoint admin center.](sharepointonline/media/site-lifecycle-management/scope-options.png)](sharepointonline/media/site-lifecycle-management/scope-options.png#lightbox)

    For more information, see the following sections in this article:

    - About the scope of site attestation policies
    - Uploading a CSV file with the list of sites
    - Selecting sites at scale
6. On the **Configure policy** step, specify the following options:

    - Choose how often you want the sites to be attested (3 months, 6 months, and 12 months).
    - Identify who is responsible for attesting the site (site owners, site admins, or both).
    - Exclude site owners or admins from receiving requests.
    - Specify what action the policy should take after three notifications.

    Keep the following points in mind:

    - Recently attested sites are skipped.
    - Newly created sites are skipped (because a grace period applies).
    - Only sites that are both old enough and due for reattestation are included.

    For more information about your policy options, see About site attestation policy configuration settings (in this article).
7. On the **Finish** step, specify whether to test your policy or activate it immediately.

    - Give your policy a name and description.
    - Under **Policy mode**, select either the **Simulation** or **Active** mode. For more information, see About policy modes (in this article).

## About the scope of site attestation policies

Note

A policy scopes a site for attestation only if **both** of the following conditions are true:

- The site's creation date is older than the attestation threshold
- The site's last attestation date is also older than the same threshold

The attestation threshold is calculated using the policy run date minus the attestation period (how often you want sites to be attested, configured by SharePoint administrators). If either condition isn't met, the site is excluded from attestation for that run.

You can create site lifecycle policies with different scopes based on your organization's requirements. Choose the sites to include in the policy based on:

- Site templates
- Creation sources
- Sensitivity labels
- Whether to include sites under retention policies and retention holds

To exclude specific sites, add the site URLs of up to 100 sites in the **Exclude sites** section while configuring the policy.

### Uploading a CSV file with the list of sites

If you select **Upload a CSV file with a list of up to 10,000 URLs**, you can upload a list of site URLs for the policy.

[![Screenshot showing the option to upload a CSV file with site URLs for site attestation policy in SharePoint admin center.](sharepointonline/media/site-lifecycle-management/upload-csv-site-list.png)](sharepointonline/media/site-lifecycle-management/upload-csv-site-list.png#lightbox)

Tip

- You can export the site list from the SharePoint active sites page.
- Ensure that the CSV file uses the same format as the sample CSV file and has no duplicate URLs. Also, make sure the URLs are valid and complete.
- Ensure the URLs listed in the CSV file belong to your tenant's domain.

### Selecting sites at scale

If you select **Select sites at scale**, you can choose site templates to include in this policy, and then filter them by:

- Sensitivity label
- Site creation source

You can also choose whether to:

- Include sites with retention policies and retention holds
- Exclude specific sites from this policy

[![Screenshot showing scale options for site attestation policy in SharePoint admin center.](sharepointonline/media/site-lifecycle-management/scope-scale.png)](sharepointonline/media/site-lifecycle-management/scope-scale.png#lightbox)

#### Selecting site template types

Select site template types from the following list:

- All sites
- Classic sites
- Communication sites
- Group connected sites without teams
- Team sites without Microsoft 365 group
- Teams-connected sites

#### Filtering sites by sensitivity labels

Set policy scope by filtering sites by their sensitivity labels.

Note

If your tenant doesn't use sensitivity labels, this option is unavailable.

#### Filtering sites by creation source

Filter sites for the policy scope by site creation source:

- SharePoint Home
- SharePoint admin center
- PowerShell
- PnP
- Teams

#### Include sites with retention policies and retention holds

The include or exclude option for sites with retention policies and holds applies only to sites that are governed by [Microsoft Purview retention policies and labels](/en-us/purview/retention?tabs=table-overriden).

This setting doesn't impact the inclusion or exclusion of sites that are in read-only or locked states.

For sites that are in a read-only or locked state, the following behaviors are expected:

- **Unlocked sites**: Always included in policy scope
- **Read-only sites locked by the same policy type**:

    - Included in scope
    - Report indicates the site was previously actioned by this policy
- **Read-only sites locked by a different policy type**:

    - Excluded from policy scope
    - Another policy already owns and governs this site
- **Read-only sites externally locked** (locked because of reasons other than site lifecycle management):

    - Included in scope
    - External locks don't prevent the policy from evaluating the site
- **No access (fully locked) sites**:

    - Included in scope, but the policy takes no enforcement action
    - The policy skips action because the site is already in a no access locked state

You can't change these default behaviors through policy configuration options.

## About site attestation policy configuration settings

### Excluding specific sites from the policy

Enter up to 100 sites that you want to exclude from the site attestation policy. Be sure to separate each URL by new lines.

[![Screenshot showing the option to exclude specific sites from a site attestation policy in SharePoint admin center.](sharepointonline/media/site-lifecycle-management/exclude-sites.png)](sharepointonline/media/site-lifecycle-management/exclude-sites.png#lightbox)

After setting the policy's scope, select **Next**, and then proceed to the next section.

### Excluding site owners or admins from receiving requests

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

### Actions to take on unattested sites after three notifications

For sites that are unattested after three monthly notifications, you can choose to either do nothing or take one of the following enforcement actions. The following table summarizes how the inactive site policy behaves for each selected enforcement action:

| Enforcement action | Policy behavior |
| --- | --- |
| **Do nothing** | Site owners or site admins receive monthly notifications for three months. After this period, no notifications are sent for the next three months. If the site remains unattested after six months, monthly notifications resume. The policy execution report lists unattested sites as unactioned by the site owner. You can download this report and filter out sites marked as unactioned. |
| **Read-only access** | Site owners or site admins receive monthly notifications for three months. If the notification recipients don't mark the site as attested during this period, the site goes into read-only mode. |
| **Archive sites after mandatory read-only period** | Site owners or site admins receive monthly notifications for three months. If the notification recipients don't mark the site as attested during this period, then the site goes into a read-only mode for a configurable duration (3, 6, 9, or 12 months). After the configured number of months, the site gets archived through [Microsoft 365 Archive](/en-us/microsoft-365/archive/archive-setup). Archival is subject to the tenant enabling Microsoft 365 Archive in the Microsoft 365 admin center. |

[![Screenshot showing enforcement actions available for unattested SharePoint sites in site attestation policy.](sharepointonline/media/site-lifecycle-management/enforcement-actions.png)](sharepointonline/media/site-lifecycle-management/enforcement-actions.png#lightbox)

Note

If you configure the policy to take an enforcement action:

- The notifications stop after the policy action succeeds.
- The site and its status are included in the monthly report.

### Customizing email notifications

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

After configuring the policy settings, select **Next** to finish your policy. Name the policy, add a description (optional), and select a policy mode.

Select **Finish**. You can now view and manage your policy from the **Site lifecycle management** &gt; **Site attestation policy** dashboard.

### Read-only mode

When you configure an unattested site policy with the read-only enforcement action, it sends extra notifications to inform site owners or site admins that the site goes into read-only mode.

[![Screenshot of Site lifecycle management read-only mode notification.](sharepointonline/media/site-lifecycle-management/9-inactive-site-policy-read-only-mode.png)](sharepointonline/media/site-lifecycle-management/9-inactive-site-policy-read-only-mode.png#lightbox)

When the site is in read-only mode, the following banner appears on the site:

[![Screenshot of Site lifecycle management read-only mode banner at the top of a SharePoint site.](sharepointonline/media/site-lifecycle-management/10-inactive-site-policy-read-only-mode-banner.png)](sharepointonline/media/site-lifecycle-management/10-inactive-site-policy-read-only-mode-banner.png#lightbox)

#### Removing sites from read-only mode

To remove a site from read-only mode in the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219), go to the **Active sites** page, select the site, and then select **Unlock** from the site page panel.

Site owners can't remove a site from read-only mode. They must contact the tenant admin to remove read-only mode.

[![Screenshot of Site lifecycle management site page in SharePoint admin center.](sharepointonline/media/site-lifecycle-management/11-inactive-site-policy-read-only-mode-site-page.png)](sharepointonline/media/site-lifecycle-management/11-inactive-site-policy-read-only-mode-site-page.png#lightbox)

### Unarchiving a site

To unarchive a site in [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219), expand **Sites** and select **Archived sites**. Select the site you want to unarchive and select **Reactivate**.

Note

Only tenant admins can reactivate an archived site.

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

## About policy modes

## Policy modes

Site ownership policies support two operating modes:

- **Simulation mode** – Runs the policy once and generates a report without ongoing enforcement.
- **Active mode** – Runs monthly, generates reports, sends notifications, and can apply enforcement actions based on policy configuration.

Note

Site lifecycle policies in simulation mode are now available in GCCH and DoD environments as of November 17, 2025.

For more information about policy modes across site lifecycle management policies, see [Overview of SharePoint site lifecycle management](site-lifecycle-management).

## Reporting

After each run of the configured policy, you can view a detailed report about the sites it identifies. In the **Site attestation policies** page, select the desired policy from the list.

The panel outlines the numbers of:

- Sites to attest
- Sites that didn't have anyone to notify
- Sites attested
- Sites set to read-only
- Archived sites You can also view the policy's scope, configuration, and general information on the report.

[![Screenshot showing the detailed attestation report for SharePoint site lifecycle management.](sharepointonline/media/site-lifecycle-management/attestation-report-detail.png)](sharepointonline/media/site-lifecycle-management/attestation-report-detail.png#lightbox)

You can also view the policy's scope, configuration, and general information on the panel. Select the **Download detailed report** option to download the report in CSV containing the following details for each of the sites identified due for attestation:

| Column | Definition |
| --- | --- |
| Site name | Name of the site |
| URL | URL of the site |
| Template | Template of the site |
| Connected to Teams | Indicates if it's a Teams-connected site |
| Sensitivity label | Sensitivity label assigned to the site |
| Retention policy | Indicates if any retention policy is applied to the site |
| Site lock state | State of site access **before** the policy runs (Unlock/Read-Only/No access) |
| Notified site admins | Email addresses of site admins receiving attestation notifications |
| Notified site owners | Email addresses of site owners receiving attestation notifications |
| Last attested by | Email address of the person who last attested the site |
| Last attestation date (UTC) | Date when the site was last attested |
| Number of site owners | Total count of site owners for the site |
| Email address of site owners | Email addresses of all site owners |
| Number of site admins | Total count of site admins for the site |
| Email address of site admins | Email addresses of all site admins |
| Total notifications count | Total notifications sent so far by any policy under the same policy template |
| Action status of policy | Status of the site (First, second, or third notification sent, Site in read-only mode, Site archived, Action taken by another policy such as read-only, archive, or notified by another policy) |
| Action taken on (UTC) | Date on which the enforcement action was taken (date when site was archived or put in read-only mode) |
| Last activity date (UTC) | Date of last activity detected across SharePoint site and connected workloads |
| Site creation date (UTC) | Date when the site was created |
| Storage used (GB) | Storage consumed by the site |
| Duration in read-only (days) | Number of days the site is in the enforced read-only state |

## Configure actionable emails for US Government Cloud (GCC High or DoD) environments

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