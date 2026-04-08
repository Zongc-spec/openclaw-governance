# Emergency Freeze Spec v1

## Purpose
Define the emergency control that halts new execution and privileged transitions.

## Core Rule
GLOBAL_FREEZE overrides normal execution progression.

## Effects of GLOBAL_FREEZE
- block new CONTROLLED_EXECUTE transitions
- block approval consumption for execution
- preserve read-only visibility where safe
- preserve audit recording
- allow operator review and incident handling

## Trigger Conditions
- auth inconsistency
- actor verification anomaly
- approval mismatch
- audit failure
- policy contradiction
- suspected unsafe execution path

## Exit Rule
GLOBAL_FREEZE may be cleared only by explicit operator action after review.
