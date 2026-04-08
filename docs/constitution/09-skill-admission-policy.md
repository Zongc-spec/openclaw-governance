# Skill Admission Policy

## Admission Checklist
A skill may be approved only if all items are documented:
- skill name
- business purpose
- execution scope
- file/network/browser/system permissions
- external side effects
- failure mode
- rollback method
- audit output
- sample allowed commands
- sample denied commands

## Skill Classes
### S1 — Read-only skill
No write side effect.

### S2 — Drafting skill
May prepare artifacts in approved draft locations.

### S3 — Controlled-write skill
May write only to approved non-protected paths under explicit policy.

### S4 — High-risk external-action skill
Affects external systems or irreversible state. Always explicit approval.

## Default Rule
Unregistered skills are denied.
Unclassified skills are denied.
Skills without rollback notes are denied.
