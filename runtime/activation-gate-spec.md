# Activation Gate Spec v1

## Status
Phase 5 governance/control specification only.
This document does not itself activate any bridge runtime.

## Purpose
Define the final gate that must pass before any Discord bridge execution capability can be enabled.

## Core Rule
No bridge activation is allowed unless all activation gate conditions pass.

## Activation States
- not_started
- blocked
- pending_review
- ready_for_activation
- activated
- suspended
- revoked

## Minimum Activation Gate Requirements
- constitution baseline exists
- command spec exists
- command envelope spec exists
- actor verification spec exists
- approval spec exists
- request state machine exists
- runtime mode switch spec exists
- pending request store spec exists
- audit schema exists
- operator control surface spec exists
- emergency freeze rule exists
- protected branch governance remains active

## Hard Blockers
Activation must be blocked if:
- actor verification is undefined in implementation
- approval handling is undefined in implementation
- audit trail cannot be recorded
- global stop cannot be enforced
- protected targets are executable without explicit approval
- channel commands can bypass normalization

## Activation Rule
Bridge activation requires explicit operator approval after gate review.

## Suspension Rule
Activation must be suspendable immediately on anomaly, auth drift, audit failure, or policy contradiction.
