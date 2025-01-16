---
o1 Prompt:
---
CONTEXT:
- The “03-scaffolding.md” template.
- Our known routes, pages, components from docs.

WHAT TO GENERATE:
- A final “03-scaffolding.md” describing how we create placeholders for all pages/components.
- Must adhere to .cursorrules naming and structure.

GOAL:
- Have a doc that ensures we systematically scaffold the app.

Please output “[03-scaffolding.md]” with all details included.



---
Template:
---

# 03 - Scaffolding
**Status**: [Draft / In Progress / Complete]

## Purpose
- Pre-create the folder/file structure for all planned pages, components, and APIs before building features.

## Tasks
1. **Review Documentation**  
   - [Look at the “core-pages-and-flows.md” or slice documents to identify all routes/components needed.]

2. **Create Placeholders**  
   - [Generate empty directories or `.md` files for each page, component, or API route.]

3. **Enforce .cursorrules**  
   - [Naming conventions, file structure, etc.]

4. **Smoke Test**  
   - [Verify that the empty pages compile and the app still runs.]

## Validation
- All major pages, components, and routes exist as placeholders.
- The folder structure matches the planned architecture.
- The dev build runs with no errors.

## Next Steps
- Move to `/_docs/plan/02-slices/00-slice-creation.md` for defining slices or actual feature builds.
