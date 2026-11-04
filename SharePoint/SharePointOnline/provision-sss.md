---
layout: Conceptual
title: Provision the SharePoint Success Site - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/provision-sss
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2020-08-21T00:00:00.0000000Z
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: high
ms.collection:
- Strat_SP_modern
- M365-collaboration
ms.custom: admindeeplinkSPO
search.appverid:
- SPO160
- MET150
description: Provision the SharePoint Success Site
locale: en-us
document_id: d5c747f8-17cb-209a-a503-a9caa9da8cd8
document_version_independent_id: 0a7ae298-5bd2-1327-5933-7adfd7c0975a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/provision-sss.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: provision-sss
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/provision-sss.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: a90691cb-7477-3079-eec2-3f7de5774c04
---

# Provision the SharePoint Success Site - SharePoint in Microsoft 365 | Microsoft Learn

Start the SharePoint Success Site provisioning process by understanding the prerequisites. We recommend provisioning the SharePoint Success Site from the Microsoft 365 learning pathways administration page by following the instructions in this article. Global Administrator (sometimes called tenant administrator) credentials are required to start the provisioning process for the SharePoint Success Site.

Important

Microsoft recommends that you use roles with the fewest permissions. Using lower permissioned accounts helps improve security for your organization. Global Administrator is a highly privileged role that should be limited to emergency scenarios when you can't use an existing role.

