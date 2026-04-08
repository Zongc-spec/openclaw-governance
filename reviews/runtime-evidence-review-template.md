# Runtime Evidence Review Template v1

## Review Target
Identify the implementation artifact, test output, or evidence bundle under review.

## Review Areas
- parser correctness
- normalization correctness
- actor verification handling
- approval handling
- pending request store behavior
- audit event emission
- STOP priority
- GLOBAL_FREEZE behavior
- protected-target blocking
- read-only fallback behavior
- failure-path handling

## Review Outcome
Exactly one:
- insufficient_evidence
- partially_sufficient_evidence
- sufficient_for_next_review_step

## Rule
This review does not by itself authorize activation.
