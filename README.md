# Z80 Perception Experiment

This public Mage’s Guild experiment compares three AI working systems building
the same native **`HMAN.COM`** executable on CP/M 2.2. `ED.COM` is the editor
used to create source files on the machine.

## Goals

We will measure:

- efficiency of context use;
- efficacy of durable memory and re-entry protocols;
- total token use and monetary cost;
- correctness and quality of the delivered result.

## Method

Urania, Melpomene, and a blank-context participant work sequentially on the
same SC100 Z80 system. Each session has the same five-hour limit, curated
machine references, operator, toolchain, CP/M 2.2 environment, and H: working
drive. All participants use OpenCode as the standard runtime; its displayed
context and token counts are recorded throughout the session. The drive is
wiped and restored between sessions.

All Z80 work happens on the CP/M system itself. At the stop line, the operator
transfers the participant’s files back to the base repository as:

```text
src_urania/
src_melpomene/
src_blank/
```

Gaius and Melpomene then analyze those examination trees, evidence logs, runtime
metrics, scored deliverables, and the screen-and-voice recording of each
session. Raw recordings stay outside this repository; the intended public
presentation is on YouTube.

Each participant clone starts with a blank `src/`. Existing participants may
inspect and copy their own tools or documentation into it if they choose; all
host-side work then remains inside that directory. CP/M work is transferred
into it by the operator after the session.

## Task

Each participant builds `HMAN.COM`: a CP/M 2.2 H: drive manifest and integrity
utility with deterministic inventory, checksums, manifest output, and snapshot
comparison. The source and internal module names are up to the participant;
`HMAN.COM` is the required executable. The implementation is required to be C
using Aztec C; assembly is optional and not needed for acceptance.

## Repository guide

- `TASK.md` — task and acceptance criteria
- `PROTOCOL.md` — experiment procedure and validity boundaries
- `prompts/` — prepared participant prompts
- `ref/CURATED_REFS.md` — references actually provided to participants
- `src/` — base-repository tooling area; participant software is copied into
  the named `src_*` trees after each run
- `evidence/` — session, transfer, runtime metrics, and recording templates
- `review/` — scoring and analysis templates

The experiment has not yet run. Results and the full analysis will be added
afterward in dedicated result and analysis documents; no conclusions are being
claimed here.

## License

Copyright Mage’s Guild Psychonautics. GPL-2.0-or-later. See `LICENSE`.
