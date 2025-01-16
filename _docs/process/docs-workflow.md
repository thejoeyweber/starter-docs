# docs-workflow.md

# Docs Workflow
**Status**: [Draft / In Progress / Complete]

## Purpose
Describe how we create, update, and validate all documentation in /_docs/.

## Recommended Process
1. **Start with .cursorrules**  
   Load the project instructions, confirm naming/structure rules.
   If any variation from .cursorrules is necessary for a particular doc, be sure to note it clearly.

2. **Draft Document**  
   Use the relevant .md template (e.g., page doc, slice doc).
   Provide all context and references to o1 when generating content.

3. **Review & Validate**  
   Manually read doc for clarity and completeness. Check references to existing docs or code.

4. **Versioning & Changelog**  
   Maintain a simple version or “v2” naming if significant rewrites occur (e.g. 01.01-<doc>.md).
   Keep a short changelog if major updates to .cursorrules or system-wide naming changes are introduced.

5. **Encourage Iterative Doc Generation**  
   For substantial changes, create a “v2” or “01.01-...md” referencing the original doc so we can track evolution.

## Collaboration with AI
List best practices for giving o1 enough context, specifying final format, etc.

## Updates
Explain how to handle changes: rename docs, push new versions, maintain status fields.

## References
Link to plan docs or any “o1-prompting.md” doc
