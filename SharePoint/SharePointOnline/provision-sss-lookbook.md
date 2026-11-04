---
layout: Conceptual
title: Provision the SharePoint Success Site from SharePoint Look Book - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/provision-sss-lookbook
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-06-25T00:00:00.0000000Z
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: sites-pages
ms.localizationpriority: high
ms.collection:
- Strat_SP_modern
- M365-collaboration
search.appverid:
- SPO160
- MET150
description: Learn how to provision the SharePoint Success Site from the SharePoint Look Book.
locale: en-us
document_id: 351132f6-30a6-e1d5-fe95-76dc7b1f31d8
document_version_independent_id: e007b540-c240-c1d3-daf5-88417e6fd010
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/provision-sss-lookbook.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: provision-sss-lookbook
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/provision-sss-lookbook.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: ae4b7810-79c9-53ec-4654-59d877844801
---

# Provision the SharePoint Success Site from SharePoint Look Book - SharePoint in Microsoft 365 | Microsoft Learn

Important

Look book is currently unavailable. See [Applying PnP Templates to SharePoint Sites](/en-us/sharepoint/dev/solution-guidance/applying-pnp-templates).

You can provision the SharePoint Success Site after you confirm that you *and* your tenant meet the following [prerequisites](provision-sss#meet-the-requirements):

- You're using Global Administrator credentials.
- Your tenant has the App Catalog installed.
- You're an administrator of the App Catalog.
- Your tenant is provisioned with Microsoft 365 learning pathways version 4.0 or later.

Important

Microsoft recommends that you use roles with the fewest permissions. Using lower permissioned accounts helps improve security for your organization. Global Administrator is a highly privileged role that should be limited to emergency scenarios when you can't use an existing role.

## Start provisioning from the SharePoint Look Book

If your tenant is already provisioned with Microsoft 365 learning pathways version 4.0 *or later*, you can provision the SharePoint Success Site from the [SharePoint Look Book](https://adoption.microsoft.com/sharepoint-look-book).

If you aren't sure what version of Microsoft 365 learning pathways is installed on your tenant, review the [prerequisites](provision-sss#meet-the-requirements). Then provision the SharePoint Success Site.

1. Navigate to the [custom PnP site templates](/en-us/sharepoint/dev/solution-guidance/applying-pnp-templates#available-templates) and select the template you need.
2. To provision the template, see [Provisioning a template](/en-us/sharepoint/dev/solution-guidance/applying-pnp-templates#provisioning-a-template).
3. Then, go to your tenant's learning pathways site.
4. Select **Home** &gt; **Learning pathways administration**.

    ![Image of the Microsoft 365 learning pathways admin page. The &quot;Learning pathways administration&quot; menu item is highlighted.](sharepointonline/media/sss-sss-admin.png)
5. Select the **More actions** (...) button, and then select **Add to Content Pack**.
6. Select **SharePoint Success Site**.

    ![Image of the content pack in the Microsoft 365 learning pathways admin page. The &quot;SharePoint Success Site&quot; selection is highlighted.](sharepointonline/media/sss-content-pack.png)
7. Go back to the Microsoft 365 learning pathways administration page.
8. Select **Complete**, as the following image shows:

    ![Image of the Microsoft 365 learning pathways solution Complete button.](sharepointonline/media/sss-m365lp-confirm2.png)

    Important

    Make sure to select **Complete** to finish the provisioning process.
9. To confirm that the SharePoint Success Site is successfully provisioned, go to the site, and then select **Get Started** &gt; **Plan your site**. You should see the web part on the page, as the following image shows:

    ![Image of the SharePoint Success Site landing page, named Plan your site.](sharepointonline/media/sss-content-landing.png)

In the next section, you'll add site owners to the Microsoft 365 learning pathways administration page and the SharePoint Success Site. This setting grants privileges to [customize the site and content](customize-sss).

## Add site owners

Assign a few site owners to grant administrative privileges to customize the site and training content. To hide, show, or enable playlists, users need site-owner permissions or site-member permissions to the Microsoft 365 learning pathways site. To edit the look, navigation, and site content, users need site-owner permissions or site-member permissions to the SharePoint Success Site.

To add owners or members to both sites:

1. On the site, select **Settings** &gt; **Site permissions**.
2. Select **Advanced Permission Settings**.
3. Select **Site owners** or **Site members**.
4. Select **New** &gt; **Add users to this group**. Then add the people who should be site owners or site members.
5. In the sharing message, include a link to **Explore the site**. Then select **Share**.

## Site provisioning help

- For provisioning help, see [troubleshooting](/en-us/office365/customlearning/feedback).
- See Microsoft 365 learning pathways [FAQs](/en-us/office365/customlearning/faq).
- Share your [feedback](https://github.com/pnp/custom-learning-office-365/issues) with us.

## Frequently asked questions

**Can I provision from the Microsoft 365 learning pathways admin page?**

Answer: Yes. Follow the guidance in [Provision the SharePoint Success Site to your tenant from the learning pathways administrative page](provision-sss#provision-the-sharepoint-success-site-1).

**Who has permission to provision the SharePoint Success Site?**

Answer: The Global Administrator (formerly called the tenant admin).

**Who has permission to customize the site template?**

Answer: A user who has [SharePoint site owner](/en-us/sharepoint/site-permissions#site-owners) and [above](/en-us/sharepoint/site-permissions).

**Who can create custom playlists and hide or show content in Microsoft 365 learning pathways?**

Answer: A user who has [SharePoint site owner](/en-us/sharepoint/site-permissions#site-owners) and [above](/en-us/sharepoint/site-permissions) permissions for Microsoft 365 learning pathways.

**Who has permissions to use the SharePoint Success Site as a user?**

Answer: Users who have Microsoft 365 user permissions, SharePoint Site visitor permissions, or higher permissions.