# Audit Record Schema v1

## Purpose
Define the canonical audit record structure for non-read operations and important control events.

## Required Record Fields
- audit_id
- timestamp
- request_id
- actor
- actor_verified
- channel
- command_type
- mode
- action_class
- target
- intent
- policy_result
- execution_state
- decision
- reason
- policy_version

## Optional Record Fields
- approval_reference
- rollback_reference
- error_code
- error_summary
- notes

## Audit Classes
- request_received
- request_normalized
- policy_denied
- pending_approval
- approval_recorded
- rejection_recorded
- stop_recorded
- execution_started
- execution_succeeded
- execution_failed
- request_closed
- activation_state_changed

## Core Rule
Audit records must be append-oriented and must not silently overwrite prior state.

## Minimum Retention Principle
Protected-target and approval-related events must always remain auditable.
