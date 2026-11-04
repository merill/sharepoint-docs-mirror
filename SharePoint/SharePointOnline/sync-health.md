---
layout: Conceptual
title: OneDrive sync reports in the Apps Admin Center - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/sync-health
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-09-16T00:00:00.0000000Z
ms.reviewer: kangan
ms.author: v-mactran
author: MachelleTranMSFT
manager: jtremper
audience: Admin
f1.keywords:
- NOCSH
ms.topic: article
ms.service: onedrive
ms.localizationpriority: medium
ms.collection:
- Strat_OD_admin
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- onedrive-toc
search.appverid:
- ODB160
- ODB150
- GOB150
- GOB160
- MET150
ms.assetid: e1b3963c-7c6c-4694-9f2f-fb8005d9ef12
description: Learn how to proactively monitor OneDrive health, devices, and usage across an organization using the OneDrive sync reports.
locale: en-us
document_id: 9f65565e-e318-a6d3-2216-b81243b753f3
document_version_independent_id: 905fabb5-f3cb-0dd4-af58-f785a45002a5
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/sync-health.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: sync-health
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/sync-health.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
platformId: 6eeba776-91b8-c0ea-e770-4ba1eb021682
---

# OneDrive sync reports in the Apps Admin Center - SharePoint in Microsoft 365 | Microsoft Learn

