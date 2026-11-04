---
layout: Conceptual
title: Plan the SharePoint app in Teams for your organization - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/homesites/plan-sharepoint-app-in-teams
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-07-14T00:00:00.0000000Z
ms.reviewer: 
ms.author: dipadur
author: divyachapan
manager: elizapo
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
description: Build a team of stakeholders to align the primary use cases for your user experience strategy, then plan for each component of the SharePoint app in Teams experience
locale: en-us
document_id: 9801b493-3410-39d8-3484-564fe03c9ff7
document_version_independent_id: d49e00af-0802-f305-57b9-1817d27d04d7
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/homesites/plan-sharepoint-app-in-teams.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: homesites/plan-sharepoint-app-in-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/homesites/plan-sharepoint-app-in-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 6d34b577-31e0-0b08-55e4-13872a63411b
---

# Plan the SharePoint app in Teams for your organization - SharePoint in Microsoft 365 | Microsoft Learn

In the planning phase, build a team of stakeholders to align the goals and primary use cases for your organization's user experience strategy, then start by planning for each component of the SharePoint app in Teams experience. Consider success metrics and adoption tactics to ensure it meets the needs of your organization and users.

Note

- You must have an Enterprise (E), Frontline (F), or Academic (A) license type to create a the SharePoint in Teams experience.
- Users with a Microsoft 365 subscription (E, F, or A license) are limited to creating and using one experience. If you want to create or use two or more experiences (up to 50), then every user in your tenant must have a Microsoft Viva Suite or Viva Communications and Communities license. See [Microsoft Viva plans and pricing](https://www.microsoft.com/microsoft-viva/pricing) for more info.
- You must have SharePoint admin permissions to access the SharePoint admin center. SharePoint in Teams is available on mobile and tablet devices in GCC, GCC High, and DoD environments with limited features. For more information, see the [list of service availability](/en-us/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government#service-availability-for-each-plan).

## Step 1: Plan for the SharePoint app in Teams

The SharePoint app in Teams is designed to help users complete high-priority tasks and easily access important information. It is built on the SharePoint home site technology. This experience can be built over time as your organization adapts and scales. Organizations can use an [existing SharePoint home site](sharepoint-app-in-teams-overview) or create a new site and establish it as a home site for the SharePoint app in Teams.

The SharePoint app in Teams is composed of [four main components](sharepoint-app-in-teams-overview):

- **Dashboard**: The [dashboard](create-dashboard) is your user’s digital toolset. It brings together the tools your users need, enabling quick and easy access whether they are in the office or in the field.
- **News**: You can program News to flow in from organizational sites, boosted news, user’s followed sites, frequent sites, and people users work with in an immersive reader experience.
- **Resources**: Resources provide links to the most popular destinations at your organization. Create your own links and choose to target [specific audiences](https://support.microsoft.com/office/resources-web-part-6ab12c98-0249-4a3e-92d5-776ce2217d37).
- **Announcements**: Use the [Announcements web part](announcements-web-part) to display short messages for important communications in your Home site. This web part is available only in SharePoint home sites.

These components can be featured across Web, desktop, and mobile, but display differently based on screen resolution.

## Step 2: Establish a SharePoint home site either using an existing communication site or create a new one

A SharePoint home site acts as the front door to your organization’s intranet and a gateway to other popular portals that are relevant to the entire organization. A [SharePoint home site](sharepoint-app-in-teams-plan) is a SharePoint communication site that acts as a front door to your organization’s intranet. Once a SharePoint home site is set, the news posted from that site is prioritized across the intranet. A SharePoint home site can be set in the [SharePoint admin Center](sharepoint-app-in-teams-app-config) when creating a new experience, or assigned to an existing SharePoint home site. Having a SharePoint home site also allows you to take advantage of the SharePoint app bar.

### Set up global navigation in the SharePoint app bar (optional)

Once you have a SharePoint home site, you can set up the SharePoint app bar to improve navigation to intranet resources through global navigation, and personalized content like sites, news, files, and lists. Links from the Global Navigation bar can also be imported into the Resources web part.

For more information, see the [introduction to the SharePoint app bar](sharepoint-app-bar).

### Review, prioritize, and modernize content to align with key scenarios and tasks (optional)

After defining the key scenarios and tasks in the planning phase, ensure priority content is located on modern SharePoint communication sites and team sites. Both [modern and classic sites](https://support.microsoft.com/sharepoint/get-started-with-sharepoint/sharepoint-classic-and-modern-experiences) can be used, but only modern sites appear in the Microsoft Teams app. Classic sites open in a separate browser window.

If you have many SharePoint sites, make sure you focus on sites, pages, and content that are relevant to your employee base. Sites and content that are unrelated to key tasks and scenarios can be modernized later.

**Sites that should be reviewed and prioritized**:

- Sites that dashboard cards link to.
- Sites that are displayed in global navigation.
- Sites that frequently publish organizational news.
- Sites that help users complete the most important day-to-day tasks or access important information.

**Resources to help you modernize**:

- Use the [SharePoint modernization scanner](/en-us/sharepoint/dev/transform/modernize-scanner) to create a dashboard that helps you determine modernization readiness.
- Learn more about how to [transform classic sites to modern sites](/en-us/sharepoint/dev/transform/modernize-userinterface-site-pages), or consider [creating new modern sites using SharePoint site templates](https://support.microsoft.com/office/39382463-0e45-4d1b-be27-0e96aeec8398).
- See the article on [healthy portal guidance for high-traffic sites](/en-us/sharepoint/portal-health) for more guidance on how best practices and recommendations for popular sites that are expected to get a high amount of traffic.

## Step 3: Plan the dashboard

Start by identifying the key scenarios that the SharePoint app in Teams needs to support and identify owners of those user experiences. Common scenarios include view paystubs and vacation hours, submit help tickets, catch up on news, check daily lunch menus, find people in a directory, and shift management. For more information, see the [full list available dashboard cards](available-dashboard-cards). If your organization has a specific need that calls for a custom card, consider using the [card designer](use-card-designer) to build your own.

These scenarios can be [targeted to specific audiences](use-audience-targeting-sharepoint-app-in-teams) using Microsoft 365 Groups. Consider which groups of users need access to specific resources.

| General | For information workers | For frontline workers |
| --- | --- | --- |
| - View pay and benefits  - Submit a ticket to the help desk  - Access lunch and café options  - Catch up on news and announcements | - Find people and team information  - Complete required training  - View company holidays | - View and manage shifts  - Access time sheets and popular forms  - View workplace policies and resources |

Collaborate and align with business groups that manage these experiences to determine the best design.

### Planning process

As you work with business owners and key stakeholders to align your overall design strategy, answer the following questions for each task:

- Who is the audience?
- What do users need to accomplish or learn?
- What tools or technology do they use today?
- What tools or technology do you want visitors to use to accomplish their key tasks?
- What information needs to be promoted?

### Design with your audience in mind

As a best practice, it's important to make decisions that are rooted in specific tasks for certain audiences:

- Consider using a common framework for scenario planning that starts by selecting a certain role or audience "In my role as a...".
- Then, narrow down the objective in "I need to...".
- Next, consider the ideal tool or process to meet the objective in "So that I...".
- Lastly, script out what success looks like in "I know this is successful when...".

For example, create a table like the following to list business scenarios that you want to address with cards in the dashboard:

| In my role as... | I need to... | So that... | I know this is successful when... |
| --- | --- | --- | --- |
| Full time user | Easy access to benefit and payroll information | I can quickly check important information without needing help from HR | Requests for help with benefits and payroll to the HR team are reduced |
| Frontline worker | Clock in and out from a mobile device | I can create efficiencies in my workflow | Schedules and breaks are managed from the SharePoint app in Teams |
| People manager | Welcome and onboard new team members | I can grow and develop talent | I spend less time managing standard onboarding functions |
| Sales representative | Access specific product training materials while on a mobile device | Can quickly resolve customer issues | Most customer issues get resolved in real-time |
| HR specialist | Promote the use of the self-service benefits | I can spend more time working with users on unique benefits questions and scenarios | All of my user interactions are about individual critical scenarios |

Keep in mind that not every task should be turned into a card on the Dashboard. Focus on tasks that are the most impactful to your users that can be executed within a short amount of time.

## Step 4: Get ready for News

News presents SharePoint news from organizational sites, boosted news, user’s followed sites, frequent sites, and people users work with in an immersive reader experience. This gives content publishers a reliable method of distributing important news and information, while keeping frontline workers, information workers, and hybrid workers alike engaged and informed on important news and announcements. And it is all based on what permissions a user has to vew various news and their main source site.

Audience targeting can be used to show news content to specific groups of people if you want to present information that is relevant only to a particular group of people. For example, you can target news stories about a specific project to only team members and stakeholders of the project. For more information, see the article on [audience targeting](use-audience-targeting-sharepoint-app-in-teams).

Users can access their news from the News tab.

## Step 5: Plan the resources

Resources are the navigational links to portals and other popular destinations. Resources should be the most important and popular portals for your target audience and can be targeted to specific audiences. If you configured the SharePoint app bar, you can also provide users with links to resources. The global navigation bar can only be accessed outside SharePoint by users through the SharePoint app in Teams by selecting the organizations logo on the Teams app rail.

For more information, see the article on [editing resources](https://support.microsoft.com/office/resources-web-part-6ab12c98-0249-4a3e-92d5-776ce2217d37). For more information on SharePoint navigation, see the introduction to [SharePoint information architecture](/en-us/sharepoint/information-architecture-modern-experience).

## Step 6: Create an adoption plan

Planning for change and helping users adopt new resources are different for every organization. Use the considerations and best practices here as a starting point to creating an adoption plan that fits your organization’s needs. Include considerations for change management and training materials for end-users in your plan.

### Adoption considerations

- Users can access the SharePoint app in Teams from Microsoft Teams and SharePoint on desktop or mobile devices.
- Use [early adopters and champions](https://adoption.microsoft.com/roles/champion/) to extend their enthusiasm to the rest of the organization.
- Plan to engage with users where they typically meet and share information (for example, if your organization already meets in Teams, plan to post in channels.)
- Determine where questions about the SharePoint app in Teams should go, and who should answer them. Consider using a Viva Engage community, a SharePoint site with guidance and Frequently Asked Question (FAQs), or a specific, monitoed Teams channels to allow users to ask questions or see commonly asked questions.

### Change management considerations

- Start by creating awareness and interest in multiple channels to appeal to different audiences. Consider common spaces for on-site users like the break room or conference rooms. For remote workers and the rest of the organization, plan to post announcements in Teams, Viva Engage, and SharePoint.
- Make sure different audiences of end-users can easily understand how this new tool helps improve their day-to-day work.
- Create opportunities for users to ask questions, get help, and see live demonstrations. Consider setting up weekly training sessions or office hours during the first month of adoption. Use champions where possible.
- Reinforce change by creating incentives for using the new tools.
- Clearly explain how to use the SharePoint app in Teams on desktop and mobile devices, how to engage with the Dashboard, where to find announcements and resources, and where to view the latest news and announcements.
- Create specialized guidance for different audiences like frontline workers or hybrid workers.

### Training considerations

- Use training to help raise awareness about how to use the SharePoint app in Teams on [desktop](https://support.microsoft.com/office/3da30f39-684a-4bde-bb81-2e1407d59b52) and [mobile](https://support.microsoft.com/topic/use-a-screen-reader-to-access-and-customize-viva-connections-on-android-and-ios-c4f573dd-cca0-41bd-a409-bc421bf39f32) devices.
- Showcase different ways to connect and engage with cards on the dashboard.
- Consider providing different training guidance for different audiences.
- Highlight popular links that can be found in the Resources web part when on a mobile device.

## Step 7: Consider success metrics

Part of the planning process includes determining which metrics will be used to measure how effective the SharePoint app in Teams is in bringing your organization together and keeping specific audiences informed.

- **Use the analytics feature within the SharePoint app in Teams:** Use [analytics](sharepoint-app-in-teams-analytics) to understand how and when users engage with various components, the content types users engage with, and the platforms used to access.
- **High-level view of usage across M365 apps:** Use [Microsoft 365 usage analytics](/en-us/microsoft-365/admin/usage-analytics/usage-analytics) to access a prebuilt dashboard that contains several prebuilt reports that focus on adoption of Microsoft 365 apps, usage, communication, and collaboration.
- **Site or page level data:** Get [site level](https://support.microsoft.com/office/2fa8ddc2-c4b3-4268-8d26-a772dc55779e) and [page level](https://support.microsoft.com/office/e3186199-ccc8-4445-9162-bb1bcec8b7ee) usage reports in SharePoint to gauge engagement and learn more about when users access content and what devices they're using.
- **Get direct feedback from users:** Usage analytics aside, you can ask users directly about their overall satisfaction. Consider [creating a card on the Dashboard that links to a Microsoft Form](https://support.microsoft.com/office/4ffb64cc-7d5d-402f-b82e-b1d49418fd9d) where you can ask users to rate satisfaction and provide feedback.

## Step 8: Plan for maintenance over time

As your business grows and evolves, you'll likely identify new scenarios that can be supported by the SharePoint app in Teams. Over time, you might decide to retire cards on the dashboard or rearrange global navigation in resources.

Additionally, users will share feedback that can be used to improve the experience. Each of these scenarios requires time to implement and to communicate as needed. Plan to have a point-person, or team of people, who can manage these tasks over time, update the dashboard, adjust resources, and more.

## Next, build and customize the SharePoint app in Teams for your organization

After you meet requirements, have a plan for the dashboard, and are prepared to help users adopt the SharePoint app in Teams experience, it's time to [move on to the build phase](build-sharepoint-app-in-teams).