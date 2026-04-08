# Approval Token Spec v1

## Status
Phase 4 governance/control specification only.

## Purpose
Define the minimum structure and handling rules for explicit approvals.

## Core Rule
Approval must be explicit, request-bound, actor-bound, and non-transferable.

## Minimum Approval Fields
- request_id
- actor
- actor_verified
- approval_decision
- reason
- timestamp

## Approval Decisions
- approve
- reject
- stop

## v1 Token Principle
In Phase 4, "approval token" is a governance concept, not yet a cryptographic primitive.
It is an explicit approval record bound to a specific request_id.

## Valid Approval Conditions
Approval is valid only if:
- request_id exists
- request is in pending_approval state
- actor is verified
- request target has not materially changed
- request scope has not widened
- approval is within policy

## Invalid Approval Conditions
Approval is invalid if:
- actor is unverified
- request_id is unknown
- request is already closed
- target changed after review
- policy version changed and invalidated state
- approval text is ambiguous

## STOP Priority
A valid stop decision overrides prior approval and blocks further execution.

## Audit Requirement
Every approval event must record:
- request_id
- actor
- decision
- timestamp
- reason
- policy version
