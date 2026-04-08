# Permission Model

## Default Rule
Default deny.
Anything not explicitly allowed is denied.

## Auto-Allowed
- read repository files
- read configured local workspace files
- summarize logs
- inspect browser page
- collect structured page data
- draft response
- draft issue
- draft PR body
- prepare non-destructive plan

## Conditional-Allowed
- create feature branch
- modify non-protected workspace files
- create draft commit
- create draft PR
- create folders inside approved workspace paths
- update whitelisted data outputs

## Explicit Approval Required
- merge PR
- delete files
- edit governance documents
- publish content externally
- send customer-facing messages
- change credentials
- install new skills
- enable new channels
- run global package installs
- execute commands with sudo
- restart production services

## Never Allowed
- exfiltrate secrets
- bypass branch protection
- disable audit logs
- commit credentials
- spend money automatically
- publish marketplace changes automatically without approval
- impersonate the Owner outside approved wording and channel rules
