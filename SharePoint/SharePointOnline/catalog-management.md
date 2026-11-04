---
layout: Conceptual
title: Catalog management in SharePoint Advanced Management - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/catalog-management
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-10-08T00:00:00.0000000Z
ms.reviewer: nvasudevan
manager: dansimp
ms.author: deniseb
author: denisebmsft
audience: Admin
customer-intent: As a SharePoint admin, I want to gain insights into content distribution across my organization to optimize resource management.
f1.keywords:
- NOCSH
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Highpri
- Tier2
- M365-sam
- M365-collaboration
- essentials-manage
search.appverid: 
description: Learn how to use Catalog management in SharePoint Advanced Management to gain insights into content distribution across your organization.
locale: en-us
document_id: d0da6e46-7943-9f91-6ae2-e14f571c2921
document_version_independent_id: 0c9f8ae7-856d-7f55-2ceb-df2adff22d12
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/catalog-management.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: catalog-management
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/catalog-management.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
platformId: 1977d1f8-6274-1cd1-bfe2-ccf362a18658
---

# Catalog management in SharePoint Advanced Management - SharePoint in Microsoft 365 | Microsoft Learn

Catalog management in [SharePoint Advanced Management](advanced-management) helps you understand how content is organized across your SharePoint environment. It uses existing Microsoft 365 metadata to automatically group sites into meaningful categories, giving you a centralized view of your content landscape.

