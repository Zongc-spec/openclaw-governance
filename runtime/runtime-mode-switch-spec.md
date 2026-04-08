# Runtime Mode Switch Spec v1

## Purpose
Define how runtime mode changes are governed.

## Runtime Modes
- OBSERVE
- PREPARE
- CONTROLLED_EXECUTE
- HIGH_RISK_PENDING

## Default Mode
Default runtime mode is OBSERVE.

## Core Rule
Mode transitions must be explicit, policy-compliant, and auditable.

## Allowed Default Transitions
- OBSERVE -> PREPARE
- PREPARE -> OBSERVE
- PREPARE -> HIGH_RISK_PENDING
- HIGH_RISK_PENDING -> PREPARE
- HIGH_RISK_PENDING -> OBSERVE

## Restricted Transitions
- OBSERVE -> CONTROLLED_EXECUTE requires explicit approval and satisfied runtime preconditions
- PREPARE -> CONTROLLED_EXECUTE requires explicit approval and satisfied runtime preconditions
- CONTROLLED_EXECUTE -> HIGH_RISK_PENDING allowed on policy escalation or anomaly
- CONTROLLED_EXECUTE -> OBSERVE allowed on stop/rollback/close

## Runtime Preconditions for CONTROLLED_EXECUTE
- verified actor context
- valid request state
- valid approval if required
- approved target
- audit path available
- rollback path defined where applicable

## Fail-Closed Rule
If current mode is unknown or transition validation fails, remain in safest lower mode.
