---
layout: Conceptual
title: Deprecation of Classic SharePoint Pages - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/classic-user-created-page-deprecation
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
description: Guidance for customers regarding retirement of classic SharePoint pages.
author: shiongzuo
ms.author: jihongzuo
manager: liangz
ms.date: 2026-08-24T00:00:00.0000000Z
ms.topic: upgrade-and-migration-article
ms.service: sharepoint-online
ms.subservice: sites-pages
locale: en-us
document_id: c725a8cb-998e-9b41-de87-8ff2fe67c64c
document_version_independent_id: 55cddaa0-5855-685b-7b4e-4caec26230e3
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/classic-user-created-page-deprecation.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: classic-user-created-page-deprecation
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/classic-user-created-page-deprecation.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: afcb9050-ad77-9984-0c3c-d99c2192c1de
---

# Deprecation of Classic SharePoint Pages - SharePoint in Microsoft 365 | Microsoft Learn

Microsoft SharePoint continues to evolve to help organizations create and manage content more securely, easily and intelligently. As part of this evolution, new changes will be introduced to classic publishing sites, classic user-created pages, and custom scripting in SharePoint Online to reduce security and governance risks associated with legacy customization models, and help organizations move to more secure, manageable, and mobile-ready [modern SharePoint experiences](guide-to-sharepoint-modern-experience).

The change rollout begins on March 1, 2027, and continues on October 1, 2028. Start assessing your environment and planning modernization now.

Important

These changes don't delete or modify existing classic page content. Affected pages remain available for viewing but become read-only when the applicable phase takes effect.

## Rollout timeline

### Phase 1 — Beginning March 1, 2027

#### Changes for all tenants

- Creation of new classic publishing sites will be disabled for both site collections and subsites.
- Activation of classic publishing feature will be disabled for both site collections and subsites.
- The `AllowClassicPublishingSiteCreation` tenant setting will be enforced as `False` and cannot be changed.

#### Additional changes for new tenants created on or after March 1, 2027

- Users can no longer create new classic pages.
- The ability to add or update custom scripts will be disabled by default.
- The `DenyAddAndCustomizePages` site setting will be enforced as `True` and cannot be changed.

### Phase 2 — Beginning October 1, 2028

The Phase 1 page and scripting restrictions will extend to all remaining existing tenants:

- Classic user-created pages become read-only. Users can no longer create or edit classic pages.
- The ability to add or update custom scripts will be disabled by default.
- The `DenyAddAndCustomizePages` site setting will be enforced as `True` and cannot be changed.

Important

Existing classic user-created pages will remain accessible for viewing in a read-only form after Phase 2.

### Classic user-created pages in scope

The read-only change applies to:

- Wiki pages
- Web Part pages
- Blog pages
- Publishing pages
- Custom ASPX pages created by using SharePoint Designer or third-party solutions

Other classic experiences, including list and library views and list form pages, aren't in the current scope. However, custom scripts embedded in those experiences are subject to the changes to custom script creation and updates.

### Cloud environments in scope

The changes to classic user-created pages apply across all Microsoft 365 environments, including:

- Microsoft 365 Government (GCC, GCC High, and DoD)
- Office 365 air-gapped cloud environments
- Microsoft 365 operated by 21Vianet

## Why this change is happening

Classic pages and legacy customization models rely on server-side rendering and custom scripting. These technologies can increase security risk, administrative complexity, and maintenance costs. They also limit the consistency, manageability, and pace of innovation available with modern experiences.

Modern SharePoint provides:

- More secure and well-governed collaboration environments
- A foundation for current and future AI-powered experiences
- Mobile-ready experiences
- Easier administration and long-term maintenance

## What you should do now

Use a phased approach to reduce migration risk and give site owners time to validate modernized pages.

### 1. Discover and assess your classic environment

Identify active classic sites and pages across your tenant.

