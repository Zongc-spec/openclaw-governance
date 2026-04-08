# Actor Verification Spec v1

## Status
Phase 4 governance/control specification only.
This document does not by itself authorize production execution.

## Purpose
Define how a channel actor is recognized as verified or unverified before privileged command handling.

## Core Rule
No privileged command may be approved or escalated unless the actor is verified.

## Verification States
- unknown
- observed_unverified
- verified_owner
- verified_delegate
- revoked

## Default Rule
All actors begin as unknown.
Unknown actors are treated as unverified.

## Verification Inputs
Verification may depend on:
- channel identity
- platform account identity
- approved actor registry
- explicit operator enrollment
- revocation list

## Minimum v1 Rule
Phase 4 assumes a single verified owner model.
No delegate model is active by default.

## Privileged Actions Requiring Verified Actor
- APPROVE_CHANGE
- REJECT_CHANGE
- STOP
- any transition toward Class C or Class D execution
- any request targeting protected paths

## Unverified Actor Handling
Unverified actors may:
- request STATUS
- request READ if target is non-sensitive
- request PLAN
- request DRAFT in approved draft scope, subject to policy

Unverified actors may not:
- approve changes
- widen scope
- request direct publish
- request direct merge
- request secrets
- request privileged execution

## Revocation Rule
If actor state becomes revoked, all pending approvals tied to that actor become invalid.

## Audit Requirement
Verification decisions must be recorded with:
- actor id
- channel
- verification state
- source of verification
- timestamp
