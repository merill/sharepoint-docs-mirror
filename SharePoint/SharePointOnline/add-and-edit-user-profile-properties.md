---
layout: Conceptual
title: Add and edit user profile properties in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/add-and-edit-user-profile-properties
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2025-01-16T00:00:00.0000000Z
ms.reviewer: waynewin
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.custom: admindeeplinkSPO
ms.collection:
- Strat_SP_admin
- M365-collaboration
search.appverid:
- SPO160
- BSA160
- GSP150
- MET150
ms.assetid: 85091402-737f-4bb9-99a7-bc5f194502a8
description: Learn how to add and edit properties on SharePoint user profiles that are configured from information that your organization supplies to the Microsoft 365 directory service.
locale: en-us
document_id: 089de41e-64c6-4698-5a2e-deafe6fac8ea
document_version_independent_id: 99812440-95be-2284-4b90-3088f55b3772
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/add-and-edit-user-profile-properties.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: add-and-edit-user-profile-properties
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/add-and-edit-user-profile-properties.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: cd3a11cd-6092-a52c-9584-c24f2bff7ccc
---

# Add and edit user profile properties in SharePoint - SharePoint in Microsoft 365 | Microsoft Learn

If your organization uses the cloud identity model, your user accounts are stored in Microsoft Entra ID and you can manage most user profile info in the Microsoft 365 admin center. For info, see [Edit or change a user in Microsoft 365](/en-us/office365/admin/add-users/change-a-user-name-and-email-address). You can also manage user profiles (including adding user pictures and defining user managers) in the Microsoft Entra admin center. For info, see [Add or change profile information for a user in Microsoft Entra ID](/en-us/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal). If you need to create custom user profile properties, such as languages spoken, emergency contact info, or sales account, you can use user properties in SharePoint. Note that these properties are NOT synced back to Microsoft Entra ID.

## Add a property for a user profile

1. Go to [**More features** in the new SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185077), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

Note

If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.

1. Under **User profiles**, select **Open**.
2. Under **People**, select **Manage User Properties**.

    ![Manage User Properties link under Admin user profiles.](sharepointonline/media/ab8985da-a2f9-4839-b4a2-f0feeb379f31.png)
3. Select **New Property**.
4. In the **Name** box, enter a unique name for the property.

    ![Property settings under User Profile in Admin](sharepointonline/media/b18946ee-7db7-4587-9f0b-2ea1d892415f.png)
5. In the **Display Name** box, enter the profile property name that will be displayed to all users. (This name doesn't have to be unique.)
6. In the **Type** list, select the data type for the property.

    Note

    If you select **string (Multi Value)**, the property will be permanently set as a multi-valued property. You can't change this setting after you select **OK**. You can only delete the property and add it again as a new single-value property.
7. If you selected binary, HTML, or string, use the **Length** box to enter the maximum number of characters allowed for property values.
8. If you selected string and want to associate the profile property with a [managed metadata term set](managed-metadata), select **Configure a Term Set to be used for this property**. Then select a term set from the list.
9. Make sure **Default User Profile Subtype** is selected so the default user profile subtype is associated with this user profile property.
10. In the **Description** box, enter the instructions or information that is displayed to users about this profile property.
11. In the **Policy Settings** section, select the policy setting and default privacy setting that you want for this property. Select the **User can override** box to enable users to override these settings.
12. If you want users to be able to change this profile information for themselves, select **Allow users to edit values for this property**.
13. In the **Display Settings** section, specify whether and how the property will be viewed by users.
14. In the **Search Settings** section, select **Alias** if the property is the equivalent of a user's name. For example, you might do this if you create a property for a "Stage name" and want searches for all documents by John Kane to return the same results as searches for the user's real name. Select the **Indexed** if you want searches to return all the user profiles matching that property. For example, if you have a property for "University," a search for that value would return all alumni from that university.

    Note

    The **Alias** check box is available only if you set the **Default Privacy Setting** &gt; **Everyone**.
15. Select **OK**.

## Edit or delete a property you added

1. Go to [**More features** in the new SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185077), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

Note

If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.

1. Select **User profiles**, and then select **Open**. Under **People**, choose **Manage User Properties**.

    ![Manage User Properties link under Admin user profiles.](sharepointonline/media/ab8985da-a2f9-4839-b4a2-f0feeb379f31.png)
2. In the **Property Name** column, select the profile property that you want to change, and then select **Edit** or **Delete**.
3. Edit the elements you want to change.

    Note

    Some elements of profile properties, such as the **Type** element, are unavailable because they can't be edited. To define these elements, create a new property. The exception is the Source Data Connection property. It's predefined in SharePoint and can't be changed.
4. When you're done, select **OK**.

## Synchronize custom properties

Custom properties from Active Directory or Microsoft Entra ID aren't synchronized with SharePoint. For info about bulk updating custom user profile properties by using PowerShell, see [Call the import API from PowerShell](/en-us/sharepoint/dev/solution-guidance/bulk-user-profile-update-api-for-sharepoint-online#call-the-import-api-from-powershell).

## Need more help?

![Ask a question](/en-us/office/media/icons/pngs/users-group-blue-32.png) If you have technical questions about this topic, you might find it helpful to post them on the [SharePoint discussion forum](https://social.technet.microsoft.com/Forums/sharepoint/home?forum=onlineservicessharepoint). It's a great resource for finding others who have worked with similar issues or who have encountered the same situation.