---
layout: Conceptual
title: Automate workflows in a SharePoint document library - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/copilot-in-sharepoint-automate-workflows
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: 
ms.date: 2026-09-24T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.reviewer: jseto
ms.author: natenna
author: cjtancortex
manager: corywink
audience: Admin
f1.keywords:
- NOCSH
ROBOTS: 
ms.topic: how-to
ms.service: sharepoint-online
ms.subservice: ai-copilot
ms.collection:
- M365-collaboration
- m365copilot
ms.localizationpriority: medium
search.appverid:
- MET150
description: Learn how to use rules to automate workflows in a SharePoint document library.
locale: en-us
document_id: af0ac0da-fe1a-7279-a3c7-37db36f65f18
document_version_independent_id: f272dec9-7faa-fa1b-fd25-d8c0c77fb59c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/copilot-in-sharepoint-automate-workflows.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: copilot-in-sharepoint-automate-workflows
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/copilot-in-sharepoint-automate-workflows.md
platformId: b7390e6e-24a7-b7ed-0b60-6df3e6060124
---

# Automate workflows in a SharePoint document library - SharePoint in Microsoft 365 | Microsoft Learn

Copilot in SharePoint enables you to set up automations in your document library by describing what you want to happen using natural language. You don't need to know technical terms or navigate complex menus. Simply describe your intent and an appropriate workflow rule is suggested and configured.

## Launch the quick action

1. In the lower-right corner of your document library, select the Copilot in SharePoint icon.
2. From the **quick actions** menu, select **Set up rules**.
3. The chat panel opens and displays a list of suggested actions related to the creation of rules.

    Note

    If this is the first time using Copilot in SharePoint in the library, the system automatically generates up to three suggested columns based on the available files. These columns are auto-populated with metadata and can be useful when creating rules.

## Use a suggested prompt

1. From the chat panel, select an action. For this example, use **Send notification**.
2. In the chat box, review the instruction provided. If needed, modify the text to better suit your intent. When ready, select **Send** (![Screenshot of the send icon in the chat box.](sharepointonline/media/knowledge-agent/chat-box-send-icon.png)) to submit your action.
3. Based on your prompt, the system generates a rule. Review the rule and select **Create** to set up the rule.

    ![Screenshot of the Create a rule page.](sharepointonline/media/knowledge-agent/knowledge-agent-create-a-rule.png)
4. The chat panel summarizes the rule conditions.

    ![Create a rule from the suggested prompt](sharepointonline/media/knowledge-agent-automate-workflows/create-a-rule-from-the-suggested-prompt.jpg)

## Enter a custom prompt

1. In the chat panel's text box, enter your own automation instruction. When requesting a rule, specify the condition in which it should run and the action that should happen. This condition ensures the rule meets your needs.

    ![Create a rule for Serena Ribeiro](sharepointonline/media/knowledge-agent-automate-workflows/create-a-rule-for-serena-ribeiro.jpg)

    Tip

    You can use Copilot in SharePoint to perform four actions: email, move, copy, and set value. Here are some sample prompts:

    - Send an email (for example, "Email me when a contract is approved" or "Notify me when new files are added and the release date is in 2025")
    - Move a file (for example, "Move reviewed invoices to the Verified Expenses folder")
    - Copy a file (for example, "Copy all Northwind Traders invoices to the Northwind folder")
2. Select **Send** (![Screenshot of the send icon in the chat box.](sharepointonline/media/knowledge-agent/chat-box-send-icon.png)) to submit your prompt.
3. Based on your prompt, a rule is generated. Review the rule created and select **Create** to set up the rule.

    ![Screenshot of the Create a rule page showing the generated rule.](sharepointonline/media/knowledge-agent/knowledge-agent-generated-rule.png)
4. The chat panel summarizes the rule conditions.

    ![Create a rule for Serena Ribeiro _ in chat response](sharepointonline/media/knowledge-agent-automate-workflows/create-a-rule-for-serena-ribeiro-in-chat-reponse.jpg)

## Save your changes

1. When you're ready to save the rule you created and any other changes you made, select **Save changes**.
2. On **Save changes to library?**, confirm the changes and then select **Apply changes**.
3. You're returned to the updated library, and the rule runs automatically whenever the defined conditions are met.

    Tip

    If you want to see all of the rules in your document library, from the header select **Automate** &gt; **Rules** &gt; **Manage rules**. ![Screenshot showing the path to view all rules in your library.](sharepointonline/media/knowledge-agent/knowledge-agent-rules-path.png)

## Requirements and limitations

- **Supported rule triggers**: A new item is created, an item is modified, or an item is deleted.
- **Supported rule actions**: Email, move, copy, and set value.
- **Supported languages**: All languages supported through [Microsoft Copilot](https://support.microsoft.com/topic/26de43a1-c176-4908-bef7-29c8c37ac7ce) for text-based prompts and responses, but it can only process files in English.
- **Limitations**:

    - Encrypted files can't be analyzed to run rules.
    - The "date approaches" trigger for rules isn't yet supported by Copilot in SharePoint.
    - The translate and delete rule actions aren't yet supported by Copilot in SharePoint. Organizations with [pay-as-you-go billing](/en-us/microsoft-365/documentprocessing/syntex-azure-billing) set up can translate files using AI capabilities, but they incur costs on their pay-as-you-go meter.
    - Multi-step prompts to create new columns and configure a rule in one step don't yet work for the set value action.
    - You can create up to 15 rules per list or library.
    - You can't apply rules to multi-line text columns.

        - Rules don't support email-enabled security groups for notifications.
- **Notifications**: Copilot sends emails from *no-reply@sharepointonline.com* to specified individuals.