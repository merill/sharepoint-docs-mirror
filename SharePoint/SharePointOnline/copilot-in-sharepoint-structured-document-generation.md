---
layout: Conceptual
title: Generate structured documents in a SharePoint document library - SharePoint in Microsoft 365 | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/sharepoint/copilot-in-sharepoint-structured-document-generation
breadcrumb_path: /sharepoint/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-SharePoint
feedback_system: Standard
feedback_product_url: https://feedbackportal.microsoft.com/feedback/forum/06735c62-321c-ec11-b6e7-0022481f8472
recommendations: true
description: Structured document generation lets you turn Word document templates into intelligent, AI-powered forms.
manager: corywink
author: cjtancortex
ms.author: shrganguly
ms.service: sharepoint-online
ms.subservice: ai-copilot
ms.topic: article
ms.date: 2026-08-26T00:00:00.0000000Z
ms.update-cycle: 180-days
audience: Admin
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365copilot
f1.keywords:
- NOCSH
search.appverid:
- MET150
locale: en-us
document_id: 61c33d2c-cb7f-5aee-62c5-ab45c88010f6
document_version_independent_id: 34cdcba2-17d4-e84d-2a2e-bcf27525573a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SharePoint-pr/blob/live/SharePoint/SharePointOnline/copilot-in-sharepoint-structured-document-generation.md
site_name: Docs
depot_name: office.OfficeDocs-SharePoint
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-SharePoint/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: copilot-in-sharepoint-structured-document-generation
moniker_range_name: 
monikers: []
item_type: Content
source_path: SharePoint/SharePointOnline/copilot-in-sharepoint-structured-document-generation.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/97159432-14a9-4307-a469-d2f2c75f0e33
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/50565c62-5f6b-4687-be38-323113c72c2e
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 18eeb1d1-e759-8cb2-97f4-af080aa6f4b2
---

# Generate structured documents in a SharePoint document library - SharePoint in Microsoft 365 | Microsoft Learn

Structured document generation lets you turn Word document templates into intelligent, AI-powered forms. When a user submits a form, the system automatically generates a new document from the template with the submitted values merged into the appropriate fields. This process creates consistent, governed documents every time - without requiring manual edits to the template.

This feature is useful for organizations that regularly produce standardized documents, such as:

- **Legal and compliance** - Contracts, NDAs, statements of work, settlement agreements, vendor agreements.
- **Procurement and finance** - Purchase orders, invoices, payment authorizations.
- **Human resources** - Employment verification letters, offer letters, travel and visa support letters.
- **Sales and operations** - Proposals, bid documents, statements of compliance, customer letters.

## How structured document generation works

The document generation process involves two roles and a handoff between them.

**Content manager (template creator)** - Creates and governs templates and forms. They define the document structure, required fields, and conditional rules to ensure that every generated document is consistent and compliant.

**Content consumer (form submitter)** - Submits forms to generate documents. They fill out the form with the requested information, and the system generates a new document that preserves the approved layout and language - only the field values change.

## Prerequisites

- Content managers, or users who create and configure forms, must have a [Microsoft Copilot license](/en-us/microsoft-365/copilot/microsoft-365-copilot-licensing) assigned.
- To create a form, users must have **Edit** permissions on the document library.
- The source document must be a Microsoft Word document (.docx format).

## Create a form from a document

You can create a form from any Word document stored in a SharePoint document library.

