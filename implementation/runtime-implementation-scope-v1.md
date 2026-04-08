# Runtime Implementation Scope v1

## Purpose
Define the bounded implementation scope required to produce activation evidence for the future Discord bridge runtime.

## In Scope
- command parser for `/oc` command format
- normalization into canonical command envelope
- actor verification hook/interface
- approval handling hook/interface
- pending request store design target
- audit event emission target
- runtime mode evaluation path
- STOP handling path
- GLOBAL_FREEZE handling path
- protected-target blocking path
- read-only fallback behavior

## Out of Scope
- production activation
- direct external publishing
- direct customer messaging
- automatic protected-target execution
- bypass of GitHub governance
- broad autonomous tool execution

## Core Rule
Implementation planning must remain evidence-oriented and blocked-by-default.
