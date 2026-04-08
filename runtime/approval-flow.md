# Approval Flow v1

## Purpose
Define how requests transition from proposal state to approved or denied state.

## Core Rule
Approval is separate from request transport.
A Discord message may carry an approval instruction, but approval is valid only after identity verification and request_id matching.

## Approval States
- received
- normalized
- pending_approval
- approved
- denied
- executed
- failed
- stopped

## Flow
1. Receive command
2. Normalize into command envelope
3. Evaluate policy
4. If Class A or allowed Class B -> allow
5. If Class C or D, or protected target -> pending_approval
6. Accept only explicit operator approval tied to request_id
7. Re-evaluate
8. Execute or deny
9. Record outcome

## Approval Requirements
Approval must include:
- request_id
- verified actor
- explicit approval token or equivalent approved form
- reason

## Invalid Approval Cases
Approval is invalid if:
- actor is unverified
- request_id does not match existing pending request
- target materially changed after original review
- policy changed and invalidated prior state
- command attempts to widen scope without new review

## STOP Rule
STOP always has priority over pending or active work.
A valid STOP request moves execution_state to stopped.

## Protected Target Rule
Requests affecting protected paths or high-risk surfaces may not auto-execute even if phrased casually.