- Use the Microsoft Purview Audit `SharePoint Classic Activities` category and the `ClassicPageCreated`, `ClassicPageEdited`, and `ClassicPageViewed` events to understand current usage.
- Run the [Microsoft 365 Assessment Tool](https://aka.ms/microsoft365assessmenttool) to identify classic pages, Web Parts, customization patterns, and modernization feasibility.
- Review the [requirements for the classic pages assessment](/en-us/sharepoint/dev/transform/assessment-tool-classic-pages-requirements) before collecting usage data.

If your assessment finds no classic publishing sites, classic user-created pages, or affected custom scripts, no action is required for these changes.

### 2. Prioritize by business importance and usage

Start with frequently edited, high-traffic, or business-critical pages. Group pages by complexity and modernization pattern so you can migrate representative waves and reuse what you learn.

### 3. Transform pages to modern SharePoint experiences

Use the [classic page transformation guidance](/en-us/sharepoint/dev/transform/modernize-userinterface-site-pages) and PnP PowerShell for deterministic page transformation. Validate each generated page before expanding to a larger wave.

For complex pages with custom HTML, script editor content, or layouts that need human judgment, evaluate the open-source [SharePoint Page Migration Agent (preview)](https://github.com/pnp/SharePointPageModernizationAgent). Preview and community tools might not fully automate complex scenarios and don't have a Microsoft support SLA. Highly customized pages can require redesign or manual rebuilding.

**Video: Demo on transforming classic SharePoint pages with agents**

The following video shows how SharePoint Page Migration Agent assists with migrating classic SharePoint pages:

### 4. Modernize in waves

Combine centralized planning and prioritization with execution by site owners. A wave-based migration makes it easier to validate content, links, permissions, Web Parts, and page layout before expanding the migration.

## Frequently asked questions

### What happens to my existing classic sites?

Existing classic sites remain available. These changes don't modify or delete classic page content. You can modernize many classic sites in place rather than rebuild them from scratch. For guidance, see [Modernize your classic SharePoint sites](/en-us/sharepoint/dev/transform/modernize-classic-sites).

### What happens to classic pages that I don't modernize?

For tenants created on or after March 1, 2027, classic user-created pages are read-only by default beginning on that date. For all remaining existing tenants, classic user-created pages that haven't been modernized become read-only beginning October 1, 2028. Users can continue to open and view the pages, but they can't edit them or create new classic user-created pages. Modernize pages that must remain editable after the applicable date.

### Can I create classic publishing sites in the future?

Beginning March 1, 2027, you can't create site collections or subsites that use the following publishing-related templates. Other classic templates aren't affected by this change.

| Template ID | Template |
| --- | --- |
| `BLANKINTERNETCONTAINER#0` | Publishing Portal Site |
| `CMSPUBLISHING#0` | Publishing Site |
| `BLANKINTERNET#0` | Publishing Site Blank |
| `ENTERWIKI#0` | Enterprise Wiki |
| `SRCHCEN#0` | Enterprise Search Center |
| `SPSSITES#0` | Site Directory |
| `SPSNHOME#0` | News Home Site |
| `PRODUCTCATALOG#0` | Product Catalog |
| `SPSREPORTCENTER#0` | Report Center |
| `SPSTOPIC#0` | Topic Area Template |

### Can I migrate classic sites and pages from SharePoint Server to SharePoint Online?

Beginning March 1, 2027, classic publishing sites can't be migrated as-is to a newly created classic publishing site in SharePoint Online because creation of those sites is disabled.

Classic user-created pages can still be migrated, but they become read-only in SharePoint Online when the applicable phase takes effect. Script-based page elements and other customizations might not be preserved. Plan to modernize these pages as part of the migration.

### Are other classic pages affected?

No. The page read-only change applies only to the classic user-created page types listed in this article. List and library views, list form pages, and other classic experiences aren't in the current scope and might be addressed on a separate timeline. Custom scripts embedded in those experiences are still subject to the custom scripting changes.

## Related resources

- [Guide to the modern experience in SharePoint](guide-to-sharepoint-modern-experience)
- [Allow or prevent custom scripts in SharePoint sites](allow-or-prevent-custom-script)
- [Modernize your classic SharePoint sites](/en-us/sharepoint/dev/transform/modernize-classic-sites)
- [Transform classic SharePoint pages to modern pages](/en-us/sharepoint/dev/transform/modernize-userinterface-site-pages)
- [Microsoft 365 Assessment Tool](https://aka.ms/microsoft365assessmenttool)