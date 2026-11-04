---
layout: Conceptual
title: How to Enable Enterprise Brand Images with PowerPoint Copilot - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/enable-enterprise-brand-images-powerpoint-copilot
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
description: Self-Serve Setup Guide for Enterprise Customers to enable Brand Images with PowerPoint Copilot
author: EH560
ms.author: eleanl
manager: yvhsieh
ms.service: sharepoint-online
ms.topic: how-to
ms.date: 2026-06-26T00:00:00.0000000Z
locale: en-us
document_id: d5494473-1ecf-846f-37f9-e6bc641cacf5
document_version_independent_id: 754cfb8b-dce8-9806-15f6-37b45d35d6c2
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/enable-enterprise-brand-images-powerpoint-copilot.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: enable-enterprise-brand-images-powerpoint-copilot
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/enable-enterprise-brand-images-powerpoint-copilot.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: d8283208-2eb2-d0c0-0ea7-7c0125f152f0
---

# How to Enable Enterprise Brand Images with PowerPoint Copilot - SharePoint in Microsoft 365 | Microsoft Learn

Copilot in PowerPoint can now create on-brand presentations using your company-approved images stored in Brand Kit in Microsoft 365. Here’s how you can set up Copilot in PowerPoint to use your brand images.

### Option 1: Brand Kit in Microsoft 365.

Copilot in PowerPoint can create on-brand presentations using images from your organization's Brand Kits.

**Steps to Enable:**

1. Ensure your Brand Kit contains a significant image set (ideally 1,000+ images) to achieve the best results in Copilot scenarios.
2. Publish your organization's Brand Kit to make approved brand assets available to users. Learn how to create and publish in, [Create and manage official Brand Kits in the Microsoft Copilot app](https://support.microsoft.com/Microsoft-365-Copilot/create-and-manage-official-brand-kits-in-the-microsoft-365-copilot-app).
3. A user in your organization can then include branded images from Brand Kit when creating or editing presentations with Copilot in PowerPoint.

### Option 2: SharePoint Organizational Asset Library (OAL)

If your organization stores approved images in a SharePoint Organizational Asset Library (OAL), you can link those images to a Brand Kit in Microsoft 365. Once connected, users can access those assets through Brand Kits when creating presentations with Copilot in PowerPoint.

### Option 3: Templafy Image Library

If your organization stores approved images in Templafy, you can link those images to a Brand Kit in Microsoft 365. Once connected, users can access those assets through Brand Kits when creating presentations with Copilot in PowerPoint.

Note: Your administrator should enable the Microsoft [Graph Connector for Templafy](https://support.templafy.com/hc/articles/24656260075549-How-to-enable-Microsoft-Graph-Connector-for-Templafy-Image-Library) in order to be able to link Images from Templafy in Brand Kit.

### Tips for Success

- Use Copilot to generate [on-brand presentations](https://support.microsoft.com/topic/keep-your-presentation-on-brand-with-copilot-046c23d5-012e-49e0-8579-fe49302959fc). To use images from your organization's Brand Kit, select the + button in the Copilot prompt box, then choose Select brand and pick the desired Brand Kit. Copilot will use brand assets from the selected Brand Kit when creating your presentation.
- Ensure your Brand Kit image asset library contains at least 1,000 brand-approved images with robust metadata (name, description, and tags) to improve Copilot’s ability to retrieve relevant visuals.
- To further enhance image relevancy, consider expanding the quantity of images provided to Copilot and refining your image tags to optimize search results.

### Related Articles

- [Keep your presentation on-brand with Copilot - Microsoft Support](https://support.microsoft.com/en-gb/topic/keep-your-presentation-on-brand-with-copilot-046c23d5-012e-49e0-8579-fe49302959fc)

#### Templafy Connector

- [About the Templafy connector](/en-us/microsoftsearch/connectors-gallery)
- [How to Enable Microsoft Graph connector for Templafy Image Library](https://support.templafy.com/hc/articles/24656260075549-How-to-enable-Microsoft-Graph-Connector-for-Templafy-Image-Library) for administrators
- [How to include branded images from Templafy when creating presentations with Copilot](https://support.templafy.com/hc/articles/29041436032413-How-to-include-branded-images-from-Templafy-when-creating-presentations-with-Copilot) for users in your organization