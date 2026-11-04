---
layout: Conceptual
title: Create an organization assets library - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/organization-assets-library
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-04-03T00:00:00.0000000Z
ms.reviewer: cathed
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
search.appverid:
- SPO160
- MET150
ms.collection:
- M365-collaboration
- m365initiative-spsitemanagement
description: Specify a library as a location for assets that are centrally stored and managed in your organization.
locale: en-us
document_id: 5bacce83-65f6-b862-e413-09122aee356d
document_version_independent_id: 5c4e1169-1d5d-6e0d-d574-f3aaba0a5d92
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/organization-assets-library.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: organization-assets-library
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/organization-assets-library.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://authoring-docs-microsoft.poolparty.biz/devrel/60932d05-feee-4685-a73b-595e25dd9318
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://authoring-docs-microsoft.poolparty.biz/devrel/c43bb58b-1190-419b-8d18-e6052371b599
platformId: e4f05a5c-d3c0-fb01-f63e-9e637bd43190
---

# Create an organization assets library - SharePoint in Microsoft 365 | Microsoft Learn

Note

This feature is not available for Office 365 operated by 21Vianet (China) or Microsoft 365 US Government plans.

You can specify up to 30 organization asset libraries for a single organization. All of these libraries (regardless of type) must be on the same site. Only libraries (not folders) can be set as organization asset libraries.

If your organization needs to store and manage files for all your users to use, you can specify one or more document libraries on a SharePoint site as an "organization assets library." You can create two types of organization assets:

- **Images such as photos and logos**: When a user adds a web part to any modern page in SharePoint and that web part opens the file picker, the user can select "Your organization" in the left pane to browse the libraries you've specified.

    ![Selecting an image to add to a SharePoint page](sharepointonline/media/imagelibrary.png)
- **Office templates**: When a user creates a new Office document, they can select the tab for your organization to see the available templates. The following Office apps are supported:

    - Word, Excel, or PowerPoint desktop apps. Microsoft 365 Apps Version 2002 or later is also required.

        ![Selecting a template in PowerPoint](sharepointonline/media/office-templatelibrary.png)
    - PowerPoint on the web. Templates aren't available from the **New** menu. Instead, users need to go to the PowerPoint start page and select **Office Template Library**. For the organization assets library to appear to a user in PowerPoint on the web, the user must be assigned a license to Office 365 E3 or E5.

        Note

        - For the organization assets library to appear to a user in PowerPoint on the web, the user must be assigned a license to Office 365 E3 or E5. Users who use the Word, Excel, or PowerPoint desktop app also need Microsoft 365 Apps Version 2002 or later. (The organization assets library is not available in Word on the web or Excel on the web.)
        - Allow up to 24 hours for the organization assets library to appear to a user in the desktop apps.
        - Uploaded template files must be in the following formats:
            - **Excel**: .xltx. [Learn how to save an Excel workbook as a template](https://support.microsoft.com/office/save-a-workbook-as-a-template-58c6625a-2c0b-4446-9689-ad8baec39e1e).
            - **Word**: .dotx. [Learn how to save a Word document in this format](https://support.microsoft.com/topic/create-a-template-86a1d089-5ae2-4d53-9042-1191bce57deb).
            - **PowerPoint**: .potx. [Learn how to save a PowerPoint file in this format](https://support.microsoft.com/office/ee4429ad-2a74-4100-82f7-50f8169c8aca).
        - Users need at least read permissions on the root site for your organization for the organization assets library to appear in the desktop apps.

        Organization fonts are supported on PowerPoint for the web. [Learn more about support for your organization fonts here.](support-for-organization-fonts-in-powerpoint-for-the-web)

## Use Microsoft PowerShell to specify a library as an organization assets library

1. Select an existing site or create a new site for the organization assets. This can be any type of site, such as a communication site, a team site that's connected to a Microsoft 365 Group, or a modern team site that isn't connected to a Microsoft 365 Group.

    Note

    All organization asset libraries must be on the same site.
2. **Set the permissions on the site**. Add the people you want to be able to upload files as members or owners of the site or Microsoft 365 Group.

    Note

    Adding "Everyone except external users" as visitors is required. If necessary, [customize the permissions for the library](https://support.office.com/article/02d770f3-59eb-4910-a608-5f84cc297782). You can customize the permissions of up to 100 files and folders in the library.
3. Upload the images or Office templates to a document library.
4. [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    Note

    If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell."
5. Connect to SharePoint as [at least a SharePoint Administrator](sharepoint-admin-role) in Microsoft 365. To learn how, see [Getting started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
6. Run the following command to designate the document library as an organization assets library:

    ```PowerShell
    Add-SPOOrgAssetsLibrary -LibraryUrl <URL> [-ThumbnailUrl <URL>] [-OrgAssetType <ImageDocumentLibrary or OfficeTemplateLibrary>] [-CdnType <Private or Public>]
    ```

    - *LibraryURL* is the absolute URL of the library to be designated as a central location for organization assets.
    - *ThumbnailURL* is the URL for the image file that you want to appear in the card's background in the file picker; this image must be on the same site as the library. The name publicly displayed for the library will be the organization's name.
    - *OrgAssetType* is either `ImageDocumentLibrary` or `OfficeTemplateLibrary`. If you don't specify the *OrgAssetType*, the library will be designated as an image library by default.
    - *CdnType* needs to be specified only if you want to create a public CDN. If you don't specify the *CdnType*, it enables a private CDN by default. 

        [Learn more about the Add-SPOOrgAssetsLibrary cmdlet](/en-us/powershell/module/sharepoint-online/add-spoorgassetslibrary).

    Example:

    ```powershell
     Add-SPOOrgAssetsLibrary -LibraryURL https://contoso.sharepoint.com/sites/branding/Assets -ThumbnailURL https://contoso.sharepoint.com/sites/branding/Assets/contosologo.jpg -OrgAssetType         ImageDocumentLibrary
    ```

Note

Adding an organization assets library will enable a content delivery network (CDN) for your organization to provide fast and reliable performance for shared assets. You'll be prompted to enable a CDN for each organization asset library you add. For more information, see [Content Delivery Networks (CDNs)](/en-us/office365/enterprise/content-delivery-networks).

## Related commands

- See information about all organization asset libraries on the site: `Get-SPOOrgAssetsLibrary`[Learn more about this cmdlet](/en-us/powershell/module/sharepoint-online/get-spoorgassetslibrary).
- Update thumbnail URL: `Set-SPOOrgAssetsLibrary -LibraryUrl <String> -ThumbnailUrl <String>`[Learn more about this cmdlet](/en-us/powershell/module/sharepoint-online/set-spoorgassetslibrary).
- Remove a library: `Remove-SPOOrgAssetsLibrary -LibraryUrl <String>`[Learn more about this cmdlet](/en-us/powershell/module/sharepoint-online/remove-spoorgassetslibrary).