---
o1 Prompt:
---
CONTEXT:
- We have the “01-{slice}.md” template.
- Our slice is [e.g., Auth, Dashboard, etc.]. Provide relevant background or user stories.

WHAT TO GENERATE:
- A slice plan doc named “01-{slice}.md” detailing DB updates, front-end, server actions, validation steps, referencing .cursorrules.

GOAL:
- Produce a thorough plan for building this slice, including acceptance criteria and next steps.

Please output that single markdown file now.


---
Template:
---
# 01 - [Slice Name]
**Status**: [Draft / In Progress / Complete]

## Overview
- [Describe what this slice accomplishes. For example: “Implements user auth, including sign-up, sign-in, and forgot password.”]

## Relevant Docs
- [Link to user stories, .cursorrules, DB schema, pages that belong to this slice, etc.]

## Implementation Steps
1. **DB Updates** (If Any)
   - [Schema changes? New tables or columns?]
   - [Reference the “03-db-schema.md” if updated.]

2. **Frontend Pages/Components**
   - [Which pages get built or updated? Which new components or modals are needed?]

3. **Server Actions / API**
   - [Any new server actions in `@/actions/db/…` or APIs in `app/api/…`?]

4. **Integration & Testing**
   - [Unit tests, integration tests, or manual checks for this slice.]

5. **Validation**  
   - [List acceptance criteria: “User can do X.” “System logs an error if Y.”]
   - [Check .cursorrules for naming conventions, etc.]

## Known Issues or Follow-Ups
- [If partial features or sub-slices remain, note them. Possibly spawn `01.01-{slice}-fixes.md`.]

## Next Steps
- [Which slice do we build next? Mention if we have dependencies on this slice.]