1. In a SharePoint document library, select **Forms** from the command bar.
2. Select **Document generation form** to start the form creation process.

    [![Screenshot that shows the Forms command in a SharePoint document library with the Document generation form option selected.](sharepointonline/media/structured-document-generation/component-136.png)](sharepointonline/media/structured-document-generation/component-136.png#lightbox)
3. You get a high-level step pane that highlights how you go about the flow, so you know what to expect at each stage of form creation.

    [![Screenshot that shows the high-level step pane outlining the stages of the form creation flow.](sharepointonline/media/copilot-in-sharepoint-structured-document-generation/image.png)](sharepointonline/media/copilot-in-sharepoint-structured-document-generation/image.png#lightbox)
4. If you're on the document library home page, you're prompted to create a target folder. Each document generated from the form is saved into this folder.
5. Upload the Word document you want to use as a template. You can select a document from:

    - The current SharePoint document library
    - A OneDrive location
    - Your local device

    Tip

    For best results, upload a Word document with annotated placeholders such as {} or [].

    [![Screenshot that shows the options to upload a Word document from the SharePoint document library, a OneDrive location, or your local device.](sharepointonline/media/structured-document-generation/component-68.png)](sharepointonline/media/structured-document-generation/component-68.png#lightbox)
6. Copilot in SharePoint analyzes the structure of the document and automatically suggests fields—such as names, dates, addresses, and responsibilities—so you don't have to do manual setup.

    [![Screenshot that shows the suggested fields list with an indicator that a field matches an existing column in the site.](sharepointonline/media/copilot-in-sharepoint-structured-document-generation/image7.png)](sharepointonline/media/copilot-in-sharepoint-structured-document-generation/image7.png#lightbox)

    Note

    If you have other forms in the document library, you might see a reused indicator that calls out that this field "Matches an existing column in this site. Saving this field reuses that column instead of creating a new one." More on this.
7. Review the suggested fields. You can:

    - Confirm which fields are required.
    - Refine field names to match your organization's terminology.
    - See how each field maps back to locations in the document.

### Customize fields section

In the **Customize fields** section, you can:

- Use the search pane to look for existing columns to reuse, or add new fields.
- Select **Detect potential fields** to run AI detection on the document content.
- Use the **Insert** dropdown on each field to map it to specific locations in the document.
- Select the **...** (more options) menu on a field to rename it, change help text, or delete it.

    [![Screenshot that shows the Customize fields section with options to search for columns, detect potential fields, and map fields to the document.](sharepointonline/media/copilot-in-sharepoint-structured-document-generation/image8.png)](sharepointonline/media/copilot-in-sharepoint-structured-document-generation/image8.png#lightbox)

    Note

    Each field shows the number of insertions in the document (for example, "1 of 3 insertions"), so you can see exactly where values appear in the generated document.

### Configure field details

When you create or edit a field, configure the following details:

- **Field name** — Enter a descriptive name for the field.
- **Description** — A free-form text field for summaries or explanatory notes that give additional context about the field.
- **Required** — Select the **Document authors are required to fill this field** checkbox to make the field mandatory.
- **Type** — Select the data type for the field from the **Type** dropdown.
- **Default value** — Enter a value that pre-fills the field on the form, so submitters can accept it as-is or change it before submitting.

    [![Screenshot that shows the field details configuration options, including field name, description, required checkbox, and type.](sharepointonline/media/copilot-in-sharepoint-structured-document-generation/image9.png)](sharepointonline/media/copilot-in-sharepoint-structured-document-generation/image9.png#lightbox)

### Reuse fields across forms

If other forms already exist in the same document library, you can reuse an existing field instead of creating a duplicate one. When adding a field, use the search bar to find matching columns in the library—you'll see each match along with its data type—and choose whether to reuse an existing column or create a new one.

Reusing a field means multiple forms share the same underlying library column, so it appears only once in the library view. This feature eliminates duplicate columns (such as several "Contractor Name" fields), keeps your library schema clean, and ensures consistent metadata across every form.

When a column is shared by more than one form, its **name and data type are locked** and can only be changed through SharePoint column settings, not from the form. Form-specific properties such as help text and the required checkbox remain editable per form. If you need a different data type for a shared field, the system warns you and, if you proceed, creates a new "forked" column—leaving the original unchanged for other forms. Deleting a shared field removes it only from the current form; once just one form uses it, the field becomes fully editable again.

### Supported field types

The following field data types are supported:

- **Single line of text** — A short text input for names, titles, or brief descriptions.
- **Multiple lines of text** — A longer text input for detailed content such as responsibilities or clauses.
- **Number** — A numeric input for quantities, amounts, or identifiers.
- **Currency** — Stores monetary values with currency formatting and precision for financial calculations.
- **Date and time** — A date picker for selecting dates or date and time values.
- **Hyperlink** — A URL input for linking to external resources or references.
- **Email** — An email address input field.
- **Choice** — A dropdown selection from predefined options.
- **Image** — An image field for inserting logos, signatures, or other visual content into the document.
- **Managed metadata** — A field that references terms from a managed term set, so submitters select standardized, governed values instead of typing free text.
- **SharePoint List** — A lookup field that references values from a column in a SharePoint list.

When you select **SharePoint List** as the field type, you're prompted to select the SharePoint list column to associate with the field. You can also select the **Document authors can type in values manually for this field** option to allow form submitters to enter values directly in addition to selecting from the list.

[![Screenshot that shows the supported file types.](sharepointonline/media/structured-document-generation/picture1.png)](sharepointonline/media/structured-document-generation/picture1.png#lightbox)

[![Screenshot that shows the field name and type options.](sharepointonline/media/structured-document-generation/picture2.png)](sharepointonline/media/structured-document-generation/picture2.png#lightbox)

### Set up conditional sections

You can define business rules as conditional logic and map them to multiple sections in the document. Conditional sections let you control which parts of the generated document are included based on the values that form submitters enter.

For example, a legal agreement might include country-specific clauses that only appear when the submitter selects a particular country.

To set up a conditional section:

1. Open the template document. In the **Manage templates** pane, go to **Conditional sections** and select **+ New**.
2. Enter a **Name** for the conditional section, such as "Country specific clauses".
3. Under **Set up condition**, configure one or more conditions. The system evaluates conditions in top-to-bottom order. For each condition:

    - Select the field to evaluate, such as "Residing Country".
    - Select the matching rule, such as **exact match** or **contains**.
    - Enter the value to match against.
4. To add multiple conditions, select **And** or **Or** to combine them.
5. Select **Map** to associate the conditional section with one or more sections in the document content.

    [![Screenshot that shows how to set up a conditional section and map it to one or more sections in the document content.](sharepointonline/media/structured-document-generation/screenshot-2026-02-25-225111.png)](sharepointonline/media/structured-document-generation/screenshot-2026-02-25-225111.png#lightbox)

Note

You can create multiple conditional sections, each with different rules. For example, you might have separate conditions for "India specific privacy note," "US only clause," and "Other countries," each mapped to different sections of the document.

Important

Conditional sections are evaluated when the document is generated from the form. In a generated document opened in **Word for the web**, conditional sections don't update when you change a field value after generation—the hidden and shown sections stay as they were at generation time. This is a platform limitation of Word for the web, which supports a subset of the functionality available in Word for Windows (desktop), and there's currently no reliable workaround. To re-evaluate conditional sections against new field values, submit the form again to generate a new document, or open the generated document in Word for Windows (desktop).

When you finish configuring fields and conditional sections, select **Publish and open in Forms** at the bottom of the pane. Word closes the template and transitions to the form view in SharePoint. A loading indicator shows "Closing template and opening form" during the transition.

## Customize the form

After you publish the template, the form opens in SharePoint with a customization pane on the right side. The pane has two tabs: **Customize** and **Send form**.

### Show or hide fields

On the **Customize** tab, the **Show or hide fields** section lists all fields from the template with a checkbox for each one. Selected fields appear in the form. Clear the checkbox for any field you don't want to show to form submitters.

[![Screenshot that shows the Show or hide fields section with a checkbox for each field from the template.](sharepointonline/media/copilot-in-sharepoint-structured-document-generation/image4.png)](sharepointonline/media/copilot-in-sharepoint-structured-document-generation/image4.png#lightbox)

Note

For advanced field changes, edit the template in Word. The **Show or hide fields** section controls field visibility only.

### Set up conditional field visibility

While **Show or hide fields** controls which fields appear for everyone, *conditional field visibility* shows or hides an individual field dynamically—based on the answers a submitter provides to other fields. This keeps forms short and relevant, so submitters only see the questions that apply to them.

For example, on a vendor onboarding form you can hide the **Hardware Certification ID** field until the submitter selects **Hardware** in a **Vendor Category** choice field. If the submitter selects multiple categories—such as **Hardware** and **Professional Services**—every matching field appears automatically, while fields for unselected categories stay hidden.

A field that has a visibility rule is hidden by default and appears only when its condition evaluates to true.

Note

Conditional field visibility is also available for List forms and File upload forms, not just document generation forms.

To configure conditional visibility for a field:

1. On the **Customize** tab, select the **Conditional logic** pivot.[![Screenshot that shows the Conditional logic pivot in the form editor, listing each form field with options to add a visibility condition and set branching with Go to.](sharepointonline/media/copilot-in-sharepoint-structured-document-generation/image1.png)](sharepointonline/media/copilot-in-sharepoint-structured-document-generation/image1.png#lightbox)
2. Select the field you want to show or hide conditionally, and then select **Add visibility condition**.
3. Set the behavior to **Show this field when** the condition is met, then define a condition:

    - Select the **master field** whose answer the rule evaluates.
    - Select an **operator** for the comparison.
    - Enter or select the **value** to compare against.
4. To combine conditions in the same rule, add another condition and choose **AND** (every condition must be true) or **OR** (any one can be true). Conditions are evaluated top to bottom.
5. The field now stays hidden until a submitter's answers satisfy the condition.

Once a rule is set, each field that has conditional visibility shows an indicator in the form editor—select it to jump straight to that field's condition and edit it.

[![Screenshot that shows a form field in the editor with a conditional visibility indicator that a form creator can select to open and edit the field's condition.](sharepointonline/media/copilot-in-sharepoint-structured-document-generation/image2.png)](sharepointonline/media/copilot-in-sharepoint-structured-document-generation/image2.png#lightbox)

Note

If a field's visibility comes from a conditional section defined in the Word template, that condition is generated automatically and appears in the **Conditional logic** pivot as read-only. To change it, edit the conditional section in the Word template.

Note

Conditional visibility and branching work at different levels. Branching jumps the submitter to a specific *field* based on an answer, while conditional visibility controls whether an *individual field* appears. When you use both, branching decides which field comes next, then conditional visibility determines whether the fields along the way are shown. A rule built on a field the submitter never reaches—because it's hidden or skipped by branching—can never be satisfied, so its target field stays hidden.

#### Supported field types and operators

You can build conditions on the following field types. The operators and input control depend on the field type.

| Field type | Operators | Input control |
| --- | --- | --- |
| Single line of text, Multiple lines of text | Exact match, Not equal, Contains, Does not contain, Is empty, Is not empty | Text input |
| Choice (single or multiple), SharePoint List | Exact match, Not equal, Contains, Does not contain, Is empty, Is not empty | Choice selector |
| Number, Currency | Equal, Not equal, Greater than, Less than, Is empty, Is not empty | Number input |
| Date and time | Exact match, Not equal, Before, After, Is empty, Is not empty | Date picker |
| All other types | Is empty, Is not empty | No input control |

For the **Is empty** and **Is not empty** operators, no value input is required.

Note

Date and time as master fields aren't available yet. The operators are listed above for reference, but conditions built on a Date and time field aren't supported in this release—support is coming soon.

#### Validation and required fields

- If a rule references a field that you deleted or removed from the form, the system shows a warning so you can fix the rule. It doesn't block you from publishing.
- A required field that is hidden by its visibility rule doesn't block submission. The form validates a required field only when it's visible and left empty, so submitters are never blocked by a required field they can't see.

Important

Conditional field visibility affects what a submitter sees while filling out the form—it's a form-filling experience, not a way to control the data itself. Because of this, **Power Automate doesn't apply conditional visibility**: if you generate documents through a Power Automate flow, the flow doesn't hide or show fields the way the form does, so a required field that your form hides will still be visible in the document.

Tip

When you use a form with Power Automate, make any field you'd normally hide an optional field so it doesn't block the intended flow.

### Themes and settings

Expand the **Themes** section to change the visual appearance of the form.

Expand the **Settings** section to configure form-level options:

- **Notify me** — Toggle to receive a notification when a form is submitted.
- **One response per person** — Toggle to limit each user to a single form submission.
- **Accept responses** — Toggle to start or stop accepting form submissions.
- **Message when form is closed** — Customize the message displayed to users when the form is no longer accepting responses (default: "We're not accepting responses at the moment.").

    [![Screenshot that shows the form Settings section with options such as Notify me, One response per person, and Accept responses.](sharepointonline/media/copilot-in-sharepoint-structured-document-generation/image5.png)](sharepointonline/media/copilot-in-sharepoint-structured-document-generation/image5.png#lightbox)

Expand the **Generated file settings** section to control the output format and naming of the documents the form produces.

- **Select file type** — Choose the format for the generated document: **Word (.docx)** or **PDF (.pdf)**.
- **Set file name pattern** — Define how generated files are named by combining fields and text (for example, "Template name\_Created by"). Press **/** to insert a field; only required fields can be inserted.

    [![Screenshot that shows the Generated file settings section with options to select the file type and set a file name pattern.](sharepointonline/media/copilot-in-sharepoint-structured-document-generation/image6.png)](sharepointonline/media/copilot-in-sharepoint-structured-document-generation/image6.png#lightbox)

### Share the form link

After you publish the form, share the form link so users in your organization can submit forms and generate documents.

1. Select the **Send form** tab in the customization pane to access the form link.

    [![Screenshot that shows the Send form tab with the form link available to copy and share.](sharepointonline/media/structured-document-generation/component-99.png)](sharepointonline/media/structured-document-generation/component-99.png#lightbox)
2. Copy the form link and distribute it through any collaboration channel:

    - Microsoft Teams
    - Outlook
    - SharePoint agents
    - SharePoint site pages

Tip

You can embed the form link directly on a SharePoint site page so that users can find and access it alongside other resources on your internal sites.

The form link is persistent—it stays the same URL even when you update and republish the template. Form submitters always see the latest published version.

## Fill out and submit a form

Content consumers use the shared form link to generate documents.

1. Open the form link from the location where you shared it—for example, a SharePoint site page, a Teams message, or an email. A simple form opens in the browser.

    [![Screenshot that shows a generated form open in the browser, ready for a submitter to fill out.](sharepointonline/media/structured-document-generation/chat-l1-chat-zq.png)](sharepointonline/media/structured-document-generation/chat-l1-chat-zq.png#lightbox)
2. Fill in the requested fields, such as event details, vendor information, roles, responsibilities, and key dates. Each field shows its data type with an icon. Required fields are clearly indicated.
3. Select **Submit** to generate the document.

    [![Screenshot that shows a completed form with the Submit button used to generate the document.](sharepointonline/media/structured-document-generation/chat-l1-chat-zq-1.png)](sharepointonline/media/structured-document-generation/chat-l1-chat-zq-1.png#lightbox)
4. The system generates a professionally formatted document using the approved template. The field placeholders in the template are replaced with the values you entered—no copying, no manual edits.

    [![Screenshot that shows the formatted document generated from the template with the submitted values merged into the fields.](sharepointonline/media/structured-document-generation/copilot-title-teal-blue.png)](sharepointonline/media/structured-document-generation/copilot-title-teal-blue.png#lightbox)

Behind the scenes, the generated document lands in the governed SharePoint library configured by the form creator, with metadata automatically captured from the form submission.

Note

You don't need access to the destination document library to submit the form. You only need access to view the generated document afterward.

## Manage generated documents

Each form submission generates a new document that's stored in the SharePoint library where you configure the form. To view generated documents:

1. Go to the SharePoint document library where you set up the form.
2. Open the folder that's linked with the form. Each generated document is stored here with the submitted values merged into the template.
3. Review the document metadata. Because the form captures rich, structured metadata from each submission, the library columns automatically populate with the field values - such as names, dates, and other details - making it easy to sort, filter, and search across generated documents.

    [![Screenshot that shows generated documents in a SharePoint library with metadata columns automatically populated from the form submissions.](sharepointonline/media/structured-document-generation/component-67.png)](sharepointonline/media/structured-document-generation/component-67.png#lightbox)

Note

Every generated document automatically receives a **reference number**—a unique identifier that stays with the document for its entire life, independent of its file name, location, or format. Each reference number is created once, never reused, and is unique across the site. The reference number becomes a usable field that you can insert into the document template just like any other field, and it stays the same when documents are copied or moved. If a document is regenerated, it gets a new reference number.

Content managers can decide how it appears by adding a prefix and suffix around an automatic, system-controlled running number that's at least four digits. The prefix and suffix can include text or contextual details—such as a fiscal year, department, or vendor name—letting you build a readable format, for example `MEA-2026-0001`.

### Set up downstream automation

The rich metadata captured from form submissions makes it straightforward to configure downstream automation workflows. For example, you can:

- **Set up notifications** - Use SharePoint rules or Power Automate to notify stakeholders when a new document is generated.
- **Trigger approval workflows** - Route generated documents for review and approval based on metadata values.
- **Move or copy documents** - Automatically organize generated documents into specific folders based on field values.
- **Integrate with other systems** - Use Power Automate to send document details to external systems, CRM tools, or reporting dashboards.

Tip

Because each form submission creates a list item with structured metadata, you can use the full range of SharePoint list automation capabilities - including rules, Power Automate flows, and API integrations - to build end-to-end business processes around your generated documents.

## Edit a published form

After you publish a form, the form fields are read-only in the SharePoint form view. To make structural changes to fields, edit the template in Word.

1. From the form view in SharePoint, select the option to open the template in Word.
2. In Word, select **Edit template** in the **Manage templates** pane. You can now add, update, or remove fields.
3. When you finish making changes, select **Publish and open in Forms** to republish the template and return to the form view.
4. The form link stays the same. Form submitters automatically see the updated fields after republishing.

Important

After you publish a form, make structural changes to fields (adding, deleting, or modifying field types) in Word. Make non-structural changes such as showing or hiding fields, changing themes, and updating settings directly in the SharePoint form view.

## Manage forms

You can view and manage all forms associated with a document library from the **Forms** menu.

1. In the document library, select **Forms** from the command bar to see all created forms. Each form has a one-to-one mapping with a template.
2. From the forms list, you can:

    - **Edit form** — Open the form configuration to make changes.
    - **Delete form** — Remove the form. The underlying template is preserved.
    - **Start or stop accepting responses** — Toggle form availability.

    [![Screenshot that shows the Forms list with options to edit a form, delete a form, and start or stop accepting responses.](sharepointonline/media/structured-document-generation/screenshot-2026-02-25-230115.png)](sharepointonline/media/structured-document-generation/screenshot-2026-02-25-230115.png#lightbox)

## Use Power Automate with structured document generation

Use Power Automate to automate document generation and build end-to-end workflows that use forms in SharePoint.

- **Form submitted (Preview)** triggers a flow when a form is submitted, so you can start workflows such as approvals or notifications.
- **Get form metadata (Preview)** retrieves the form structure, so you can map responses to fields without manual configuration.
- **Generate document from form (Preview)** creates documents by mapping input data to a document generation template and saves the output to a SharePoint library.

By using these capabilities, you can automate document creation as part of larger workflows, such as generating contracts or reports based on business events.

For more details on triggers and actions, see [SharePoint connector actions and triggers](/en-us/sharepoint/dev/business-apps/power-automate/sharepoint-connector-actions-triggers).

## Requirements and limitations

- **Supported file types** — Only Microsoft Word documents (.docx) support creating templates.
- **Permissions** — Form creators need Edit access on the document library. Form submitters need only the form link (Read access to the template is granted automatically).
- **Limitations**:

    - Forms are read-only once published. To make structural field changes, edit the template in Word and republish.
    - Form submitters don't automatically receive access to the destination document library. You must grant access to view the generated document separately, or the form creator can enable the receipt option.
    - PDF generation doesn't work if sensitivity labels are enabled for the site or library. Support for that feature is coming soon.