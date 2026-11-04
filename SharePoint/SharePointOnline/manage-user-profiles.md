---
layout: Conceptual
title: Manage user profiles in the SharePoint admin center - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/manage-user-profiles
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-04-30T00:00:00.0000000Z
ms.reviewer: waynewin
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords:
- CSH
ms.topic: how-to
ms.custom:
- ViewUserProfiles
- SPOTAMgUserProfiles
- seo-marvel-apr2020
- admindeeplinkSPO
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Strat_SP_admin
- M365-collaboration
- essentials-manage
search.appverid:
- SPO160
- MOE150
- BSA160
- GSP150
- MET150
ms.assetid: 494bec9c-6654-41f0-920f-f7f937ea9723
description: Use the SharePoint admin center to create and edit custom user properties, add or remove admins on OneDrive accounts, manage audiences, and disable OneDrive creation.
locale: en-us
document_id: be31bf07-922b-7307-a30e-f09d00fb79f3
document_version_independent_id: a42d0699-1acf-808c-0d86-dc3516f4dfaf
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/manage-user-profiles.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-user-profiles
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/manage-user-profiles.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
platformId: a9735a0f-77f2-1a3f-7885-c1a85ba4e880
---

# Manage user profiles in the SharePoint admin center - SharePoint in Microsoft 365 | Microsoft Learn

This article is for [SharePoint Administrators](/en-us/sharepoint/sharepoint-admin-role) and [above](/en-us/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365.

- If you're running SharePoint Server, see [Administer the User Profile service in SharePoint Server](administration/user-profile-service-administration).
- If you're not an admin, see [View and update your profile in Office Delve](https://support.office.com/article/4e84343b-eedf-45a1-aeb9-8627ccca14ba) for info about changing your profile.

Most organizations don't need to change any user profile settings in the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219). For the organizations that do need to work with user profile settings, this article describes the most common tasks.

## Create and edit custom user properties

In Microsoft 365, identity is managed by Microsoft Entra ID. For info about this, see [Understanding Microsoft 365 identity and Microsoft Entra ID](/en-us/office365/enterprise/about-office-365-identity). SharePoint receives this profile information as described in [About user profile synchronization](user-profile-sync). If you need to store additional info about your users, you can create custom properties in the classic SharePoint admin center. For info about doing this, see [Add and edit user profile properties in SharePoint](add-and-edit-user-profile-properties).

Note

Instead of creating user sub-types in the SharePoint admin center, we recommend using the Microsoft 365 admin center to [Compare groups](/en-us/office365/admin/create-groups/compare-groups) or using the Microsoft Entra admin center to [create groups with dynamic membership](/en-us/azure/active-directory/users-groups-roles/groups-dynamic-membership).

## Add and remove admins for a user's OneDrive

Follow these steps to transfer ownership of a OneDrive to a different user, or give a user full control over another user's OneDrive.

1. Go to [**More features** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185077), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

Note

If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.

1. Under **User profiles**, select **Open**.
2. Under **People**, select **Manage User Profiles**.

    ![The Manage User Profiles link on the user profiles page](sharepointonline/media/de423783-b0dd-4742-a937-c634936f0dca.png)
3. Enter the user's name and select **Find**.
4. Right-click the user, and then select **Manage site collection owners**.
5. Add and remove admins for the OneDrive, and then select **OK**.

    ![Manage the owners of a OneDrive](sharepointonline/media/120f7c8c-262f-4a41-a484-e830c662f534.png)

Warning

Do not remove a user as the admin of their own OneDrive. Doing this causes many experiences to break.

For info about automatically transferring ownership of OneDrive to a user's manager when the user account is marked for deletion, see [Set up access delegation](/en-us/onedrive/retention-and-deletion).

## Manage audiences (classic experience)

Audiences let you customize content on pages so that it appears only to particular people based on their:

- Membership in a distribution list or security group
- Location in the reporting structure or public info in the user profile

For example, you can display a navigational link to only people in a particular geographic location. For info about using audiences and information about using audience targeting in the modern experience, see [Target content to specific audiences](https://support.office.com/article/33d84cb6-14ed-4e53-a426-74c38ea32293).

Note

Only sites that use classic templates can be customized based on audience. Audiences are not a security feature. They help you deliver relevant content to specific groups of people, but don't prevent content from being available to anyone with the appropriate permissions.

To add, edit, or delete an audience or an audience rule, go to the Manage Audiences page:

1. Go to [**More features** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185077), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

Note

If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.

1. Under **User profiles**, select **Open**.
2. Under **People**, select **Manage Audiences**.

    ![The Manage Audiences link on the user profiles page](sharepointonline/media/5d94f074-ce73-4b11-a415-027e1b65b547.png)

    Creating a new audience:

    ![Creating a new audience](sharepointonline/media/8396cb6b-5426-40e0-9024-126bca6e8cc9.png)

    Creating a new rule for the audience:

    ![Creating rules for a new audience](sharepointonline/media/deafdd2d-4770-4344-87af-9dd1c1e6d7c4.png)

Audiences compile approximately weekly, and you can only view audience members after the audience compiles. The user profiles page shows the number of audiences, the number of uncompiled audiences, and the compilation status and time.

## Disable OneDrive creation for some users

If some users are licensed to use OneDrive, but you don't want them to create a OneDrive (perhaps for regulatory reasons), you can prevent them from doing so.

Note

If a user already created a OneDrive, changing the following setting won't delete it.

1. Go to [**More features** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185077), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

Note

If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.

1. Under **User profiles**, select **Open**.
2. Under **People**, select **Manage User Permissions**.

    ![The Manage User Permissions link on the user profiles page](sharepointonline/media/946e0564-2e7d-40a6-8603-cc3534a557be.png)
3. By default, "Everyone except external users" has permission to "Create Personal Site" (which includes creating a OneDrive and saving user data such as followed and frequent sites). Remove that group and add specific groups to allow only a subset of licensed users to create a OneDrive.

    ![The permissions dialog for controlling who can create a OneDrive](sharepointonline/media/a23b4ec4-7862-4fd4-895a-983fed62c24d.png)
4. Select **OK**.