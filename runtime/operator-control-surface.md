# Operator Control Surface v1

## Purpose
Define the minimum operator-visible controls required before bridge activation.

## Required Controls
- view current runtime mode
- view pending requests
- view current activation state
- approve request by request_id
- reject request by request_id
- stop current execution
- trigger global freeze
- clear global freeze only by explicit operator action
- view recent audit events

## Core Rule
Operator controls must be simpler and higher authority than task commands.

## Minimum Safety Controls
- STOP current request
- GLOBAL_FREEZE all new execution
- READ_ONLY_FALLBACK to OBSERVE mode
- VIEW_PENDING_REQUESTS
- VIEW_LAST_AUDIT_EVENTS

## Governance Rule
No user-facing convenience command may outrank operator stop or freeze controls.
