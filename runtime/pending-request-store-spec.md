# Pending Request Store Spec v1

## Purpose
Define the minimum governance rules for storing pending requests awaiting approval.

## Core Rule
Only normalized requests in pending_approval state may enter the pending request store.

## Minimum Stored Fields
- request_id
- timestamp
- actor
- actor_verified
- channel
- command_type
- target
- normalized_intent
- action_class
- mode
- policy_result
- current_state
- policy_version

## Store Rules
- request_id must be unique
- store entries must be append-safe
- state changes must be recorded
- closed requests must not remain pending
- protected-target requests must retain history

## Invalidation Rules
Pending requests become invalid if:
- actor is revoked
- target changes materially
- policy version changes incompatibly
- request expires under future expiry rule
- STOP is applied

## Retrieval Rule
Approvals must resolve against request_id, not fuzzy text matching.

## Audit Rule
Every insert, update, invalidation, and close event must be auditable.