Before getting started, [watch the provisioning instructional video](https://www.youtube.com/watch?v=HZjxBAKVnJs&amp;feature=youtu.be), follow all steps in the process, and make sure you've met the requirements for provisioning.

## Meet the requirements

Before provisioning the SharePoint Success Site, meet the requirements for both the **person** provisioning and the **tenant.** Your tenant's configuration determines what path you need to take to install the SharePoint Success Site. Start by reviewing the SharePoint Success Site requirements below to prepare your tenant.

| Admin role requirements | + | Tenant requirements | = | Ready to provision |
| --- | --- | --- | --- | --- |

### Admin requirements

The **person** doing the provisioning must be a Global Administrator (sometimes called a tenant admin) where the SharePoint Success Site is provisioned *and must also be* a site admin for the App Catalog.

| Global Administrator role | + | Admin of the App Catalog | = | Admin role requirements met |
| --- | --- | --- | --- | --- |

**Are you a Global Administrator?**

- **Yes** - Next, confirm your tenant has already enabled the App Catalog.
- **No** - Partner with your global admin to get the site provisioned. [Learn more about admin roles](/en-us/microsoft-365/admin/add-users/about-admin-roles).

If you aren't sure, you can confirm your role by signing in to office.com. If you're a Global Administrator, you see an Admin center app icon in the app launcher next to your Microsoft 365 apps.

**Are you a site administrator for the App Catalog?**

- **Yes** - Next, confirm your tenant has Microsoft 365 learning pathways provisioned.
- **No** - Next, ask your Global Administrator to add you as an [App Catalog administrator](/en-us/office365/customlearning/addappadmin).

#### Tenant requirements

The **tenant** where the site is provisioned must have the [App Catalog](use-app-catalog) installed *and* have the latest version of [Microsoft 365 learning pathways](/en-us/office365/customlearning/#:%7E:text=Microsoft%20365%20learning%20pathways%20is%20a%20customizable%2C%20on-demand,adoption%20of%20Microsoft%20365%20services%20in%20your%20organization.) installed. Your tenant must have **version 4.0 or higher** of Microsoft 365 learning pathways.

| App Catalog installed | + | Microsoft 365 learning pathways 4.0 or higher installed | = | Tenant requirements met |
| --- | --- | --- | --- | --- |

Use this decision tree to determine your tenant's path to meeting the **tenant** requirements.

![Decision tree](sharepointonline/media/sss-decision-tree-2.png)

Ready to get started provisioning? Review the provisioning instructions.

**Does your tenant have the App Catalog installed?**

- **Yes** - Next, confirm you're an administrator of the App Catalog.
- **No** - Next, [enable the App Catalog](https://www.bing.com/videos/search?q=where+to+find+the+app+catogue+in+sharepoint&amp;docid=608008189208497248&amp;mid=99CF7FB554B328AC189899CF7FB554B328AC1898&amp;view=detail&amp;FORM=VIRE) (this takes about 30 minutes).

If you're unsure, navigate to the SharePoint admin center, then select **Sites** &gt; [**Active sites**](https://go.microsoft.com/fwlink/?linkid=2185220). The **App Catalog** appears in the list of sites.

![Active sites in the SharePoint admin center](sharepointonline/media/sss-active-sites.png)

Important

If you need to create a App Catalog, wait at least 30 minutes after creating before provisioning Microsoft 365 learning pathways and the SharePoint Success Site.

**Does your tenant have Microsoft 365 learning pathways provisioned?**

- **Yes** - Next, confirm you're using version 4.0 or higher.
- **No** - [Provision Microsoft 365 learning pathways](/en-us/office365/customlearning/) for the first time.

If you're unsure, navigate to the SharePoint admin center, then select **Sites** &gt; [**Active sites**](https://go.microsoft.com/fwlink/?linkid=2185220). **Microsoft 365 learning pathways** appear in the list of sites.

**Is your tenant's version of learning pathways version 4.0 or higher?**

- **Yes** - You're ready to provision the SharePoint Success Site.
- **No** - Update to version 4.0 or higher and then provision the SharePoint Success Site from the Microsoft 365 learning pathways administration page.

If you're unsure, navigate to your tenant's **Microsoft 365 learning pathways administration page** and select the ellipses **(...)**

![Image learning pathways admin page](sharepointonline/media/sss-lp-version.png)

Then, select **About web part** to confirm the current version.

![Image learning pathways admin page version](sharepointonline/media/sss-lp-elipses.png)

#### If you need to, update Microsoft 365 learning pathways from version 3.0 to version 4.0 or higher

Important

The person updating Microsoft 365 learning pathways must be a site administrator for the App Catalog. If the person provisioning Microsoft 365 learning pathways isn't a site administrator for the App Catalog, [add an administrator to the App Catalog](/en-us/office365/customlearning/addappadmin) and continue.

In this step, you upload the Microsoft 365 learning pathways 4.0 web part to the App Catalog, and then navigate to the Microsoft 365 learning pathways Administration page to start the update process.

**Upload the web part package:**

1. Go to the [GitHub custom learning repository](https://github.com/pnp/custom-learning-office-365/blob/main/installation/customlearning.sppkg), and then download customlearning.sppkg to a local drive on your PC.
2. If you're not already signed in, sign into your tenant with a Global Administrator credentials.
3. Select **Admin &gt; Show All &gt; SharePoint &gt; More Features**.
4. Under **Apps**, select **Open**.
5. Select **App Catalog &gt; Distribute Apps for SharePoint**.
6. Select **Upload &gt; Choose Files**.
7. Select the customlearning.sppkg file you downloaded, then select **OK &gt; Deploy**.
8. From the Learning Pathways site, select Learning pathways administration from the Home menu.
9. You see a prompt asking if you want to update, then select **Start**.
10. When the update is complete, select **Close**.

## Provision the SharePoint Success Site

Once you've confirmed the following, you're ready to provision:

- You're signed in as a Global Administrator.
- Your tenant has the App Catalog enabled.
- You're a site administrator for the App Catalog.
- Your tenant has version 4.0 or higher of Microsoft 365 learning pathways provisioned.

We recommend that you install the SharePoint Success Site by using the following steps. As an alternative, you [can install the SharePoint Success Site from the look book](provision-sss-lookbook), just make sure you follow all instructions. Before getting started, [watch the provisioning instructions video.](https://www.youtube.com/watch?v=HZjxBAKVnJs&amp;feature=youtu.be)

### Provision the SharePoint Success Site to your tenant from the Learning pathways administrative page

1. Navigate to [office.com](https://www.office.com/) or your organization's sign-in location.
2. Sign in with your username and password.
3. Navigate to the location of the site using the URL supplied by your SharePoint Administrator or select SharePoint from the Microsoft 365 home page, and then select the **Microsoft 365 learning pathways** site.
4. From the learning pathways Home menu, select **Learning Pathways Administration**.

    ![Image of the Microsoft 365 learning pathways admin page](sharepointonline/media/sss-sss-admin.png)
5. Select the ellipses **(...)** and then select **Add Content Pack**.

    ![Image of the content pack in the Microsoft 365 learning pathways admin page](sharepointonline/media/sss-content-pack.png)
6. Select SharePoint Success Site to open the SharePoint Success Site provisioning page.
7. Select **Add to your tenant**.
8. Fill out the email address and URL details and then select **Provision**.
9. Select **Complete**.
10. When you see **Provisioning completed** on the provisioning page, you see a new tab appear in your browser called **CustomLearningAdmin**. Select the **CustomLearningAdmin** tab as shown in the following image:

![Image of the Microsoft 365 learning pathways solution tab](sharepointonline/media/custom-learning-admin-tab.png)
11. Then, select **Complete** as shown in the following image to complete the provisioning process:

![Image of the Microsoft 365 learning pathways solution complete button](sharepointonline/media/sss-m365lp-confirm2.png)

    Important

    Make sure to select **Complete** to complete the provisioning process.
12. To confirm the SharePoint Success Site has been successfully provisioned, go to the SharePoint site you provisioned, select **Get Started &gt; Plan your site.** You should see the web part on the page as shown in the following image:

![Image of the SharePoint Success Site landing page, Plan your site](sharepointonline/media/sss-content-landing.png)

## Add Site owners

Assign a few Site owners to grant administrative privileges to customize the site and training content. In order to hide, show, or enable playlists, users need Site owner or Site member permissions to the Microsoft 365 learning pathways site. In order to edit the look, navigation, and site content, users need Site owner or Site member permissions to the SharePoint Success Site.

**Add Site owners or members to both sites**:

1. From the site select **Settings**, then select **Site permissions**.
2. Select **Advanced Permission Settings**.
3. Select **Site owners** or **Site members**
4. Select **New &gt; Add users to this group**, and then add the people you want to be Site owners or Site members.
5. Include a link to **Explore the site** in the sharing message, and then select **Share**.

### Next steps - customize the SharePoint Success Site

Share the URLs for the Microsoft 365 learning pathways administration site and the SharePoint Success site with the Site owners and members who are responsible for customizing the site. Then, [customize](customize-sss) Microsoft 365 learning pathways playlist content and the look and feel of your SharePoint Success Site to meet the needs of your organization.

### Site provisioning help

- Reference [troubleshooting](/en-us/office365/customlearning/feedback) for provisioning help
- See Microsoft 365 learning pathways [FAQs](/en-us/office365/customlearning/faq)
- Share your [feedback](https://github.com/pnp/custom-learning-office-365/issues) with us

#### Frequently asked questions

**Question: What are the requirements for installing the SharePoint Success Site into my tenant environment?**

Answer:

- Ensure SharePoint Online is enabled in your environment.
- The individual that provisions the SharePoint Success Site must be the Global Administrator of the target tenant for install.
- The tenant where the site is provisioned must have:
    - The App Catalog installed
    - Version 4.0 or higher of [Microsoft 365 learning pathways](/en-us/office365/customlearning/#:%7E:text=Microsoft%20365%20learning%20pathways%20is%20a%20customizable%2C%20on-demand,adoption%20of%20Microsoft%20365%20services%20in%20your%20organization.) installed

**Question: Can I provision the site from the look book?**

Answer: Yes, follow the guidance on how to provision from the [look book](provision-sss-lookbook).

**Question: Who has permission to provision the SharePoint Success Site?**

Answer: A Global Administrator.

**Question: I have installed the SharePoint Success Site successfully, but I'm not able to get the Success Site content from the Microsoft 365 learning pathways web part loaded on my site. What should I do?**

Answer:

It's likely that the content pack hasn't been fully installed. You must return to the **CustomLearningAdmin** page that will appear when site provisioning is done to complete the installation. Confirm you have followed steps 10 through 12 above. Review the [provisioning video](https://www.youtube.com/watch?v=HZjxBAKVnJs&amp;feature=youtu.be) for more detail.

**Question: Who has permission to customize the site template?**

Answer: A [SharePoint site owner](/en-us/sharepoint/site-permissions#site-owners) and [above](/en-us/sharepoint/site-permissions).

**Question: Who can create custom playlists and hide or show content in Microsoft 365 learning pathways?**

Answer: A site collection administrator or site owner of Microsoft 365 learning pathways.

**Question: Who has permissions to use the SharePoint Success Site as a user?**

Answer: Any user or guest who has SharePoint site visitor permissions or higher.