---
layout: Conceptual
title: Package biz apps into organizational list templates - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/package-biz-apps-org-list-template
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-06-25T00:00:00.0000000Z
ms.reviewer: hasaladi
ms.author: v-smandalika
author: v-smandalika
manager: dansimp
audience: Admin
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: lists
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.collection:
- M365-collaboration
description: Learn how to package biz apps into organizational list templates.
locale: en-us
document_id: 61878c2f-1f0b-5854-978e-857c3b041efb
document_version_independent_id: f74df08c-8f44-7a8d-8dbe-3164ae3ddebb
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/package-biz-apps-org-list-template.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
interactive_type: powershell
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: package-biz-apps-org-list-template
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/package-biz-apps-org-list-template.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/1ae5c491-970a-4062-8301-6336e69f9026
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/f2c3e52e-3667-4e8a-bf11-20b9eaccdc8c
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 54410cb0-b943-051a-7f31-8c7808e71186
---

# Package biz apps into organizational list templates - SharePoint in Microsoft 365 | Microsoft Learn

There are a number of steps by which you can create a packaged SharePoint list template that contains in-built custom flows. The objective is to assemble and register a packaged file that contains the site script actions needed to create the list and the flows, and a Dataverse solution archive (zip) that contains the flow definitions.

Once you have your source SharePoint list set up and are ready to work on integrating flows with it, and on assembling a template with these components, perform the following the steps:

## Obtaining solution zip file

1. Sign in to Power Automate portal by launching https://flow.microsoft.com/ (or choose **Integrate &gt; Power Automate &gt; See your flows**" in the SharePoint Portal).
2. Create a new Dataverse solution by referring to [Overview of solution-aware flows](/en-us/power-automate/overview-solution-flows).

    For an introduction to Dataverse solutions, see [Solution concepts](/en-us/power-platform/alm/solution-concepts-alm).
3. Add a new flow or customize existing flows to this solution by referring to [Create a cloud flow in a solution](/en-us/power-automate/create-flow-solution).
4. Ensure that your flows use connection references for each trigger and action that you use. For more information on how to use a connection reference, see [Use a connection reference in a solution](/en-us/power-apps/maker/data-platform/create-connection-reference).
5. Once you're satisfied with the contents of your solution (including any connection references or environment variables you wish to set up), [export and download](/en-us/power-automate/export-flow-solution) it to a disk.
6. Extract all files from the zip file into a separate folder.
7. Browse into the folder's **Workflows** subfolder.
8. Open each flow-related .json file and then search and replace all instances of the following elements:

    1. **The URL of the SharePoint site that the original list resided in**: Replace with **{ContextSharePointSiteUrl}**.
    2. **The ID of the original SharePoint list**: Replace with **{ContextSharePointListId}**.

    **For example**:

    **[Before replacements]**

    ```powershell
    "parameters": {
       "dataset": "https://microsoft.sharepoint-df.com/teams/AlinTest ",
       "table": "d6ac2804-7a1c-4cd4-98c8-56b85a9294b7"
                }
    ```

    **For example**:

    **[After replacements]**

    ```powershell
    "parameters": {
       "dataset": "{ContextSharePointSiteUrl}",
       "table": "{ContextSharePointListId}"
                }
    ```
9. Save the changes and close all file editors that you've opened for these files.
10. Go back to the root folder of the solution; select all files (solution.xml, customizations.xml, and so on) and folders; right-click and choose **Compress to ZIP file** from the context menu.

    [![Selecting all the files and compressing them to a zip.](sharepointonline/media/select-all-files-compress-to-zip-file.png)](sharepointonline/media/select-all-files-compress-to-zip-file.png#lightbox)

    You can keep this resulting zip file, and you can also choose to discard the original solution zip file that earlier downloaded (as specified in Step 6 of this procedure).

## Obtaining the site script action file (manifest.json)

Important

Prior to performing the steps in this section, ensure that you've tested your prototype list and flows to your satisfaction.

1. Ensure you've installed SharePoint Online Management Shell on your computer.
2. Launch SharePoint Online Management Shell.
3. Run the following command to connect to the tenant's admin service:

    `[Connect-SPOService](/powershell/module/sharepoint-online/connect-sposervice)  -Url <Link to SPO admin portal> -Credential <full username of the admin user>`
4. Run the following command to extract a site script file from the target list:

    `[Get-SPOSiteScriptFromList](/powershell/module/sharepoint-online/get-spositescriptfromlist)  -ListUrl <full URL of the target list> | Out-File manifest.json`
5. Open the *manifest.json* file in your favorite text (or code) editor and manually add an action with the verb "importBusinessApps," the relative path of your solution file inside the overall template package and the target listName (in this case, the title of the listName binding). This value should be the same as the *listName* property of the "CreateSPList" action.

    For example:

    [![Adding a verb in the .json file.](sharepointonline/media/adding-verb-json-file.png)](sharepointonline/media/adding-verb-json-file.png#lightbox)

## Assembling the final SharePoint package zip file

1. Ensure that the solution zip file and the *manifest.json* file (from previous step) are in the same folder location.
2. Select these two files; right-click and then select **Compress to ZIP file** (or **Send to &gt; ZIP file**, depending on the OS).

## Registering the new template as a list design

1. To upload the zip file (created in Assembling the final SharePoint package zip file) as a site script package, run the following command in the same management shell window:

    `$pkg = Add-SPOSiteScriptPackage -Title "<script title>" -Description "<script description>" -ContentPath '<relative path to zip file from previous step>'`

    Note

    Inclusion of the *Description* property in the command is optional.
2. Take a peek at the new package by printing out its properties through the following command:

    `"$pkg"`

    The output should contain an *Id* property which is needed in the following steps.

    Note

    (Optional) Run `Get-SPOListDesign` to ensure you're not adding a duplicate with the same title/description, or to inspect what's already there.
3. Run the following command:

    `Add-SPOListDesign -Title "<list design title>" -Description "<list design description>" -SiteScripts $pkg.Id`

    If the list design was successfully created, you should be able to view it in the **From your organization**" area of the **Create List** dialog.