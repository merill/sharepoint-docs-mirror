---
layout: Conceptual
title: Initiate site access reviews for Data access governance reports - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/site-access-review
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-07-09T00:00:00.0000000Z
description: Learn about how to initiate site access reviews as a remedial action for data access governance for SharePoint sites.
audience: Admin
customer-intent: As a SharePoint administrator, I want to initiate site access reviews for data access governance reports.
f1.keywords: NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Strat_SP_admin
- Highpri
- Tier2
- M365-sam
- M365-collaboration
- trust-pod
ms.custom:
- admindeeplinkSPO
ms.reviewer: pullabhk
ms.author: deniseb
author: denisebmsft
manager: dansimp
search.appverid: 
locale: en-us
document_id: 1f267a9f-bb56-9c58-aede-dc75c9abb15e
document_version_independent_id: b1399e6b-fcb9-99d8-5b8b-d9da10352b18
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/site-access-review.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: site-access-review
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/site-access-review.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 0bd24344-6438-a72c-9147-974c0c1bce92
---

# Initiate site access reviews for Data access governance reports - SharePoint in Microsoft 365 | Microsoft Learn

Site access reviews in the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219) enable [IT administrators](/en-us/microsoft-365/admin/add-users/assign-admin-roles) to delegate the process of reviewing data access governance reports to site owners of overshared sites.

This review process is crucial because:

- Compliance reasons prevent IT administrators from accessing file-level or item-level details.
- Site owners are best positioned to review and address oversharing issues for their own sites.

Note

Site access review supports only SharePoint sites. It currently doesn't support OneDrive accounts.

## What do you need to initiate a site access review?

See [SharePoint Advanced Management prerequisites](sharepoint-advanced-management-prerequisites).

In addition, before initiating a site access review, make sure site owners are available to respond to review requests, take necessary actions, and complete the review.

Microsoft 365 operated by 21Vianet doesn't support site access reviews, even if you have the required licenses.

## How site access review works

