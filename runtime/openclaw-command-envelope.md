# OpenClaw Command Envelope v1

## Purpose
Every Discord command must be normalized into a standard command envelope before policy evaluation or execution.

## Canonical Envelope Fields
REQUEST_ID:
TIMESTAMP:
CHANNEL:
ACTOR:
ACTOR_VERIFIED:
COMMAND_TYPE:
MODE:
ACTION_CLASS:
TARGET:
INTENT:
JUSTIFICATION:
APPROVAL_TOKEN:
ROLLBACK_REQUIRED:
POLICY_RESULT:
EXECUTION_STATE:
NOTES:

## Field Definitions
- REQUEST_ID: unique request identifier
- TIMESTAMP: ISO 8601 timestamp
- CHANNEL: source channel, v1 uses discord
- ACTOR: sender identity label
- ACTOR_VERIFIED: true or false
- COMMAND_TYPE: one of 8 allowed Discord commands
- MODE: OBSERVE / PREPARE / CONTROLLED_EXECUTE / HIGH_RISK_PENDING
- ACTION_CLASS: A / B / C / D
- TARGET: requested target object or surface
- INTENT: normalized intent summary
- JUSTIFICATION: short reason for request
- APPROVAL_TOKEN: required for approved high-control transitions
- ROLLBACK_REQUIRED: yes or no
- POLICY_RESULT: allow / deny / pending_approval
- EXECUTION_STATE: received / normalized / blocked / approved / executed / failed
- NOTES: extra context

## Normalization Rule
No execution-side evaluation may occur until a request is normalized into this exact envelope shape.

## Default Mapping Guidance
- STATUS -> MODE OBSERVE / ACTION_CLASS A
- READ -> MODE OBSERVE / ACTION_CLASS A
- PLAN -> MODE PREPARE / ACTION_CLASS B
- DRAFT -> MODE PREPARE / ACTION_CLASS B
- PROPOSE_CHANGE -> MODE PREPARE / ACTION_CLASS B or HIGH_RISK_PENDING depending on target
- APPROVE_CHANGE -> no execution by itself; changes approval state only
- REJECT_CHANGE -> no execution by itself; terminates pending request
- STOP -> immediate stop request; no expansion allowed

## Deny Conditions
Requests must be denied if:
- actor is unverified for privileged command types
- target is missing for target-dependent requests
- intent is ambiguous
- request implies destructive action without explicit approval path
- request conflicts with constitution or protected path policy

## Example Envelope
REQUEST_ID: dc-20260408-001
TIMESTAMP: 2026-04-08T14:30:00+08:00
CHANNEL: discord
ACTOR: owner
ACTOR_VERIFIED: true
COMMAND_TYPE: STATUS
MODE: OBSERVE
ACTION_CLASS: A
TARGET: gateway
INTENT: check service and browser status
JUSTIFICATION: daily check
APPROVAL_TOKEN: none
ROLLBACK_REQUIRED: no
POLICY_RESULT: allow
EXECUTION_STATE: normalized
NOTES: read-only request
