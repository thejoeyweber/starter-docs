---
o1 Prompt:
---
CONTEXT:
- We have a template for project-setup.md. 
- We know .cursorrules must be implemented.

WHAT TO GENERATE:
- A finalized “01-project-setup.md” detailing the steps needed to set up the project, referencing .cursorrules and any custom steps we have.

GOAL:
- Produce a single markdown doc reflecting the project’s actual environment, with each step clearly described.

Please output the final [01-project-setup.md] file now.


---
Template:
---

# 1. Project Setup

# 01 - Project Setup
**Status**: [Draft / In Progress / Complete]

## Purpose
- Establish the initial codebase and environment so we have a running application.

## Tasks
1. **Initialize Repo**  
   - [Steps for creating or cloning a repo, setting up .gitignore, etc.]

2. **Install Starter App**  
   - [Steps for Next.js init, Tailwind, shadcn config, etc.]

3. **Configure .cursorrules**  
   - [Remind devs to keep .cursorrules in the root. Summarize key points.]

4. **Clean Up Boilerplate**  
   - [Remove or replace placeholder pages/components. Validate all runs well in dev.]

5. **Push to Git**  
   - [Confirm the local environment is stable, then push to remote repo.]

## Validation
- The app runs at localhost without errors.
- All placeholders are removed or updated.
- .cursorrules is recognized.

## References
- [Link to any relevant code samples or doc references if needed]

## Next Steps
- Move on to [02-documentation.md].
