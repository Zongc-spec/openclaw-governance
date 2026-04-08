# Discord Command Spec v1

## Status
Phase 3 governance design only.
No production Discord execution bridge is authorized by this document alone.

## Role of Discord
Discord is a command transport channel only.
Discord is not a constitutional authority source.
Discord messages may request action, but all action must be interpreted under repository governance and policy rules.

## Allowed Command Types
Only the following command types are valid in v1:
- STATUS
- READ
- PLAN
- DRAFT
- PROPOSE_CHANGE
- APPROVE_CHANGE
- REJECT_CHANGE
- STOP

Any command outside this list is invalid by default.

## Command Syntax
Preferred v1 syntax is semi-structured and begins with `/oc`.

### Standard Form
/oc <COMMAND_TYPE>
target: <target>
intent: <intent>
reason: <reason>

## Examples

### STATUS
/oc STATUS
target: gateway
intent: check service and browser status
reason: daily check

### READ
/oc READ
target: reports/daily-summary.md
intent: read latest generated report
reason: operator review

### PLAN
/oc PLAN
target: discord bridge rollout
intent: propose rollout steps
reason: planning only

### DRAFT
/oc DRAFT
target: reports/bridge-v1.md
intent: draft discord bridge constitution
reason: phase 3 governance

### PROPOSE_CHANGE
/oc PROPOSE_CHANGE
target: policies/discord_allowed_commands.yaml
intent: propose extension of allowed draft commands
reason: governance evolution

### APPROVE_CHANGE
/oc APPROVE_CHANGE
request_id: dc-20260408-014
approval_token: APPROVED-BY-OWNER
reason: reviewed and accepted

### REJECT_CHANGE
/oc REJECT_CHANGE
request_id: dc-20260408-014
reason: target too broad

### STOP
/oc STOP
target: current execution
reason: operator stop

## Parsing Rules
- command must begin with `/oc`
- command type must be one of the allowed command types
- fields must be parsed into command envelope format
- missing required fields results in deny or clarification-needed state
- ambiguous natural language destructive intent must be denied

## Security Rules
- Discord does not override GitHub governance
- Discord may not amend constitution or policy directly
- Discord commands must be normalized before policy evaluation
- unverified actors must not be allowed to approve changes
