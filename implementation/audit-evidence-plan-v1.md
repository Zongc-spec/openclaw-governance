# Audit Evidence Plan v1

## Purpose
Define the minimum proof required for auditability.

## Required Audit Events
- request_received
- request_normalized
- policy_denied
- pending_approval
- approval_recorded
- stop_recorded
- execution_started
- execution_succeeded
- execution_failed
- request_closed
- activation_state_changed

## Required Evidence
- event schema output examples
- append behavior examples
- failure-path audit examples
- freeze-path audit examples

## Rule
If meaningful audit events cannot be produced, activation remains blocked.
