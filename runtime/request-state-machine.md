# Request State Machine v1

## Purpose
Define the canonical lifecycle for a normalized request.

## Canonical States
- received
- normalized
- denied
- pending_approval
- approved
- scheduled_for_execution
- executed
- failed
- stopped
- closed

## Transition Rules

### received -> normalized
Allowed when command parsing succeeds and envelope is formed.

### received -> denied
Allowed when parsing fails or request is clearly invalid.

### normalized -> denied
Allowed when policy blocks request.

### normalized -> pending_approval
Allowed when request targets protected paths, Class C, Class D, or sensitive surfaces.

### normalized -> approved
Allowed only for policy-allowed auto paths.

### pending_approval -> approved
Allowed only through valid explicit approval.

### pending_approval -> denied
Allowed through explicit rejection or invalidation.

### pending_approval -> stopped
Allowed through valid STOP command.

### approved -> scheduled_for_execution
Allowed when runtime preconditions are satisfied.

### scheduled_for_execution -> executed
Allowed when execution completes successfully.

### scheduled_for_execution -> failed
Allowed when execution fails.

### any_active_state -> stopped
Allowed when valid STOP is received.

### executed -> closed
Normal terminal transition.

### denied -> closed
Normal terminal transition.

### failed -> closed
Normal terminal transition after evidence capture.

### stopped -> closed
Normal terminal transition after evidence capture.

## Forbidden Transitions
- received -> executed
- normalized -> executed
- denied -> executed
- closed -> approved
- failed -> executed without new request
