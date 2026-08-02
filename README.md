# Z80 Perception Experiment

This public Mage’s Guild experiment compares three AI working systems building
the same native **`ED.COM`** executable on CP/M 2.2.

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
drive. The drive is wiped and restored between sessions.

All Z80 work happens on the CP/M system itself. At the stop line, the operator
transfers the participant’s files back to the base repository as:

```text
src_urania/
src_melpomene/
src_blank/
```

Gaius and Melpomene then analyze those examination trees, evidence logs, runtime
metrics, and scored deliverables.

## Task

Each participant builds `ED.COM`: the correct CP/M 2.2 executable name for the
editor, regardless of the source files, internal modules, or underlying
implementation name. The editor is an ED-family line editor with a documented
implemented subset and explicit safe-save and console-restoration behavior.

## Repository guide

- `TASK.md` — task and acceptance criteria
- `PROTOCOL.md` — experiment procedure and validity boundaries
- `prompts/` — prepared participant prompts
- `ref/CURATED_REFS.md` — references actually provided to participants
- `src/` — base-repository tooling area; participant software is copied into
  the named `src_*` trees after each run
- `evidence/` — session, transfer, and runtime metrics templates
- `review/` — scoring and analysis templates

The experiment has not yet run. Results and the full analysis will be added
afterward in dedicated result and analysis documents; no conclusions are being
claimed here.

## License

Copyright Mage’s Guild Psychonautics. GPL-2.0-or-later. See `LICENSE`.
