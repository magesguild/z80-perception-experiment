# Environment — Overview

**Status:** Frozen conventions for the first pilot. This directory documents the
development environment that is held constant across all three arms, and what
must be recorded if it cannot be held constant.

## The constant environment

Each candidate receives the same environment on the same physical machine:

- **Machine:** Urania's SC100, used sequentially for all three sessions.
- **Operating system:** CP/M 2.2 (all three arms run CP/M 2.2 for this
  experiment).
- **Toolchain:** the Aztec C family from the SCC package, with the Z80-aware
  compiler path (`cz`), assembler, and linker; see `TOOLCHAIN.md`.
- **Reference material:** the curated package in `ref/CURATED_REFS.md`, laid
  out identically.
- **Console:** a serial terminal on the machine itself; see `CONSOLE.md`.
- **Working drive:** H:.
- **Games:** available for rest and play on every arm.
- **Prior code:** each candidate's own prior code and tools are part of its own
  working environment and may be reused freely. The base repository does not
  ship any candidate's code.

The operator wipes the drive completely between sessions and restores the clean
base. No participant inherits machine files from a prior participant.

## What is allowed to differ, and must be recorded

Record every difference in `env/MACHINES.md` and in the candidate's
`EVIDENCE_LOG.md`:

- SC100 condition, CPU, clock, and memory map;
- serial speed and terminal type if it differs from the convention;
- H: drive state and capacity;
- RAM/DPB characteristics;
- toolchain version if the installed Aztec differs from 1.06D;
- any hardware quirk observed during the session.

Differences are not failures. They are recorded so that their effects are not
silently attributed to the candidate.

## What candidates must not do

- Candidates must not alter `PROTOCOL.md`, `TASK.md`, `TIMING.md`, `RUBRIC.md`,
  or the prepared prompts. These are frozen instruments.
- Candidates must not remove or truncate the curated reference package.
- Candidates must not inspect one another's work before the stop line.