- You can initiate site access reviews for up to 100 sites directly from the web view of data access governance reports.
- If you need to review a larger number of sites, use [PowerShell](/en-us/sharepoint/powershell-for-data-access-governance#initiate-site-access-review-using-powershell) to initiate reviews.
- When you initiate a review, the site owner receives an email tailored to the specific oversharing issue identified in the selected report. For example, if the review is for the "Content shared with 'Everyone except external users'" category, the email focuses only on sharing concerns related to that report.

## Supported reports

Site access reviews are available for the following reports:

- Sharing link reports (Anyone, PeopleInYourOrg, Specific People shared externally)
- "Content shared with 'Everyone except external users'" reports
- Oversharing baseline report using permissions

## How to initiate a site access review

1. Sign in to the SharePoint admin center with your admin credentials.
2. Expand the **Reports** section and select **Data access governance**.
3. Select **View reports** for any one of the supported reports.
4. Choose a report and select the sites you want to review.

    [![Screenshot that shows Initiate site access review for sites listed within DAG report](sharepointonline/media/data-access-governance/initiate-site-access-review.png)](sharepointonline/media/data-access-governance/initiate-site-access-review.png#lightbox)
5. Select **Initiate site access review**.
6. Select **Customize and preview email** to customize the email contents for site owners.

    ![Customize the email to be sent to site owners](sharepointonline/media/data-access-governance/customize-email-initiate-site-access-review.png)
7. Customize the message to site owners as described in the email customization section.
8. Select **Send** to initiate the review request.

You can also [initiate site access reviews by using PowerShell](powershell-for-data-access-governance#initiate-site-access-review-by-using-powershell).

Important

You can initiate up to 1,000 site access reviews from the **Site permissions across your organization** report each calendar month. The limit resets when the month changes.

## Track site access reviews

To track all initiated site access reviews, go to the **My review requests** tab on the Data access governance landing page.

[![Screenshot that shows track all reviews initiated from a central page](sharepointonline/media/data-access-governance/my-review-requests.png)](sharepointonline/media/data-access-governance/my-review-requests.png#lightbox)

Once a review is initiated, its status stays "pending" until the site owner completes it. After completion, the review status and comments update with the reviewer's name and the date and time of completion. If a review fails (for example, due to an invalid email for the site owner), it's marked as failed.

You can also [Track site access reviews by using PowerShell](powershell-for-data-access-governance#track-site-access-reviews-by-using-powershell).

## Site access review process for site owners

When you start a review, site owners get an email that includes:

- A relevant title.
- Your comments, if any.
- A request to review site permissions.
- A link to a detailed access review page, specific to the identified issue in the data access governance report.

Here are examples of the different emails a site owner might receive:

- Content shared with 'Everyone except external users' report for the past 28 days:

    [![Screenshot that shows email received by site owners for oversharing via EEEU](sharepointonline/media/data-access-governance/email-eeeu-files-folders-lists.png)](sharepointonline/media/data-access-governance/email-eeeu-files-folders-lists.png#lightbox)
- Sharing links report for the past 28 days:

    [![Screenshot that shows the detailed oversharing permissions reports email notification.](sharepointonline/media/site-access-review/3-email-sharing-links.png)](sharepointonline/media/site-access-review/3-email-sharing-links.png#lightbox)
- Oversharing baseline report using permissions:

    [![Screenshot that shows the sharing links within the last 28 days report email notification.](sharepointonline/media/site-access-review/2-email-permissions-report.png)](sharepointonline/media/site-access-review/2-email-permissions-report.png#lightbox)

### Review 'Everyone Except External Users' site access requests

Site owners can review and manage access in two main areas:

- **SharePoint groups:**

    - View which groups contain 'Everyone except external users.'
    - See when and by whom the group was added.
    - Remove 'Everyone except external users' from groups if necessary:
        1. Open the SharePoint group membership page.
        2. Select **Everyone except external users**, select **Actions**, and select **Remove users from group**.

            [![Screenshot that shows displays sharepoint group members](sharepointonline/media/data-access-governance/manage-sharepoint-group-membership.png)](sharepointonline/media/data-access-governance/manage-sharepoint-group-membership.png#lightbox)
- **Individual items (files/folders/lists):**

    - View items shared with 'Everyone except external users' in the last 28 days.
    - See sharing details (who shared and when).
    - Manage access and remove permissions as needed:
        1. Select **Manage access**.
        2. Under the 'Everyone except external users' group in the **Groups** tab, select the group and select **Remove access**. See [Stop sharing OneDrive or SharePoint files or folders, or change permissions](https://support.microsoft.com/office/stop-sharing-onedrive-or-sharepoint-files-or-folders-or-change-permissions-0a36470f-d7fe-40a0-bd74-0ac6c1e13323) for more information.

            [![Screenshot that shows view for site owner regarding items shared with eeeu.](sharepointonline/media/data-access-governance/site-owner-view-foreeeu-files.png)](sharepointonline/media/data-access-governance/site-owner-view-foreeeu-files.png#lightbox)

### Review 'Sharing link' reports

When the site owner opens the email, they're redirected to a detailed sharing links report. This report shows:

- Files for which links were generated, with the date and the user who created the link.
- The **Manage access** button that site owners use to remove or modify permissions.

The following screenshot shows the detailed sharing links report:

[![Screenshot that shows the detailed sharing links report.](sharepointonline/media/site-access-review/6-detailed-sharing-links.png)](sharepointonline/media/site-access-review/6-detailed-sharing-links.png#lightbox)

### Review 'Oversharing baseline using permissions' reports

When site owners select the email, they're redirected to the site access review page, where they can see the oversharing baseline using permissions report. This report helps site owners identify items with excessive permissions and take necessary actions.

[![Screenshot that shows the oversharing baseline using permission reports email notification.](sharepointonline/media/site-access-review/5-detailed-permissions-report.png)](sharepointonline/media/site-access-review/5-detailed-permissions-report.png#lightbox)

The SharePoint admin views the number of users with permissions to a site in the Data access governance report. Site owners can see this number, along with how permissions are distributed across different site items. Items with the highest number of permissioned users are shown first, so the site owner can address the most exposed items.

### Understanding the permissions report

#### Number of permissioned users

This column shows the total number of users who have permissions to a specific scope (Site, List, Folder, or File). It reflects the exposure of that item compared to others. However, this number isn't unique - if the same user has both direct and indirect permissions, they're counted multiple times.

**Example**:

Imagine a folder "F" with the following permissions:

- 40 users from Group "A"
- 10 users with direct permissions
- 20 users with permissions via sharing links

The total number of permissioned users for folder "F" is 80 (40 from Group "A" + 10 direct + 20 via sharing links). No deduplication is applied, so if the same user is in both Group "A" and has access via a sharing link, they're counted twice.

Additionally, the total number of permissioned users across all scopes might exceed the number of users shown in the email or Data Access Governance report. This situation happens because users can have permissions on multiple items. While a user might be counted once at the site level, they're counted separately for each item they have access to.

#### Number of groups

This column shows how many groups have permissions to a specific item or scope. Often, a large portion of exposure comes from permissions granted to groups, especially those with many members. You can reduce exposure by adjusting group memberships or removing unnecessary groups from permissions.

Select the **Group number** to see the membership count of each group. This information helps you identify which groups to target for reducing permissions.

[![Screenshot that shows a specific group and its member count.](sharepointonline/media/site-access-review/4-group-membership-details.png)](sharepointonline/media/site-access-review/4-group-membership-details.png#lightbox)

#### Links and EEEU/Everyone

This section displays:

- The number of links (for example, "Anyone" or "People in your organization") that are shared for the scope.
- Whether the item is exposed to Everyone or EEEU (Everyone Except External Users).

If the number of links is high or the EEEU/Everyone column says "Yes," this condition is an immediate indicator that the item has broad exposure, and the site owner should focus on reducing permissions for that item.

#### Manage Access

The **Manage Access** button provides a way for the site owner to take action by:

- Removing individual users
- Modifying group memberships
- Deleting links
- Adjusting permissions

For a SharePoint site, selecting this button redirects to the **SharePoint group management** page. For individual items, it opens the **Manage Access** interface, which provides more granular control over permissions.

### Complete site access reviews

After the site owner makes the necessary changes, such as modifying or removing permissions, they should:

1. Select **Complete review**.
2. Add any relevant comments.
3. Submit the review.

The process sends comments back to the IT administrator, and the review is marked as completed.

### Manage multiple site access reviews

Site owners can receive and handle multiple site access review requests simultaneously. To track all review requests:

[![Screenshot that shows Master page to track all site review for a site.](sharepointonline/media/data-access-governance/site-review-master-page.png)](sharepointonline/media/data-access-governance/site-review-master-page.png#lightbox)

1. Go to the **Site reviews**page via:
    - The link in the review email.
    - The gear icon on the site home page:
        1. Select **Site settings**.
        2. Select **Site reviews**.

            [![Screenshot that shows path to site review page from site home page under gear icon.](sharepointonline/media/data-access-governance/site-review-from-gear-icon.png)](sharepointonline/media/data-access-governance/site-review-from-gear-icon.png#lightbox)
        3. View all pending site access reviews.
        4. Complete reviews as necessary.

## Customize email to site owners

Now you can customize the email sent to site owners to increase the likelihood that site owners see the email as a genuine request from SharePoint admins and not as a suspicious email. The following values are new and available for customization:

- From address: The custom username you specify in the Microsoft 365 admin center [under organizational profile](/en-us/microsoft-365/admin/email/select-domain-to-use-for-email-from-microsoft-365-products) automatically provides this value.
- Title of the email
- Message to the site owner that usually describes the scenario
- Any additional comments related to the ask to review
- A link to any SharePoint page or document that lists details or further instructions

![customize message, comments and add links to SharePoint pages in emails to site owners](sharepointonline/media/data-access-governance/email-customization-dag.png)

Select **Save** to save your customizations for this report type. This action overrides any previous changes and automatically applies to subsequent site reviews from that report type. In other words, you can save a customized version for each report type, as shown in the Data Access Governance landing page. Select **Reset** to revert all customizations to product defined defaults.