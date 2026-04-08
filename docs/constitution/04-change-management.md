# Change Management

## Rule
All durable system changes must follow:
Request -> Classification -> Policy Check -> Plan -> Approval Gate -> Execution -> Evidence -> Review

## Required for Controlled Write
- target path identified
- action class identified
- rollback path identified
- approval state recorded
- audit record generated

## Required for Governance Change
- GitHub branch
- pull request
- reviewer requirement
- no direct push to protected branch
- constitutional files under CODEOWNERS protection

## Merge Rule
Protected branches must require:
- pull request
- passing checks
- required review
- code owner review for governance paths

## Emergency Rule
Emergency does not remove audit requirements.
Emergency does not justify undocumented broadening of permissions.
Any emergency exception must be written back into incident records.
