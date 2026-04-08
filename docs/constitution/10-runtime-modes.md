# Runtime Modes

## MODE 1 — OBSERVE
Read-only only.
No file write.
No outbound message.
No browser form submission.

## MODE 2 — PREPARE
May draft files in approved draft area.
May prepare patch, PR text, issue text, summaries.
No protected target writes.

## MODE 3 — CONTROLLED_EXECUTE
May perform pre-approved write actions in allowed workspace.
Must generate audit record.

## MODE 4 — HIGH_RISK_PENDING
No execution.
Approval request only.
