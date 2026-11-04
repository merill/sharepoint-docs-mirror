---
layout: Conceptual
title: Create or edit a Secure Store Target Application - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/create-or-edit-secure-store-target-application
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2018-07-11T00:00:00.0000000Z
ms.reviewer: 
ms.author: ruihu
author: maggierui
manager: jtremper
audience: Admin
f1.keywords:
- CSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.collection: M365-collaboration
ms.localizationpriority: medium
ms.custom: admindeeplinkSPO
search.appverid:
- MET150
- SPO160
ms.assetid: f724dec2-ce28-4b76-9235-31728dce64b5
description: Learn how to configure a Secure Store Target Application, including application IDs and credentials for the external data source.
locale: en-us
document_id: a78da1cd-d47b-3dea-5c7e-7d7ed5061cdf
document_version_independent_id: a92e04f1-723d-f665-d377-fc2eff3a0ba3
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/create-or-edit-secure-store-target-application.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: create-or-edit-secure-store-target-application
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/create-or-edit-secure-store-target-application.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: f78ea158-2229-7904-3f80-815b916c8f0e
---

# Create or edit a Secure Store Target Application - SharePoint in Microsoft 365 | Microsoft Learn

When you want to use external data (such as data from your other business applications or partner resources) in SharePoint, you can use Business Connectivity Services (BCS) together with Secure Store. And, you can manage BCS and Secure Store right in the [SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185219). The external data source that you can connect to is called a Secure Store Target Application, or just a Target Application.

BCS makes it possible for you to set up a connection to the Target Application, and the Secure Store enables you to manage the credentials that are required by the external data source.

Note

To access the Secure Store, you must have at least the [SharePoint Administrator](sharepoint-admin-role) role.

## How the Secure Store Service Works

This SharePoint service makes access to external business application data easier. In order to understand why the Secure Store Service offers this benefit, it's important to understand that the username and password used to access external data stores may not be the same as the username and password used to access SharePoint. When a user accesses a SharePoint page that displays information from an external data system, SharePoint must make a separate request to retrieve information from the external data system. This must be made with credentials that are known to the external data system in order for the request for content to be successful. Only then can SharePoint display the information from the external data system on the page. The Secure Store Service stores the external data system credentials for this reason.

The Secure Store Service is designed to create a background mapping between a group of users in SharePoint, and a single user known to the external data system. When the Secure Store Service is properly configured, the following occurs:

- A user authenticates through Internet Information Services (the web server technology underlying SharePoint technologies) to SharePoint via valid credentials.
- Inside SharePoint, the Secure Store Service uses mapped credentials known to the external business application to render any necessary external data on the site for the authenticated user.

Another benefit of the Secure Store Service is that it eliminates authentication prompts for users. When users navigate to SharePoint pages that access external data systems, the Secure Store Service is active in the background, checking user rights and providing mapped credentials to the external data when appropriate. This allows users to access the required data without prompting them to enter usernames and passwords specific to the external application.

## Create a Target Application

1. Go to [**More features** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185077), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

Note

If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.

1. Under **Secure store**, select **Open**.
2. In the **Manage Target Applications** group on the ribbon, select **New**.

    ![Configuring a Secure Store Target Application in the SharePoint admin center](sharepointonline/media/c3ba43ae-b8df-4b63-b187-9ce1bd6cb42f.png)
3. In the **Target Application Settings** section, enter values for the following fields:
4. **Target Application ID**. You might find it useful to assign a meaningful name. For example, if you are connecting to source that contains employee data, you might enter EmployeeTargetApp.
5. Display Name. This field should be a user-friendly name for the Target Application. For example, you might use Employee Data.
6. **Contact E-mail** Enter a valid email address for people to use when they have questions.
7. **Target Application Type**. By default, SharePoint uses type **Group Restricted**.
8. In the **Credential Fields** section, for the credentials that are required to access data in the Target Application, enter the **Field Names** and **Field Types**. These fields determine how you will map identity in the Secure Store Service. By default, the Credential Fields list the Windows User Name and Windows Password with matching Field Types (User Name and Password), and specifies that the password is masked.
9. In the **Target Application Administrators** section, enter a list of users, or to search for the name of a group, select **Browse**. This section usually contains the account of the SharePoint Administrator, or a Global Administrator.
10. In the **Members** section, enter a list of users or SharePoint groups of users who need to access the target app. Or, to search for the name of a group that you want to map to the Target Application, select **Browse**.
11. Select **OK** to accept this configuration and return to the Secure Storage Service page. The new Target Application appears on the page.

## Edit settings for a Target Application

1. Go to [**More features** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185077), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

Note

If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.

1. Under **Secure store**, select **Open**.
2. From the list of Target Applications, select an existing Target Application.
3. On the ribbon, select **Edit**.

    Note

    Some fields on the Edit page are not available. These elements cannot be edited. After you create a Target Application, you can't change the **Target Application ID**, **Target Application Type**, or **Credentials Fields**.
4. Select any of the following to edit the contents:

- Display Name
- Contact E-mail
- Target Application Administrators
- Members

1. Select **OK**.

## Set credentials for a Target Application

1. Go to [**More features** in the SharePoint admin center](https://go.microsoft.com/fwlink/?linkid=2185077), and sign in with an account that has [admin permissions](sharepoint-admin-role) for your organization.

Note

If you have Office 365 operated by 21Vianet (China), [sign in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), then browse to the SharePoint admin center and open the More features page.

1. Under **Secure store**, select **Open**.
2. Select a single Target Application from the list if you have created more than one.
3. In the **Credentials** group on the ribbon, select **Set**. This opens the **Set Credentials for Secure Store Target Application (Group)** dialog. When you set credentials, you map a Target Application Group to a single set of credentials for an external data system.

    ![Screenshot of the &quot;Set credentials for a Secure Store Target Application&quot; dialog. You can use this dialog to set the logon credentials for an external data source](sharepointonline/media/ca3584ac-34d5-431d-a803-a6888b3a451d.png)
4. In the **Set Credentials for Secure Store Target Application (Group)** dialog, enter the credential values that you want. The credential fields that you enter apply to the external data system.

    Note

    The following fields cannot be edited. These fields specify the Secure Store mapping for the Target Application: **Target Application Name**, **Target Application ID**, and **Credential Owners**.

    Important

    Be careful when you enter the password. If you enter a password that is incorrect, you won't see a message about the error. Instead, you'll be able to continue with configuration. However, errors can occur later, when you attempt to access data through BCS. Also, if the password for the external data source is updated, you have to return to this page to manually update the password credentials.
5. When you finish entering values for credential fields, select **OK**.