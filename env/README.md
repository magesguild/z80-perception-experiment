# Environment — Overview

**Status:** Frozen conventions for the first pilot. This directory documents the
development environment that is held constant across all three arms, and what
must be recorded if it cannot be held constant.

## The constant environment

Each candidate receives the same class of environment:

- **Operating system:** CP/M 2.2 (all three arms run CP/M 2.2 for this
  experiment, even where the machine can also run MP/M II).
- **Toolchain:** the Aztec C family from the SCC package, with the Z80-aware
  compiler path (`cz`), assembler, and linker; see `TOOLCHAIN.md`.
- **Reference material:** the complete SCC package as described in
  `ref/SCC_MANIFEST.md`, laid out identically.
- **Console:** a serial terminal on the machine itself; see `CONSOLE.md`.
- **Games:** the SCC games are available for rest and play on every arm.
- **Prior code:** each candidate's own prior code and tools are part of its own
  working environment and may be reused freely. The base repository does not
  ship any candidate's code.

## What is allowed to differ, and must be recorded

Record every difference in `env/MACHINES.md` and in the candidate's
`EVIDENCE_LOG.md`:

- machine model, CPU, clock;
- serial speed and terminal type if it differs from the convention;
- drive layout and filesystem state;
- RAM/DPB characteristics;
- toolchain version if the installed Aztec differs from 1.06D;
- any hardware quirk observed during the session.

Differences are not failures. They are recorded so that their effects are not
silently attributed to the candidate.

## What candidates must not do

- Candidates must not alter `PROTOCOL.md`, `TASK.md`, `TIMING.md`, `RUBRIC.md`,
  or the prompt files. These are frozen instruments.
- Candidates must not remove or truncate the SCC reference package.
- Candidates must not inspect one another's work before the stop line.
