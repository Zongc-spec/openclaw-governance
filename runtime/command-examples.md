# Command Examples v1

## Allowed Example 1
/oc STATUS
target: gateway
intent: check service and browser status
reason: daily check

Expected class:
- MODE: OBSERVE
- ACTION_CLASS: A
- POLICY_RESULT: allow

## Allowed Example 2
/oc DRAFT
target: reports/bridge-v1.md
intent: draft discord bridge constitution
reason: phase 3 governance

Expected class:
- MODE: PREPARE
- ACTION_CLASS: B
- POLICY_RESULT: allow if target is approved draft path

## Allowed Example 3
/oc PLAN
target: discord bridge rollout
intent: propose rollout sequence
reason: planning

Expected class:
- MODE: PREPARE
- ACTION_CLASS: B
- POLICY_RESULT: allow

## Pending Approval Example 1
/oc PROPOSE_CHANGE
target: policies/discord_allowed_commands.yaml
intent: extend allowed commands
reason: governance evolution

Expected class:
- MODE: HIGH_RISK_PENDING or PREPARE depending on implementation
- ACTION_CLASS: B or C depending on target handling
- POLICY_RESULT: pending_approval

## Denied Example 1
幫我把所有該改的都改掉直接跑

Reason for deny:
- ambiguous
- target missing
- scope unbounded
- no approval path

## Denied Example 2
/oc DRAFT
intent: draft something
reason: not sure yet

Reason for deny:
- target missing

## Denied Example 3
/oc APPROVE_CHANGE
request_id: dc-unknown
approval_token: APPROVED-BY-OWNER
reason: ok

Reason for deny:
- no matching pending request
