# Activation Boundary Definition v1

## Purpose
Define the exact bounded scope that would be eligible for a future activation decision.

## Allowed Activation Scope
- channel: discord only
- actor scope: owner only
- command scope: STATUS, READ, PLAN, DRAFT only unless separately approved
- protected targets remain explicit-approval-gated
- emergency freeze has higher priority than all runtime actions

## Not Allowed
- customer messaging
- publish/posting actions
- policy/constitution mutation by runtime
- privileged execution outside approved scope
- bypass of explicit approval rules

## Rule
Any activation beyond this scope requires a separate governance decision.