Use the OneDrive sync health dashboard in the Microsoft 365 [Apps Admin Center](https://config.office.com/) to get an executive summary of everything happening with OneDrive so that you can resolve common issues quickly and focus on other strategic tasks as an administrator.

Proactively keeping OneDrive healthy helps ensure that your organization's information is protected. The dashboard provides you with sync health reports for tracking relevant health issues and advisories, checking the sync status and app version of individual devices, and monitoring Known Folder Move roll out.

In this article, you learn how to set up and navigate the sync health dashboard to better manage your OneDrive users and increase OneDrive adoption.

## Requirements

Before getting started, be sure that you're familiar with the requirements needed to access the dashboard:

- OneDrive sync app version 22.232 or later for Windows and macOS.
- OneDrive sync apps on the Insiders, Production, or Deferred ring. [Set the sync app update ring](use-group-policy#set-the-sync-app-update-ring).
- [Office Apps Administrator](/en-us/microsoft-365/admin/add-users/about-admin-roles) or Microsoft 365 Administrator role access is required to enable and set up the dashboard for your organization. After the feature is enabled by one of these roles, one can also view the dashboard using [Global Reader](/en-us/microsoft-365/admin/add-users/about-admin-roles), Security Administrator, Office Apps Administrator, or Reports Reader access. To learn more about administrator roles and permissions in Microsoft 365, visit [About Admin Roles](/en-us/microsoft-365/admin/add-users/about-admin-roles).
- Devices in your organization should allow connections to `https://clients.config.office.net`.

Note

This feature isn’t available to customers who have Office 365 operated by 21Vianet.

## Set up the OneDrive sync health dashboard

In this section, you learn how to set up sync reports on Windows and macOS devices.

# [Intune](#tab/intune)
This tab provides how-to steps for enabling sync reports on Intune joined devices.

1. Ensure you have the required role and app versions listed in the previous section.
2. Go to [Microsoft 365 Apps admin center](https://config.office.com) and sign in as an Office App Administrator
3. In the left navigation menu, select **Setup**
4. Verify that a **Tenant Association Key** is present in the text field. If the field is empty, select **Generate new key**. When you generate a new key for the first time, it can take up to 30 seconds for it to appear.

    Note

    Customers who have Office 365 GCC or Office 365 GCC High and DoD do not need a **Tenant Association Key**.
5. Copy the **Tenant Association Key**
6. Go to [Intune admin center](https://intune.microsoft.com/) and sign in as an Intune Administrator.
7. From the left navigation menu, select **Devices** &gt; **Configuration**
8. Create a new policy, select **Windows 10 and later** or **macOS** for platform and **Settings catalog** for policy type.
9. Name the new policy and give it a description then select next.
10. Select **Add settings** and then navigate to **OneDrive**
11. Check the box for **Enable sync health reporting for OneDrive** and check the box for **Sync Admin Reports**
12. Under the **Sync Admin Reports** option, paste your **Tenant Association Key**
13. Select **Next** and apply your scope tags
14. Select **Next** and apply your assignments
15. Select **Create**

# [Windows](#tab/windows)
This tab provides how-to steps for enabling sync reports on Windows devices.

Note

The previous Group Policy HKLM\SOFTWARE\Policies\Microsoft\OneDrive\SyncAdminReports is no longer supported, and machines using that key will no longer appear in the sync health dashboard. Admins need to switch to the currently supported key (additional information below): HKLM\SOFTWARE\Policies\Microsoft\OneDrive\EnableSyncAdminReports.

1. Ensure you have the required role and app versions listed in the previous section.
2. Go to [Microsoft 365 Apps admin center](https://config.office.com) and sign in as an Office App Administrator.
3. From the left navigation menu, select **Health** &gt; **OneDrive Sync**.
4. In the left navigation menu, select **Setup**.
5. Verify that a **Tenant Association Key** is present in the text field. If the field is empty, select **Generate new key**. When you generate a new key for the first time, it can take up to 30 seconds for it to appear.

    Note

    Customers who have Office 365 GCC or Office 365 GCC High and DoD do not need a **Tenant Association Key**.
6. Enable the OneDrive EnableSyncAdminReports Group Policy Object (GPO).

    Important

    **You must enable this setting on the devices from which you want to get reports.** This setting doesn't affect users. We recommend a gradual rollout starting with a few test devices per day, then up to 100 devices per day, then gradually up to 10,000 devices per day until you finish.

    You can enable this setting in multiple ways:

    - Edit the registry

        a. Go to HKLM\SOFTWARE\Policies\Microsoft\OneDrive

        b. Right-click &gt; **New** &gt; **DWORD (32-bit) Value**

        c. Name: EnableSyncAdminReports

        d. Type: REG\_DWORD

        e. Data: 1

        ![Screenshot image depicting the creation of a new key in the Registry Editor](sharepointonline/media/createregkey.png)
    - Run Command Prompt as an administrator, and then run the following command:

        ```PowerShell
         reg.exe add HKLM\Software\Policies\Microsoft\OneDrive /v EnableSyncAdminReports /t REG_DWORD /d 1
        ```
    - Use [Group Policy](use-group-policy#manage-onedrive-using-group-policy).

    To apply the setting on a single PC, follow these steps:

    - Open Group Policy Editor (gpedit.msc).
    - Go to Computer Configuration\Administrative Templates\OneDrive.
    - Choose **Enable sync health reporting for OneDrive**.
    - Select **Enabled** and then press **OK**.

Important

When you enable the EnableSyncAdminReports setting on devices, it can take up to three days for reports to be available. Devices will appear in the report after this time. Forcing a specific device to report data is unsupported.

Note

OneDrive sync health reports can also be enabled using administrative templates in Intune. For more information, see [Use administrative templates in Intune](configure-sync-intune).

# [macOS](#tab/macos)
This tab provides how-to steps for enabling sync reports on macOS devices.

1. Ensure you have the required role and app versions listed in the previous section.
2. Go to the [Microsoft 365 Apps admin center](https://config.office.com) and sign in as an Office Apps Administrator.
3. From the left navigation menu, select **Health** &gt; **OneDrive Sync**.
4. In the left navigation menu, select **Setup**.
5. Verify that a **Tenant Association Key** is present in the text field. If the field is empty, select **Generate new key**. When you generate a new key for the first time, it can take up to 30 seconds for it to appear.

    Note

    Customers who have Office 365 GCC or Office 365 GCC High and DoD do not need a **Tenant Association Key**.
6. Before proceeding, ensure that the OneDrive application has been quit.
7. Create a .plist file with the key **EnableSyncAdminReports**. You can also use a script to set the key. The key is the same whether you run the standalone or Mac App Store edition of the sync app. However, the .plist file name and domain name will be different. When you apply the setting, ensure that you target the appropriate domain depending on the edition of the sync app.

| - | Standalone | Mac App Store |
| --- | --- | --- |
| **.plist location ** | /Library/Preferences/com.microsoft.OneDrive.plist | /Library/Containers/com.microsoft.OneDrive-mac/Data/Library/Preferences/com.microsoft.OneDrive-mac.plist |
| **Domain ** | com.microsoft.OneDrive | com.microsoft.OneDrive-mac |

1. Use the Terminal app to deploy the EnableSyncAdminReports setting onto your local computer.

    Enter the following preference key to enable the setting: &lt;key&gt;EnableSyncAdminReports&lt;/key&gt; &lt;integer&gt;1&lt;/integer&gt;
2. Refresh the preferences cache.
3. On the next start of OneDrive, the new setting will be picked up.

Important

After you enable the EnableSyncAdminReports setting on devices, it takes up to three days for reports to be available.

---

## Navigate the OneDrive Sync health dashboard

In this section, you'll learn how to successfully navigate the OneDrive Sync health dashboard. Learn about the reporting insights available to you and how they can help you proactively manage OneDrive for your organization.

Jump to:

- Overview
- Devices
- Issues
- Export data for custom reporting

Note

After you set up the dashboard as described in the previous section, the Global Reader admin role is sufficient to access and view reports.

### Overview

The **Overview** tab (the default view) shows a summary of devices that have at least one sync issue, a percentage of the devices in your organization using [Known folder move](redirect-known-folders), and the number of devices running on the current version of OneDrive.

| Card name | Description |
| --- | --- |
| Sync errors | *Shows how many devices have sync errors or not.* Sorting through errors can help you proactively reach out to educate people while resolving common issues and improving user experience. Users may not report OneDrive issues to you immediately. Unreported issues could lead to unwanted problems while they're working on important tasks. With the **Sync errors** card, you won't have to wait to be notified by users to take action. |
| Known folders | *Shows a snapshot of the number of known folders currently in use.***Known Folder Move** allows people to keep their Desktop, Documents, and Pictures folders protected by syncing them to the cloud with OneDrive. If you’re rolling out Known Folder Move for your organization, the **Known folders** card is a great way for you to monitor progress. |
| Sync app version | *Shows the number of devices running on the current version of OneDrive.* Running the current version of OneDrive helps users stay up to date with all the latest and greatest fixes and features from Microsoft. Hover over the **Sync app version** card for a filtered view of operating systems on the current version. Note: Mac App store devices are excluded from this section and will appear in the count as "devices excluded". |
|  |  |

### Devices

The **Devices** tab shows all users, their current health state, their known folders currently moved in OneDrive, their current app version and operating system version, a timestamp of the last time the app was fully up to date, and a timestamp of the last time the sync app reported health data to the dashboard. The last status reported timestamp (UTC) is updated every ~36 hours, or ~1 hour after the client starts up. An icon and status in the **Errors** column indicate the state of each device.

This table provides a summary of the information found in each column of the **Devices** tab:

| Column name | Description |
| --- | --- |
| User | The name of the user |
| User email | The user's email address |
| Device name | The device name |
| Errors | The health status of a device |
| Known folders | The name of folders moved to OneDrive |
| App version | The current version of OneDrive running on the device |
| Operating system | The current version of the OS running on the device |
| Last synced timestamp (UTC) | The last time that the sync app was fully up to date with the cloud |
| Last status reported timestamp (UTC) | The last time that the sync app reported health data to the dashboard |
|  |  |

Customize your view of which devices show up on the dashboard by using the filter option in the command bar. Standard filters include "all devices" where you can see every device and "devices with errors" where you'll only see devices with errors.

You can easily create a custom filter with your own conditions. From the command bar, select **Filter** &gt; **New filter** to open the **Custom filter** panel. Name your filter and select your desired conditions. If you'd like to filter by app version, be sure that you enter the complete sync app version number including periods. Afterwards, select **Create** to use your new filter.

When someone in your organization reports a problem with syncing files to OneDrive, you can investigate quickly without having to ask for extra details of the error message via Microsoft Teams chat or Outlook email. Select a user to see more information on their device and sync status. This detailed view lets you see a user's essential OneDrive information including any errors they might be experiencing.

### Issues

The **Issues** tab shows you a list of OneDrive error messages found in the health report and the number of devices affected by them in your organization. Use this view to see if there are any common patterns between users and the errors present across your organization.

You can learn more about the error and devices affected by selecting an error message from the list. The **Issues** panel appears with a summary of the devices affected, along with a list of users and their current app version and operating system. Partner with your users to fix common OneDrive sync issues.

To learn more about OneDrive error messages, see [What do the OneDrive error codes mean?](https://support.microsoft.com/office/what-do-the-onedrive-error-codes-mean-f7a68338-e540-4ebf-ad5d-56c5633acded).

## Export sync health data for custom reporting

Use the dashboard for day-to-day monitoring and troubleshooting. If you need to retain data, build custom reports, or combine sync health data with other organizational data, use Microsoft Graph Data Connect to copy the data to a supported destination that you manage.

Microsoft Graph Data Connect provides the following OneDrive datasets:

- `BasicDataSet_v0.OneDriveSyncHealth_v1` contains information about report-enabled devices, including the user, device, operating system, sync app version, update ring, Known Folder Move status, error count, and last-synced and last-status-reported timestamps.
- `BasicDataSet_v0.OneDriveSyncErrors_v1` contains details about sync errors. Join this dataset with the sync health dataset by using the `OneDriveDeviceId` property.

For the complete schemas, see [Microsoft Graph Data Connect datasets](/en-us/graph/data-connect-datasets#onedrive-and-sharepoint-online).

Important

Sync health data can include user and device information. Before you export data, plan how you'll restrict access, apply your organization's retention requirements, and monitor the Azure resources that store and process the data. Microsoft Graph Data Connect and the Azure services used by your pipeline can incur charges.

### Before you begin

Make sure that:

- You've set up the OneDrive sync health dashboard. Only devices that have sync health reporting enabled are included in the dataset.
- Your Microsoft 365 tenant and Azure subscription are in the same Microsoft Entra tenant.
- You have a Global Administrator to enable Microsoft Graph Data Connect and approve the application.
- A different user has the Application Administrator or Application Developer role to register the application. The user who registers the application can't also approve it.
- The user who creates the Azure resources has sufficient permissions in the Azure subscription to create the selected compute and destination resources and assign the required roles.
- Your Azure storage and compute resources are in a [region supported for your Microsoft 365 data location](/en-us/graph/data-connect-datasets#regions).
- If your organization uses Microsoft 365 Multi-Geo, you plan a separate pipeline for each region that you need to extract. A single pipeline can't extract data from multiple Microsoft 365 regions.

### Configure Microsoft Graph Data Connect

1. Follow [Build your first Microsoft Graph Data Connect application](/en-us/graph/data-connect-quickstart) to:

    - Enable Microsoft Graph Data Connect in the Microsoft 365 admin center.
    - Register a single-tenant Microsoft Entra application.
    - Create the compute and destination resources for your pipeline.
    - Assign the application the permissions required for the selected destination. For Azure Blob Storage or Azure Data Lake Storage Gen2, assign the **Storage Blob Data Contributor** role.
2. In the Microsoft Graph Data Connect registration wizard in the Azure portal, select the compute type, activity type, and destination that you intend to use. Make sure that the destination URI and the pipeline linked service match. For example, use an Azure Data Lake Storage Gen2 linked service for a DFS URI and an Azure Blob Storage linked service for a blob URI.

    Add `BasicDataSet_v0.OneDriveSyncHealth_v1`. Add `BasicDataSet_v0.OneDriveSyncErrors_v1` if you need detailed error information. Select only the columns required for your reporting scenario.
3. Ask the Global Administrator to approve the application:

    1. In the [Microsoft 365 admin center](https://admin.microsoft.com), go to **Settings** &gt; **Org settings**.
    2. On the **Security & privacy** tab, select **Microsoft Graph Data Connect applications**.
    3. Select the application, review its datasets, columns, and destination, and then select **Approve**.
4. Create a pipeline by using Microsoft Fabric, Azure Synapse, or Azure Data Factory. Select a compute, activity, and destination combination supported by Microsoft Graph Data Connect, and make sure that the choices match the application registration. Configure:

    - **Source:** Microsoft 365 (Office 365).
    - **Dataset:**`BasicDataSet_v0.OneDriveSyncHealth_v1` and, if needed, `BasicDataSet_v0.OneDriveSyncErrors_v1`.
    - **Sink:** A [supported Azure storage destination](/en-us/graph/data-connect-datasets#sinks).
    - **Authentication:** The service principal for the approved Microsoft Entra application.

    For detailed pipeline instructions, see [Set up your pipeline resource](/en-us/graph/data-connect-quickstart#set-up-your-azure-resource-with-azure-synapse-or-azure-data-factory).
5. Validate and publish the pipeline, and then run it. Monitor the pipeline until its status is **Succeeded**, and verify that the output is available in your storage destination.

For copy activities, Microsoft Graph Data Connect writes JSON output. The sync health dataset captures daily records and doesn't support delta extraction. The sync errors dataset covers the preceding 30 days and also doesn't support delta extraction. For recurring runs, write each extraction to a run-specific path and account for overlapping records when you build historical reports.

### Analyze the exported data

You can use Power BI or another analytics tool that can read the destination used by your pipeline. To analyze the data in Power BI:

1. In Power BI Desktop, select **Get data** and connect to the destination used by your pipeline.
2. Select or transform the output from the pipeline. For JSON output from a copy activity, exclude pipeline metadata files before combining the data files, if applicable.
3. Use fields such as `SyncAppVersion`, `OSName`, `LastSyncedTimestampUTC`, and `KFMEnabledFolders` to create the views required by your organization.
4. If you exported both datasets for a single reporting period, relate the sync health and sync errors data by using `OneDriveDeviceId`. If you retain multiple extractions, add the extraction date or run identifier to your model and deduplicate or filter records to the reporting period you want to analyze.

For an example of connecting Power BI to Azure Data Lake Storage Gen2, see [Analyze data in Azure Data Lake Storage Gen2 by using Power BI](/en-us/power-query/connectors/analyze-data-in-adls-gen2).

## Data for the OneDrive sync health dashboard

The sync reports use health data that your OneDrive sync apps send to Microsoft. You have choices when it comes to the technology you use and the data you share. Use the EnableSyncAdminReports setting to manage which devices send data.

To learn more about the controls available to you, see [Overview of privacy controls for Microsoft 365 Apps](/en-us/deployoffice/privacy/overview-privacy-controls). To learn more about required service data, see [Required service data for Office](/en-us/deployoffice/privacy/required-diagnostic-data).

## Known limitations and considerations

This section describes known limitations and considerations in sync reporting.

### Limitations

**Device Records:** By default, device records are kept in inventory for 30 days, after which they expire from the report.

**Folders in OneDrive:** Devices with folders in OneDrive appear in reports as a device with 0-3 known folders. If a device hasn't enabled folders in OneDrive, it appears in reports as a device that is **Not eligible** in the **Known Folders** section of the **Overview** tab. In the **Devices** tab, a hyphen ("-") will appear in the cell value of the **Known folders** table for devices that aren't applicable devices. This behavior is expected.

**Sync app version: Mac App Store edition:** For devices using the Mac App Store edition of the sync app, the version installed on each device is displayed in the **Devices** tab. The dashboard doesn't currently track whether or not the Mac App Store edition is the latest version of the sync app available in the Mac App Store. If any devices use this edition, they are excluded from the **Sync app version** section of the **Overview** tab and the number of excluded devices is displayed. This is the expected result.

**Minimum time device is on for eligibility:** Devices need to be turned on for a minimum of five hours to be eligible for the report. Devices that are turned off frequently and not on for that amount of time might be missing from the dashboard, even if the group policy is set.

**User sign-in:** Clients won't report status to the report if the user is signed out.

### Considerations

- There's negligible impact to a network after enabling the sync reports setting on devices.
- Microsoft continues its commitment to meet and exceed the requirements of EU data protection laws. All data storage is EU Data Boundary compliant.
- There are no Power BI templates available for sync reports.
- Admins see errors based on the user's client language, not in the admin's configured language.

## Troubleshooting

Use this section to troubleshoot if the OneDrive sync reports don't appear after three days.

Important

If you enable the EnableSyncAdminReports setting on devices that don't meet the requirements, it has no effect. The app won't send reports.

Confirm that the EnableSyncAdminReports setting is applied to the device. Run Command Prompt as an administrator, and then run the following command:

```PowerShell
reg.exe query HKLM\Software\Policies\Microsoft\OneDrive /v EnableSyncAdminReports
```

The output should look like this:

![Screenshot of expected command prompt output.](sharepointonline/media/syncregkeyquery.png)

If the EnableSyncAdminReports setting wasn't applied, go back and follow the steps under Set up the OneDrive sync health dashboard.

If the setting was applied correctly, wait for 36 hours with the device turned on and signed in to OneDrive. If the device still doesn't appear on the dashboard, open a support ticket with Microsoft. For more information, see the next section, Report a problem.

## Report a problem

If you encounter a problem with viewing the report dashboard, first verify that you've completed the steps in the troubleshooting section.

If problems persist after troubleshooting, [open a support ticket with Microsoft](/en-us/microsoft-365/admin/contact-support-for-business-products). Make sure that the device isn't powered off during this period so that the sync app can still run and send a health report.

For quick investigations, be sure to have the date and time when the EnableSyncAdminReports setting was enabled and either the user’s email or the OneDrive device ID available in your issue report.

To get the OneDrive device ID, select the OneDrive sync app in the notification area &gt; **Help & Settings** &gt; **Settings** &gt; **About**.

## Send feedback

We value your feedback. To submit feature suggestions and report issues, you can use the Feedback button in the top-right corner of the dashboard page.

![Screenshot of Feedback form.](sharepointonline/media/sync-feedback.png)