[![Screenshot of catalog management in the SharePoint admin center.](sharepointonline/media/catalog-management/catalog-management.png)](sharepointonline/media/catalog-management/catalog-management.png#lightbox)

By grouping sites into categories and groups, you can analyze content, apply governance actions at scale, and gain the insight needed to manage content, reduce risk, and prepare for AI-powered experiences such as Microsoft Copilot.

## How catalog management works

Catalog management organizes SharePoint sites into categories and groups based on metadata already present in your Microsoft 365 tenant.

- **Categories** are high-level classifications such as department, user type, or region.
- **Groups** provide more detail within each category. For example, within the Department category, groups might include Marketing, Sales, HR, or Finance.

This structure helps you understand how content is distributed and governed across your organization.

You can use built-in categories or add your own categories. Each category has a label that identifies its type:

- `BUILT-IN`
- `UPLOADED`
- `CUSTOM PROPERTIES`
- `ENTRA ID`

You can use categories with SharePoint Advanced Management capabilities like [Restricted Content Discovery](/en-us/sharepoint/restricted-content-discovery). For example, you can apply Restricted Content Discovery to multiple sites by using catalog groups. (See the section, Use catalog groups with Restricted Content Discovery in this article.)

## Metadata sources

Catalog management uses metadata from multiple sources to define categories and groups:

- **Microsoft Entra ID**: Organizational attributes such as department, user type, and extension attributes.
- **SharePoint site metadata**: Site properties such as property bag values, site keywords, and other SharePoint-defined properties.

Because catalog management reflects existing metadata, keeping that metadata accurate and consistent is essential for meaningful results.

## Built-in categories

Catalog management includes built-in categories derived from Microsoft Entra ID and SharePoint metadata. Common examples include:

- **Locale**: The region where the content is hosted (for example, North America versus Europe).
- **Department**: The organizational units associated with the site (for example, Finance).
- **User type**: Guest or non-guest.
- **Preferred data location (PDL)**: The [multi-geo setup](/en-us/microsoft-365/enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365) for your sites.
- **Information barriers segment**: The segment defined by [information barriers policies](/en-us/purview/information-barriers-sharepoint) for organizations that implement information barriers.

These categories are automatically populated, available without configuration, and refreshed every hour.

## Categories you can add

Note

You can't use special characters, such as non-English characters, in category names, group names, CSV file names, or display names.

In addition to built-in categories, you can create categories from the following sources:

| Method | Label | Data refresh |
| --- | --- | --- |
| Upload a CSV file that contains a list of sites you want to include in your new category | `UPLOADED` | Right away after the file is uploaded |
| Use a custom site property | `CUSTOM PROPERTIES` | The first data refresh occurs within 24 hours, and after that, every two weeks. |
| Use a Microsoft Entra ID extension attribute | `ENTRA ID` | The first data refresh occurs within 24 hours, and after that, every two weeks. |

### Upload a CSV site list

Note

Each category you add by using this option serves as a snapshot. To update the list of sites, you must update each category manually.

1. In the SharePoint admin center, in the navigation pane, go to **Reports** &gt; **Catalog management**.
2. Select **Add category**. In the **Add category** pane, select **CSV site lists**.
3. Specify a category name and description.
4. Download the CSV template and use it to create your lists. Create one CSV file for each group that you want to create in your category. You can have up to 20 groups in a category.
5. In the **Add category** pane, upload a CSV file. If you have more than one, use **Add group** for each additional CSV file.
6. Select **Save**.

### Use a custom site property

Use this option if your organization already stores classification information in SharePoint site properties, such as department, region, business unit, or compliance designation. Catalog management doesn't create or populate the property values. Instead, it reads existing property values and uses them to create categories and groups. By using this approach, you can organize sites with metadata that already exists in your environment without maintaining manual site lists.

#### Example: Use a Department site property

Suppose your organization already uses a custom site property named **Department** in the SharePoint site property bag. The property might contain values such as:

- Department = Marketing
- Department = Finance
- Department = Human Resources

When you create a catalog category and specify **Department** as the custom property, catalog management scans the selected sites and creates groups based on the values it finds. In this example, catalog management creates separate groups for Marketing, Finance, and Human Resources, and places sites into the appropriate group automatically.

After you determine the site properties you want to use, connect them to catalog management.

#### Connect custom site properties to catalog management

1. In the SharePoint admin center, in the navigation pane, go to **Reports** &gt; **Catalog management**.
2. Select **Add category**. In the **Add category** pane, select **Custom properties**.
3. In the **Properties** section, enter the name of a property that you want to use. To add more properties, select **Add property**. You can specify up to 20 properties.
4. Under **Sites**, select one of the following options:

    - **Most active sites (up to 20,000 sites)**: Data is available within 24 hours and refreshes automatically every two weeks.
    - **Upload a list of up to 20,000 sites**: Download the CSV template and use it to create your site list. Then upload the CSV file. Keep in mind that with this option, the list of sites in the category serves as a snapshot that you must update manually.
5. Select **Save**.

### Use Microsoft Entra ID extension attributes

If your organization uses [Microsoft Entra ID extension attributes](/en-us/entra/identity/domain-services/concepts-custom-attributes), you can create catalog categories based on the values stored in `extensionAttribute1` through `extensionAttribute15`. Extension attributes are predefined attributes in Microsoft Entra ID that organizations can use to store extra string-based metadata for user or device objects.

Catalog management uses these existing attribute values to group SharePoint sites into categories. When you select one or more Microsoft Entra ID extension attributes as catalog categories, Catalog management groups sites based on the extension attribute values associated with site owners. These groupings update when the underlying attribute values or site ownership changes.

For example, your organization might use an extension attribute to identify a business unit, operating model, compliance boundary, program, or other internal classification that isn't represented by a built-in category such as Department or User type. By using that extension attribute as a catalog category, you can view and manage related sites together without manually maintaining a separate site list.

Before you use extension attributes with catalog management, make sure the attributes are populated consistently in Microsoft Entra ID. Catalog management reflects the metadata that already exists in your tenant, so incomplete or inconsistent values can result in incomplete or inconsistent site groupings.

#### Identify or set extension attributes

To view a list of existing extension attributes or to set them, follow the guidance in [Extension attributes](/en-us/graph/extensibility-overview?tabs=http&amp;WT.mc_id=365AdminCSH_spo#extension-attributes). You can identify or set extension attributes by using PowerShell, Python, and more.

After you identify your extension attributes, use them to add categories.

#### Use extension attributes with catalog management

1. In the SharePoint admin center, in the navigation pane, go to **Reports** &gt; **Catalog management**.
2. Select **Add category**. In the **Add category** pane, select **Entra ID extension attributes**.
3. In the **Entra ID extension attributes** list, select the attributes that you want to use as categories.
4. Select **Save**.

## Edit a category or group

You can change the display name of any category, and you can edit categories that aren't built in. Depending on the category type, you can edit display names, descriptions, groups, and site lists. Editing a display name doesn't change the underlying metadata or site grouping.

Note

You can't use special characters, such as non-English characters, in category names, group names, CSV file names, or display names.

1. In the SharePoint admin center, in the navigation pane, go to **Reports** &gt; **Catalog management**.
2. Select a category or group to open the editing pane.
3. Take one or more of the following actions:

    1. To change the name of a category, select **Edit display name** and enter a new name.
    2. To edit a category, select **Edit category**, and then modify its name and description as needed.
    3. To edit, add, or remove a group, in the **Groups** section, select **Edit**, **Delete**, or **Add group**.
4. Select **Save**.

## Use catalog groups with Restricted Content Discovery

Organizations often need to apply [Restricted Content Discovery](restricted-content-discovery) across large groups of sites during a Copilot deployment or other governance initiatives. You can apply Restricted Content Discovery to collections of sites instead of configuring sites individually. You can also remove Restricted Content Discovery from a group of sites.

Note

There's a limit of 20,000 sites with Restricted Content Discovery in catalog management. That limit doesn't apply to Restricted Content Discovery at the tenant/service level.

Bulk operations retain existing Restricted Content Discovery behavior.

- Restricted Content Discovery remains a site-level property.
- Sites that already have Restricted Content Discovery enabled aren't modified.
- Existing permissions remain unchanged.
- Standard propagation behavior continues to apply.

Because Restricted Content Discovery must propagate across indexing systems, updates can take time to become fully effective. The amount of time depends on site size, the number of files in each site, and the number of concurrent updates being processed.

### Apply Restricted Content Discovery to a group of sites

1. In the SharePoint admin center, in the navigation pane, go to **Reports** &gt; **Catalog management**. Then select the **Actions** tab.

    [![Screenshot showing the Actions tab in Catalog Management.](sharepointonline/media/catalog-management/catalog-management-actions-tab.png)](sharepointonline/media/catalog-management/catalog-management-actions-tab.png#lightbox)

    If you didn't already set up Restricted Content Discovery, select the **Set up** button to do that.
2. Select a category to open the Restricted Content Discovery panel. If you didn't apply Restricted Content Discovery to any groups yet, select **Add from existing catalog group**.

    [![Screenshot showing the Restricted Content Discovery panel with no groups listed yet.](sharepointonline/media/catalog-management/restricted-content-discovery-no-groups-yet.png)](sharepointonline/media/catalog-management/restricted-content-discovery-no-groups-yet.png#lightbox)
3. Review the information shown in the panel. You can see:

    - How many sites have Restricted Content Discovery applied. This number changes in real time as soon as you select or remove groups.
    - A list of groups in the selected category that have Restricted Content Discovery applied.

    [![Screenshot showing the Restricted Content DIscovery panel.](sharepointonline/media/catalog-management/restricted-content-discovery-panel.png)](sharepointonline/media/catalog-management/restricted-content-discovery-panel.png#lightbox)
4. At the bottom of the panel, select **+ Add sites from a catalog group**.
5. Use the drop-down menu to select a group.
6. Select **Save**, and then confirm your changes.

### Snapshots and subsequent changes to groups

When you add a catalog roup to Restricted Content Discovery, you're adding a snapshot of that group at that point in time. If sites are added or removed from that group, no changes are made to Restricted Content Discovery.

For example, suppose a group is added to Restricted Content Discovery. When it was added, the group had ten sites. Now suppose three more sites are added to the group. In this case, Restricted Content Discovery is applied to the first ten sites, but not to the three new sites yet.

If changes occur to a group, such as sites are added or deleted, and you want to update Restricted Content Discovery application, follow these steps:

1. In the SharePoint admin center, in the navigation pane, go to **Reports** &gt; **Catalog management**.
2. On the **Actions** tab, select a category to open the Restricted Content Discovery panel.
3. In panel, in the list of groups, select the group, and then select **Remove**.
4. Re-add the group that you just removed.
5. Select **Save**, and then confirm your changes.

### Remove Restricted Content Discovery from multiple sites

1. In the SharePoint admin center, in the navigation pane, go to **Reports** &gt; **Catalog management**.
2. On the **Actions** tab, select a category to open the Restricted Content Discovery panel.
3. In the information shown in the panel, select the group you want to remove from Restricted Content Discovery.
4. Select **Remove**.
5. Select **Save**, and then confirm your changes.

### Restricted Content Discovery states in catalog management

After you apply or remove Restricted Content Discovery to or from a group, expect to see one of the following states in the status column:

- **Completed**: Restricted Content Discovery is applied to sites in the catalog group.
- **Processing**: Changes are still rolling out. The processing time varies depending on the number of files in the sites.
- **Adding sites**: Restricted Content Discovery is being added to sites in the category group.
- **Removing sites**: Restricted Content Discovery is being removed from sites in the category group.
- **Check site report**: Download the site list to see status for each site.
- **Error**: An error occurred during processing.

## Integration with the SharePoint Admin Agent

Catalog management provides structure that improves the effectiveness of the SharePoint Admin Agent. When you categorize sites, the SharePoint Admin Agent can provide more targeted insights, analysis, and governance recommendations based on how content is organized across your tenant. For more information, see [SharePoint Admin Agent](content-governance-agent).