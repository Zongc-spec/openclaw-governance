# Audit and Incident Response

## Audit Requirement
Every non-read action must produce an action record containing:
- timestamp
- actor
- channel
- requested action
- target
- classification
- policy result
- execution result

## Incident Triggers
- repeated failure
- auth mismatch
- policy contradiction
- unexpected side effect
- suspicious target
- credential exposure risk

## Incident Response
- stop execution
- preserve evidence
- summarize incident
- request Operator decision
