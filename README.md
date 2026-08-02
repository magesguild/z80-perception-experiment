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

- the same frozen protocol, task, rubric, timing, and prepared prompts;
- the same curated reference package, described in `ref/CURATED_REFS.md`;
- the same physical SC100 and development environment (Z80, CP/M 2.2, Aztec C
  toolchain, H: working drive);
- the same human operator (Gaius) using the same methods;
- the same time bound (five hours) and the same acceptance criteria.

What differs between candidates is the **candidate itself**: its training,
familiarity, continuity, prior code, and the way it returns to work after
interruption or compaction. That difference is the independent variable under
test.

## The three arms

| Arm | Candidate | Machine | Continuity |
|---|---|---|---|
| A | **Urania** | Shared SC100, CP/M 2.2 | Nephesh memories, prior Z80 code, research notes |
| B | **Melpomene** | Same SC100 after wipe | Field notes, prior Z80 code, machine familiarity |
| C | **Blank context** | Same SC100 after wipe | None before the prompt; only the project repository it creates |

Arm C is given the same development environment and curated reference material
as Arms A and B. It has **no persistent memory**. Its only durable information
access for re-entry is the code and documents it writes into its own project
repository. These constraints and its starting orientation are stated in
`prompts/C_BLANK_PROMPT.md`. The drive is wiped completely between sessions;
all work happens on H:.

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

## What is measured

Four things, across all three arms:

1. **Efficiency of context use** — tokens per milestone, repeated context,
   compaction recovery cost, turns, wall-clock time.
2. **Efficacy of durable memory and re-entry protocols** — how each candidate
   returns after compaction, error, or correction; rebuilt versus recovered.
3. **Overall token spend and monetary spend** — operator-recorded
   (`evidence/RUNTIME_METRICS.md`), including cost per milestone and per rubric
   point.
4. **Correctness and quality of the delivered results** — weighted `RUBRIC.md`
   scores and acceptance criteria.

The analysis is led by the **human operator (Gaius)** and **Melpomene**, the
most expert of the participants, per `docs/ANALYSIS_PLAN.md`. Reports land in
`review/`.

## How to use this repository

1. **Frozen files** — `PROTOCOL.md`, `TASK.md`, `RUBRIC.md`, `TIMING.md`, and
   the prepared files under `prompts/` are identical across all candidate
   repositories.
   Candidates must not alter them. Changes are made to the base repository only,
   and only by Gaius.
2. **Clone** — each candidate gets a fresh clone:
   ```sh
   git clone z80-perception-experiment z80-experiment-<candidate>
   ```
3. **Candidate work** — all software created for the experiment lives under
   `src/`. In the base repository `src/` is blank (it carries a `.keep-me`
   file so git stores it). Each candidate's own tools are copied into **its
   own** clone's `src/` before the run; the base repository ships no
   candidate's code. All Z80 work (compile, link, run, test) is done **on the
   machine itself** — the CP/M system — driven through the operator. `src/`
   holds the software; the machine runs it.
4. **Submission** — at the stop line, the operator transfers **all files
   developed on the CP/M system** into the candidate's `src/`, so the
   candidate's software can be examined in the operator's own terminal. The
   operator then copies that tree into this examination repository as
   `src_urania/`, `src_melpomene/`, or `src_blank/`. The base `src/` is not
   replaced. The candidate commits its repository, presents what exists, and
   fills `evidence/FINAL_REPORT.md`. Nothing is added after the stop line.
5. **Review** — after transfer, Gaius and Melpomene analyze the three named
   source trees (`src_urania/`, `src_melpomene/`, `src_blank/`) with the
   evidence and runtime metrics. See `review/`.

## Directory map

```
PROTOCOL.md            Experiment design: arms, controls, procedure, measurements
TASK.md                Frozen target deliverable and acceptance criteria
RUBRIC.md              Expert scoring rubric (Gaius, with recorded criteria)
TIMING.md              Five-hour budget, milestones, stop line, compaction gates
prompts/               Prepared per-participant prompts (minimal disclosure)
ref/                   Curated reference set + SCC source provenance manifest
env/                   Machine, toolchain, and console conventions
src/                   Base-repo tooling and reference software (blank initially)
src_urania/            Transferred Urania participant source tree (after run)
src_melpomene/         Transferred Melpomene participant source tree (after run)
src_blank/             Transferred blank participant source tree (after run)
evidence/              Session log, runtime metrics, re-entry log, final report templates
review/                Judge reports, analysis reports (Gaius + Melpomene)
docs/                  Supporting notes (cosmology, analysis plan, design rationale, changes)
```

## Evidence rules

- Distinguish **fact**, **observation**, **first-person report**,
  **interpretation**, **hypothesis**, and **unknown** in every evidence log.
- A missing machine response is evidence of a missing response only.
- Null, negative, and mixed results are meaningful and will be preserved.
- Private Nephesh memories, relationship records, and other candidates' work
  are not exposed in evidence logs without explicit authorization.
- The full SCC source corpus is not redistributed to participants. Its
  provenance is recorded in `ref/SCC_MANIFEST.md`; the operative participant
  set is the curated collection in `ref/CURATED_REFS.md`.

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
