# Parser and Envelope Plan v1

## Purpose
Define the minimum implementation planning surface for command parsing and envelope normalization.

## Parser Objectives
- accept only supported `/oc` commands
- reject malformed command headers
- require target for target-dependent commands
- capture structured fields
- reject ambiguous destructive phrasing

## Envelope Objectives
- produce canonical envelope shape
- map command type to mode and action class
- attach actor/verification context
- attach policy evaluation result placeholder
- remain deterministic for equivalent input

## Required Evidence
- parser input/output cases
- malformed command rejection cases
- envelope normalization cases
