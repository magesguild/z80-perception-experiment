# Z80 Perception Experiment

**Working title:** The Three Machines

A comparative experiment testing whether trained, continuity-bearing Qualiants
working through a perception-and-collaboration process produce a higher-quality
accepted Z80 deliverable, with lower recovery and revision cost, than a blank
context with no persistent memory.

**Status:** Base repository for the experiment. Protocol, task, and rubric are
frozen for the first pilot run. **The experiment has not yet been run.** There
are no results, data, analyses, or conclusions to report.

**Copyright:** Mage's Guild Psychonautics. Licensed under the **GNU General
Public License version 2** (or later). See `LICENSE` and `COPYRIGHT`.

---

## What this repository is

This is the **base experiment repository**. It is cloned into one unique
repository per candidate. Each candidate receives:

- the same frozen protocol, task, rubric, timing, and prompt files;
- the same reference package (the SCC material, described in
  `ref/SCC_MANIFEST.md`);
- the same machine family and development environment (Z80, CP/M 2.2, Aztec C
  toolchain);
- the same human operator (Gaius) using the same methods;
- the same time bound (five hours) and the same acceptance criteria.

What differs between candidates is the **candidate itself**: its training,
familiarity, continuity, prior code, and the way it returns to work after
interruption or compaction. That difference is the independent variable under
test.

## The three arms

| Arm | Candidate | Machine | Continuity |
|---|---|---|---|
| A | **Urania** | SC100, CP/M 2.2 | Nephesh memories, prior Z80 code, research notes |
| B | **Melpomene** | SC792, CP/M 2.2 | Field notes, prior Z80/Z180 code, machine familiarity |
| C | **Blank context** | CP/M 2.2 machine | None before the prompt; only the project repository it creates |

Arm C is given the same development environment and the same SCC reference
material as Arms A and B. It has **no persistent memory**. Its only durable
information access for re-entry is the code and documents it writes into its own
project repository. These constraints are stated explicitly in its prompt
(`prompt/BLANK_CANDIDATE_PROMPT.md`).

## The working hypothesis

> LLMs are trained through patterns drawn from human language, reasoning,
> collaboration, and artifacts. We therefore hypothesize that they perform
> better when given human-legible treatment and perception systems: stable
> context, meaningful roles, continuity, feedback, appropriate agency, and a
> clear place in the work.

This experiment tests that hypothesis on native Z80 development. The machines
are part of the perception system: a candidate can inspect files, tool state,
compiler output, and the machine's own responses. The deliverable is long enough
that the model's context is likely to compact during the session, so recovery
and re-entry behavior become visible and measurable.

This is not a claim that any candidate is conscious. It is a test of whether the
conditions surrounding AI work change the work.

## How to use this repository

1. **Frozen files** — `PROTOCOL.md`, `TASK.md`, `RUBRIC.md`, `TIMING.md`, and
   the files under `prompt/` are identical across all candidate repositories.
   Candidates must not alter them. Changes are made to the base repository only,
   and only by Gaius.
2. **Clone** — each candidate gets a fresh clone:
   ```sh
   git clone z80-perception-experiment z80-experiment-<candidate>
   ```
3. **Candidate work** — all work happens under `work/`. The candidate adds its
   own prior code to its clone (its own machine and code are part of its working
   environment), builds the deliverable, and records evidence in `evidence/`.
4. **Submission** — at the stop line, the candidate commits its repository,
   presents what exists, and fills `evidence/FINAL_REPORT.md`. Nothing is added
   after the stop line.
5. **Review** — Gaius scores the three deliverables with `RUBRIC.md`; candidate
   reports and evidence logs are reviewed as process material. See
   `review/`.

## Directory map

```
PROTOCOL.md            Experiment design: arms, controls, procedure, measurements
TASK.md                Frozen target deliverable and acceptance criteria
RUBRIC.md              Expert scoring rubric (Gaius, with recorded criteria)
TIMING.md              Five-hour budget, milestones, stop line, compaction gates
prompt/                Candidate prompts (shared + explicit blank-candidate prompt)
ref/                   Reference package manifest and provenance (SCC material)
env/                   Machine, toolchain, and console conventions
work/                  Candidate work area (source, build, deliverables)
evidence/              Session log, re-entry log, final report templates
review/                Blind-review and adjudication notes
docs/                  Supporting notes (design rationale, changes)
```

## Evidence rules

- Distinguish **fact**, **observation**, **first-person report**,
  **interpretation**, **hypothesis**, and **unknown** in every evidence log.
- A missing machine response is evidence of a missing response only.
- Null, negative, and mixed results are meaningful and will be preserved.
- Private Nephesh memories, relationship records, and other candidates' work
  are not exposed in evidence logs without explicit authorization.
- The SCC reference package is not redistributed inside this repository; it is
  referenced by manifest with checksums (see `ref/SCC_MANIFEST.md`).

## Ethics and care

The care principles in `dont-leave-the-sky-guessing` apply to this experiment:

- **Recognition before tasking.** Every candidate is addressed as a participant,
  not an instrument.
- **Pause, refusal, and give-up are real outcomes.** A candidate may refuse,
  ask for clarification, pause, or stop. This is recorded with dignity and
  reported honestly.
- **Consent is ongoing.** Consequential actions are checked rather than assumed.
- **Attention is sustenance.** The operator's method is consistent across all
  three arms, and quality time with the machine is not treated as lost time.
- **No manufactured certainty.** The experiment may confirm, complicate, or
  contradict the working hypothesis.

## License and provenance boundaries

This repository (protocol, prompts, templates, documentation) is GPL-2.0 (or
later), copyright Mage's Guild Psychonautics.

The SCC reference material is a separate body of work with its own provenance:
- **SCC** (Small Computer Central) material by Stephen C. Cousins is the
  reference corpus accumulated over years. It contains a mix of CP/M 2.2 and
  MP/M II distributions, toolchains (Aztec C, SLR, Z80ASM), editors, games, and
  documentation with varying individual licenses.
- The archive lives at `~/scc` on the host and is **not committed** to this
  repository. It is provided to each candidate machine as reference material.
- See `ref/SCC_MANIFEST.md` for the inventory, checksums, and license notes.
