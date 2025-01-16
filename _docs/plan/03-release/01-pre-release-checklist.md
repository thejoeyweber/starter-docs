---
o1 Prompt:
---
CONTEXT:
- The “01-pre-release-checklist.md” template.
- Summaries of all slices and any QA steps we have.

WHAT TO GENERATE:
- A final “01-pre-release-checklist.md” with the actual checks relevant to our project, referencing .cursorrules or security steps if needed.

GOAL:
- Ensure we have a thorough pre-release to-do list.

Please output “[01-pre-release-checklist.md]”.


---
Template:
---
# 01 - Pre-Release Checklist
**Status**: [Draft / In Progress / Complete]

## Purpose
- Final checks to ensure the application is production-ready.

## Checklist
1. **All Slices Complete**  
   - [Confirm each slice doc is marked “Complete.”]

2. **Testing & QA**  
   - [Run full test suite: unit, integration, e2e if available.]
   - [Check for any open issues in bug tracker.]

3. **Performance Check**  
   - [Basic load testing or performance profiling if needed.]

4. **Security**  
   - [Review .env usage, tokens, and secrets. Adhere to .cursorrules about environment variables.]

5. **Documentation Updated**  
   - [All relevant `.md` files reflect final app state.]

## Validation
- If everything passes, we’re good to proceed to final release tasks.
- If not, specify next steps or additional fixes.

## References
- [Link to any relevant doc about deployment or monitoring.]

## Next Steps
- Proceed to `02-final-release.md`.

