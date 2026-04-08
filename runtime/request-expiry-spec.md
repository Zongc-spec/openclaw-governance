# Request Expiry Spec v1

## Purpose
Define when pending requests become stale and invalid.

## Default Rule
Pending requests must not remain valid indefinitely.

## v1 Default Expiry Guidance
- low-risk pending approval request: expires after defined policy window
- protected-target pending approval request: shorter expiry preferred
- any request invalidated by policy change: expires immediately
- any request invalidated by actor revocation: expires immediately

## Revalidation Rule
Expired requests must not be revived by fuzzy approval text.
A new or renewed explicit approval path is required.

## Audit Rule
Expiry and invalidation events must be recorded.
