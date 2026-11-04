---
layout: Conceptual
title: Conditional Access policy - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/authentication-context-example
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
ms.date: 2026-07-28T00:00:00.0000000Z
ms.reviewer: samust
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
f1.keywords:
- CSH
ms.topic: article
ms.custom:
- Adm_O365
ms.service: sharepoint-online
ms.subservice: admin
ms.localizationpriority: medium
ms.collection:
- Highpri
- Tier2
- M365-sam
- M365-collaboration
search.appverid:
- MET150
description: Learn about how to use Microsoft Entra Conditional Access and authentication context with SharePoint sites and sensitivity labels.
locale: en-us
document_id: 0333d571-acdd-5efb-f22f-6c75822ce12c
document_version_independent_id: e7e2d85d-053e-164f-4ddd-675c5ccc97f4
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/authentication-context-example.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: authentication-context-example
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/authentication-context-example.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
platformId: cc176718-3fe2-d5da-eae1-42499621ad26
---

# Conditional Access policy - SharePoint in Microsoft 365 | Microsoft Learn

By using [Microsoft Entra authentication context](/en-us/azure/active-directory/conditional-access/concept-conditional-access-cloud-apps#configure-authentication-contexts), you can enforce more stringent access conditions when users access SharePoint sites.

Use authentication contexts to connect an [Microsoft Entra Conditional Access policy](/en-us/azure/active-directory/conditional-access/overview) to a SharePoint site. You can apply policies directly to the site or apply them through a sensitivity label.

You can't apply this capability to the root site in SharePoint (for example, https://contoso.sharepoint.com).

[![Screenshot of conditional access policy dashboard.](sharepointonline/media/sam-overview/8-conditional-access-policies.png)](sharepointonline/media/sam-overview/8-conditional-access-policies.png#lightbox)

## Before you begin

Review the [SharePoint Advanced Management prerequisites](sharepoint-advanced-management-prerequisites).

In addition, you need one of the following licenses:

- Microsoft 365 E5/A5 Compliance
- Microsoft 365 E5 Information Protection and Governance

## Limitations

Some apps don't work with authentication contexts. Test apps on a site with authentication context enabled before broadly deploying this feature.

The following apps and scenarios don't work with authentication contexts:

- Older versions of Office apps (see the [list of supported versions](/en-us/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#more-information-about-the-dependencies-for-the-authentication-context-option))
- SharePoint mobile apps (iOS and Android)
- Viva Engage
- You can't add the OneNote app to a channel if the associated SharePoint site has an authentication context.
- Teams channel meeting recording upload fails on sites with an authentication context.
- SharePoint folder renaming in Teams fails if the site has an authentication context.
- Teams webinar scheduling fails if OneDrive has an authentication context.
- The OneDrive sync app won't sync sites with an authentication context.
- Associating an authentication context to the enterprise application catalog site collection isn't supported.
- The "Visualize SharePoint List in Power BI" feature doesn't currently support authentication context.
- Outlook on Windows, Mac, Android, and iOS don't support communication with SharePoint sites protected by an Authentication Context.
- The multiple-file download feature currently doesn't function when both the authentication context and 'Use Conditional Access App Control' in session control are enabled in the conditional access policy.
- The multiple-file download feature won't work if an authentication context is set directly on a SharePoint site without an active Conditional Access policy using that context, or if the policy exists but is disabled.
- The file copy and move feature between different regions (cross-geo) currently doesn't function when an authentication context is applied to the destination site.
- Exporting to Excel as an Excel Web Query (IQY) doesn't currently support authentication context.
- Recording or running a script using Office Scripts in Excel for the Web fails if OneDrive has an authentication context.

## Set up an authentication context

To set up an authentication context for labeled sites, complete these basic steps:

1. Add an authentication context in Microsoft Entra ID.
2. Create a Conditional Access policy that applies to that authentication context and has the conditions and access controls that you want to use.
3. Do one of the following steps:

    1. Set a sensitivity label to apply the authentication context to labeled sites.
    2. Apply the authentication context directly to a site.

In this article, you see the example of requiring guests to agree to a [terms of use](/en-us/azure/active-directory/conditional-access/terms-of-use) before gaining access to a sensitive SharePoint site. You can also use any of the other conditional access conditions and access controls that you might need for your organization.

### Add an authentication context

First, add an authentication context in Microsoft Entra ID.

To add an authentication context:

1. In [Microsoft Entra Conditional Access](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade), under **Manage**, select **Authentication context**.
2. Select **New authentication context**.
3. Type a name and description, and select the **Publish to apps** check box.

    ![Screenshot of add authentication context UI](sharepointonline/media/aad-add-authentication-context.png)
4. Select **Save**.

### Create a Conditional Access policy

Next, create a Conditional Access policy that applies to that authentication context and requires guests to agree to terms of use as a condition of access.

To create a Conditional Access policy:

1. In [Microsoft Entra Conditional Access](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade), select **New policy**.
2. Enter a name for the policy.
3. On the **Users and groups** tab, choose the **Select users and groups** option, and then select the **Guest or external users** check box.
4. Choose **B2B collaboration guest users** from the dropdown.
5. On the **Cloud apps or actions** tab, under **Select what this policy applies to**, choose **Authentication context**, and select the check box for the authentication context that you created.

    ![Screenshot of authentication context options in cloud apps or actions settings for a conditional access policy.](sharepointonline/media/aad-authentication-context-ca-policy-apps.png)
6. On the **Grant** tab, select the check box for the terms of use that you want to use, and then select **Select**.
7. Choose if you want to enable the policy, and then select **Create**.

### Apply the authentication context directly to a site

You can directly apply an authentication context to a SharePoint site by using the [Set-SPOSite](/en-us/powershell/module/sharepoint-online/set-sposite) PowerShell cmdlet.

Note

This capability requires a Microsoft 365 E5 or Microsoft SharePoint Advanced Management license.

In the following example, you apply the authentication context you created earlier to a site called "research."

```powershell
Set-SPOSite -Identity https://contoso.sharepoint.com/sites/research -ConditionalAccessPolicy AuthenticationContext -AuthenticationContextName "Sensitive information - guest terms of use"
```

### Set a sensitivity label to apply the authentication context to labeled sites

If you want to use a sensitivity label to apply the authentication context, update a sensitivity label (or create a new one) to use the authentication context.

Note

Sensitivity labels require Microsoft 365 E5 or Microsoft 365 E3 plus the Advanced Compliance license.

To update a sensitivity label

1. In the [Microsoft Purview portal](https://purview.microsoft.com/informationprotection), on the **Information protection** tab, select the label that you want to update and then select **Edit label**.
2. Select **Next** until you are on the **Define protection settings for groups and sites** page.
3. Ensure that the **External sharing and Conditional Access settings** check box is selected, and then select **Next**.
4. On the **Define external sharing and device access settings page**, select the **Use Microsoft Entra Conditional Access to protect labeled SharePoint sites** check box.
5. Select the **Choose an existing authentication context** option.
6. In the dropdown list, choose the authentication context that you want to use.

    ![Screenshot of Microsoft Entra authentication context sensitivity label settings](sharepointonline/media/aad-authentication-context-label-setting.png)
7. Select **Next** until you are on the **Review your settings and finish** page, and then select **Save label**.

After you update the label, guests accessing a SharePoint site (or the **Files** tab in a team) with that label must agree to the terms of use before gaining access to that site.

## Block background apps

If you set authentication context on a site, admins can choose to prevent background apps from accessing that site for the apps assigned with that authentication context in a Conditional Access policy. You can configure a Conditional Access policy such that a specific authentication context can be assigned to chosen application principals (non-Microsoft applications). You need to explicitly turn on this feature by using the following cmdlet. You should have at least one Conditional Access policy with an application principal configured.

```PowerShell
Set-SPOTenant -BlockAppAccessWithAuthenticationContext $false/$true (default false)
```

## Third-party app integration

Third-party apps that use sites with authentication context attached need to be able to handle claims challenge. See [Developer guide to Conditional Access authentication context](/en-us/entra/identity-platform/developer-guide-conditional-access-authentication-context).