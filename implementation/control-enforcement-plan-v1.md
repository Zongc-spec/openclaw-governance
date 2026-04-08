# Control Enforcement Plan v1

## Purpose
Define the planning surface for enforcing governance controls in runtime.

## Required Controls
- STOP takes priority over active work
- GLOBAL_FREEZE blocks new privileged progression
- protected targets require explicit approval
- CONTROLLED_EXECUTE requires satisfied preconditions
- unknown actor cannot approve
- read-only mode remains available during freeze where safe

## Required Evidence
- stop override test evidence
- freeze enforcement test evidence
- protected-target denial evidence
- approval-required enforcement evidence
