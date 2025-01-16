
---
o1 Prompt:
---

# **o1 Prompt for `[page-name].md`**

Below is an **example** you can adapt whenever you want to generate or update a page doc via o1:

```text
CONTEXT:
1. We have a comprehensive page doc template (paste the template from above).
2. The page in question is called [Page Name].
3. Our user stories, relevant DB fields, and .cursorrules are as follows:
   - (Paste or summarize the relevant user stories, DB columns, .cursorrules rules about UI design.)

WHAT TO GENERATE:
- A final `[page-name].md` document that:
  - Fills in each section (Purpose, Layout, Fields, etc.) based on the context provided.
  - Lists all UI states (loading, error, success).
  - Includes any shadcn/Tailwind components we plan to use.
  - Mentions the server actions or APIs used for data or submission.

GOAL:
- Produce a single, definitive doc so a designer can fully build or update the page with no ambiguities.

Please output the final `[page-name].md` with each section filled in.



---
Template:
---
# [Page Name]
**Status**: [Draft / In Progress / Final]

## 1. Purpose & High-Level Overview
- **Why this page exists**: [Brief explanation—what user goal does it fulfill?]
- **Core Functionality**: [Summarize the primary actions or outcomes on this page.]

---

## 2. Layout & UI Organization
- **Overall Layout**: [Describe how the page is structured. E.g., “Header, then sidebar (if any), main content area with two columns,” etc.]
- **Key Sections**:
  1. **Section A**: [What’s displayed? Is it a table, form, or cards?]
  2. **Section B**: [Another zone or sub-section if relevant.]
  3. **Sidebars / Tabs / Modals** (if applicable): [Explain how they appear or toggle.]

> **Design Note**: If you can, embed an ASCII-wireframe, a quick Figma screenshot link, or a bullet-based “visual layout” to give an at-a-glance reference.  
> 
> Example (ASCII sketch):
> ```
> +-------------------------------------------------------+
> | Header (page title, subtitle, optional button)        |
> +-------------------------------------------------------+
> | Side Nav    | Main Content: Section A  | Right Panel? |
> |            ...                         | (If used)    |
> +-------------------------------------------------------+
> ```

---

## 3. Fields & Form Inputs
List each field, label, data type, and any relevant validations or defaults.

| Field Name     | Type       | Label / Display Text     | Validation / Constraints | Default Value | Notes                          |
|----------------|----------- |---------------------------|--------------------------|--------------|--------------------------------|
| **field1**     | text       | `Title`                  | required, max 100 chars  | (none)       | Stored in DB as `title`        |
| **field2**     | dropdown   | `Category`               | must select an option    | “General”    | Options from server, see API   |
| **field3**     | checkbox   | `Is Active?`             | optional                 | false        | Tied to `active` boolean in DB |

> **Design Note**: This table ensures a designer/dev knows exactly how each field is labeled, validated, and displayed.

---

## 4. Components & Dependencies
- **Shadcn Components Used**:  
  - e.g. `<Button variant="outline" />` for the “Cancel” action  
  - e.g. `<Input />` from `@/components/ui/input`  
- **Layouts / Shared Components**:  
  - e.g. `MainLayout` from `/components/layouts/…`
- **Any custom UI elements** (cards, tables, etc.):  
  - Indicate if they live in `/_components` for this route vs. global reuse in `/components/`.

> **Design Note**: This clarifies *exactly* which building blocks must be used (sizing, colors, classes) as per your Tailwind + shadcn design system.

---

## 5. Backend Integration & Data Flow
- **Server Actions / APIs Triggered**:
  1. **createThingAction** from `@/actions/db/things-actions.ts` – used when user saves the form.
  2. **listThingsAction** from `@/actions/db/things-actions.ts` – populates a table on load.

- **Data-Fetching Approach**:
  - “Use server component to fetch X from `listThingsAction`. Pass data to the client component as props.”
- **Error Handling**:
  - “If createThingAction fails, show toast with error. Keep form data in place for user to correct.”

> **Design Note**: By detailing each action or API route, a designer/dev knows precisely which data or actions must be accounted for in the UI, so error + loading states can be designed.

---

## 6. Page Variants & States
List each possible variation or state this page might have, ensuring the design covers them all.

1. **Default / Initial State**  
   - e.g. “Empty form or default selections.”
2. **Loading State**  
   - e.g. “Show skeleton or spinner for the main content area until data is fetched.”
3. **Error State**  
   - e.g. “If server action fails, show error toast or inline error messages.”
4. **Success State**  
   - e.g. “Redirect to confirmation page or display success banner?”
5. **Empty State** (if listing data)  
   - e.g. “No items to display, show empty illustration or message.”

> **Design Note**: This helps a designer fully cover each scenario with the right visual cues.

---

## 7. Mockups / Wireframes (Optional but Recommended)
- **Screenshots or ASCII**: Provide or link to more detailed visuals for each variant (loading, error, success, etc.).
- **Annotations**: E.g., “Button is 44px high, uses shadcn `primary` style. This is important for brand consistency.”

---

## 8. Acceptance Criteria
- **Functional Checks**:
  1. “User can input all required fields and successfully submit to create new item.”
  2. “Form shows relevant validation if fields are invalid (display error messages).”
  3. “Loading state is visible while waiting for data or submission response.”

- **UI Checks**:
  1. “Matches brand color palette from `.cursorrules` or design tokens.”
  2. “Elements are properly spaced, consistent with Tailwind `padding`, `margin` standards.”

- **Performance / Responsiveness**:
  - e.g. “Page must load under 2s on typical broadband; layout responsive for mobile.”

---

## 9. References & Cross-Links
- **User Stories**: [Link to `_docs/project/02-user-stories-and-requirements.md` item X or Y]
- **DB Schema**: [Mention any relevant table/column references from `_docs/project/03-db-schema.md`]
- **.cursorrules**: [If there are specific naming or layout rules from your root instructions]
- **Other Pages**: [If this page transitions to or from other pages, mention them here]

---

## 10. Next Steps / Additional Notes
- [Any known open questions? E.g. “We might need to confirm final color for the button.”]
- [If additional subpages or modals are discovered mid-design, note them here to create a new doc.]

---

# Example Usage

Here’s a quick example snippet showing how a filled-out doc might look in practice:

> *Name*: `user-profile.md`  
> *Status*: Draft  

> **1. Purpose**: Let users update their personal information and view account details.  
> **2. Layout**: 2-column layout with profile pic on left, user details on right.  

*(…and so on…)*
