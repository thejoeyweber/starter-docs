--- 
o1 Prompt:
---

CONTEXT:
- The “00-slice-creation.md” template.
- We have a set of user stories or features.

WHAT TO GENERATE:
- A “00-slice-creation.md” doc enumerating how we’ll break the project into slices.
- Must link each slice to relevant user stories or flows.

GOAL:
- Provide a final doc that clarifies how slices are defined and references any constraints from .cursorrules.

Please output “[00-slice-creation.md]” with all required details.


---
Template:
---

# 00 - Slice Creation
**Status**: [Draft / In Progress / Complete]

## Purpose
- Define how we identify and plan each “slice” (vertical feature set) in the application.

## Steps
1. **Review Project Docs**
   - [Check user stories, DB schema, pages/flows to see major features.]

2. **Determine Slices**
   - [List planned slices, e.g., “Auth Slice,” “Dashboard Slice,” etc.]
   - [Justify why each slice is separate.]

3. **Create Slice Plan Files**
   - [For each slice, create `01-{slice}.md`, `02-{slice}.md`, etc. with a status field.]

4. **Update or Cross-Reference .cursorrules**
   - [Mention any relevant technical constraints for each slice.]

## Validation
- We have a clear list of slices, each with its own plan file.
- Dependencies between slices are noted (e.g., “Auth must come before payments”).

## Next Steps
- Implement the first slice by referencing `01-{slice}.md`.
