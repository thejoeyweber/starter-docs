---
o1 Prompt:
---
CONTEXT:
- The “docs-workflow.md” template.
- Our known approach to doc creation (templates, references, versioning).

WHAT TO GENERATE:
- A final “docs-workflow.md” describing how we systematically create, update, and validate all docs.

GOAL:
- Provide a definitive guide to the doc process.

Please output “[docs-workflow.md]”.


---
Template:
---
# Docs Workflow
**Status**: [Draft / In Progress / Complete]

## Purpose
- Describe how we create, update, and validate all documentation in `/_docs/`.

## Recommended Process
1. **Start with .cursorrules**  
   - [Load the project instructions, confirm naming/structure rules.]

2. **Draft Document**  
   - [Use the relevant .md template (e.g., page doc, slice doc).]
   - [Provide all context and references to o1 when generating content.]

3. **Review & Validate**  
   - [Manually read doc for clarity and completeness. Check references to existing docs or code.]

4. **Versioning**  
   - [If we iterate significantly on a doc, create a “v2” or “01.01-...md” file referencing the original doc.]

## Collaboration with AI
- [List best practices for giving o1 enough context, specifying final format, etc.]

## Updates
- [Explain how to handle changes: rename docs, push new versions, maintain status fields.]

## References
- [Link to plan docs or any “o1-prompting.md” doc]
