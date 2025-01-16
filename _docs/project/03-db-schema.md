---
o1 Prompt:
---
CONTEXT:
- The “03-db-schema.md” template.
- Summaries of your actual data model or .cursorrules for schema rules.

WHAT TO GENERATE:
- A final DB schema doc describing each table, columns, relationships.

GOAL:
- Produce “03-db-schema.md” as the single source of truth for the data model.

Please output that doc now.



---
Template:
---
# Database Schema
**Status**: [Draft / In Progress / Final]

## Overview
- [Short summary of the DB approach: Drizzle, Supabase, etc.]

## Entities / Tables
1. `[table_name]`
   - [Columns, types, constraints, references]
   - [CreatedAt, UpdatedAt, etc. per .cursorrules]

2. [Add more as needed]

## Relationships
- [List foreign keys, references, or cascade behaviors.]

## Security & Indexing (Optional)
- [Notes on sensitive data or indexing approach.]

## References
- [Link to user stories that mention these entities, or mention .cursorrules for schema naming rules.]

## Next Steps
- Adjust or confirm with “actions/db/…” server actions for these tables.
