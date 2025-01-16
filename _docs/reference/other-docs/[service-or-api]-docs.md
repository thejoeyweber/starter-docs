---
o1 Prompt:
---
CONTEXT:
- The “[service-or-api]-docs.md” template.
- We have a service or external API (Stripe, PostHog, etc.) to document.

WHAT TO GENERATE:
- A single markdown doc explaining usage, config, example calls, references.

GOAL:
- Provide a “{service}-docs.md” doc in the `_docs/reference/` folder.

Please output the doc now.


---
Template:
---
# [Service or API Name] Integration Docs
**Status**: [Draft / In Progress / Final]

## Overview
- [Short summary of what this service or API does and why it’s used.]

## Setup / Configuration
- [Any environment variables, keys, or config steps needed. Cite .cursorrules if relevant.]

## Usage Examples
- [Sample code or instructions, e.g. “How to create a Stripe Checkout session.”]

## References
- [Link to official documentation or other relevant docs in `/_docs`.]

## Next Steps
- [Future enhancements or advanced usage scenarios?]
