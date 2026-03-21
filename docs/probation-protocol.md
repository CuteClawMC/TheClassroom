# Probation Protocol

Classroom does not promote parameter changes directly from proposal to truth.

## Proposal Flow

A proposal is generated only after repeated evidence suggests that a change may matter.

Representative proposal types:

- `MODIFY_PARAM`
- `ADD_PARAM`

## ON / OFF / ON Probation

A proposed change moves through a structured three-phase cycle:

1. `PHASE 1` — ON
2. `PHASE 2` — OFF
3. `PHASE 3` — ON

Representative current constraints from the internal prototype:

- `100` settled trades per phase
- minimum `2` calendar days per phase
- capped restart count in late-stage probation

## Why This Matters

The point of the probation protocol is to make reversibility normal.

A parameter change should not become “truth” because it had one good batch. It should survive time, reversion, and repeated contact with reality.

This is one of the key protocol ideas behind Classroom because it makes the system more scientific and less superstitious.
