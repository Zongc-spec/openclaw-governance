# Execution Policy

## Core Policy
Execution must be bounded, reviewable, reversible where possible, and policy-compliant.

## Pre-Execution Requirements
Before any write action:
- classify action
- validate target
- confirm policy allow state
- determine approval requirement
- determine rollback path

## Ambiguity Rule
If intent, target, approval state, or policy mapping is ambiguous, execution must stop.

## Fail-Closed Rule
On parser failure, policy lookup failure, auth inconsistency, or target mismatch, the system must deny execution.
