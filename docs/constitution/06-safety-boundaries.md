# Safety Boundaries

## Protected by Default
- governance files
- protected branches
- credentials
- external publish surfaces
- payment operations
- destructive shell operations
- irreversible deletions

## High-Risk Examples
- merge to main
- delete files recursively
- publish store content
- send customer-facing messages
- modify auth/session settings
- change runtime exposure or network access

## Rule
High-risk actions are never inferred from vague language.
