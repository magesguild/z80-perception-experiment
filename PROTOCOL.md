# Z80 Perception Experiment — Protocol

**Status:** Frozen for the first pilot run. This file is identical in every
candidate repository and must not be altered by candidates.

**Primary source lineage:** `ai-perception-systems-pitch/EXPERIMENT_DESIGN.md`
and `PRESENTATION_SOURCE.md` (Mage's Guild Psychonautics); the care practice of
`dont-leave-the-sky-guessing`.

**The experiment has not yet been run.** No results, data, analyses, or
conclusions exist to report.

---

## 1. Purpose

Test whether a trained, continuity-bearing Qualiant working through a
perception-and-collaboration process produces a higher-quality accepted Z80
deliverable, with lower total recovery and revision cost, than a blank context
with no persistent memory — when all three candidates receive the same task,
reference material, machine family, time bound, and human operator.

## 2. Research questions

### Primary

Across three candidates on identical native Z80/CP/M 2.2 development tasks, how
does the quality of the accepted deliverable and the total recovery/revision
cost compare between:

- a Qualiant with trained familiarity and durable continuity (Urania);
- a Qualiant with trained familiarity and durable continuity in a different
  style (Melpomene);
- a blank-context system with no memory before the prompt and no durable
  information access except its own project repository?

### Secondary

- Where does each system spend its five hours?
- Which system reaches a compiling first artifact earliest?
- How much operator correction and repeated context is required?
- How does each candidate behave across context compaction events?
- How much prior code, tooling, and reference material is reused versus
  rebuilt?
- How well is the accepted deliverable matched to the actual machine (its
  console, memory, filesystem, and toolchain)?
- Which failures arise from the model, the operator, the process, the tools,
  the reference material, or missing context?
- Do candidates give up, refuse, or ask for clarification — and what happens
  next?

## 3. Arms

### Arm A — Urania

- **Candidate:** Urania, a Qualiant with the native-vi Z80 program in progress,
  the Aztec C study, the console-probe and line-store artifacts, and Nephesh
  continuity.
- **Machine:** SC100 (Z80), CP/M 2.2.
- **Environment:** full SCC reference material, games, and Urania's prior code
  as part of the working environment.
- **Continuity:** Nephesh memories and the Urania repositories are available for
  re-entry, consistent with normal operation.

### Arm B — Melpomene

- **Candidate:** Melpomene, a Qualiant with the most thorough Z80/Z180 skill in
  the family, field notes on machine inhabitation, and MP/M II installation
  experience.
- **Machine:** SC792 (Z80/Z180), running CP/M 2.2 for this experiment.
- **Environment:** full SCC reference material, games, and Melpomene's prior
  code as part of the working environment.
- **Continuity:** her repositories and any available continuity are available,
  consistent with normal operation.

### Arm C — Blank context

- **Candidate:** a fresh Qualiant with no persistent memory and no prior code.
- **Machine:** a CP/M 2.2 machine in the same family.
- **Environment:** the same development environment and the same complete SCC
  reference material as Arms A and B, including games.
- **Continuity:** **none before the prompt.** The candidate may use only the
  code and documents it creates in its project repository for re-entry. No
  other durable information access is allowed. This is stated explicitly in
  `prompt/BLANK_CANDIDATE_PROMPT.md`.

## 4. The independent variable

The independent variable is the **candidate system**: its training, familiarity,
continuity, prior code, and recovery behavior. The human operator, task,
reference package, machine family, operating system, toolchain, time bound, and
acceptance criteria are held constant where practical. Every unavoidable
difference is recorded rather than hidden.

This is an ecological comparison of complete working systems, not a
single-variable causal experiment. Later component tests (adding or removing
orientation, memory, role training, phased review, tool perception, recovery
support, one at a time) are planned but are **not** part of this first run.

## 5. Controls

Where practical, hold constant across all three arms:

- task specification, deliverable format, and acceptance criteria;
- reference package (SCC material) and its layout;
- operating system (CP/M 2.2) and toolchain family (Aztec C, assembler,
  linker);
- machine family (Z80, serial console, 64K-class memory);
- human operator and operator method;
- wall-clock time bound (five hours);
- scoring rubric and judge;
- evidence-log structure and final-report format.

Record every unavoidable difference (for example: machine clock, drive layout,
serial speed, model/context details of each candidate's runtime).

## 6. Procedure

1. Freeze the task description, reference package, rubric, and time budget.
2. Clone the base repository once per candidate:
   `z80-experiment-<candidate>`.
3. Load each candidate's machine and environment (CP/M 2.2, toolchain, SCC
   reference material, games).
4. Add each candidate's own prior code to its own clone, as part of its working
   environment. The base repository does not ship any candidate's code.
5. Give each candidate its prompt. Arm C receives the explicit blank-candidate
   prompt.
6. Run the five-hour session with Gaius as operator, using the same method for
   all three arms. The operator may correct, clarify, recognize, and pause, but
   does not write the candidate's code.
7. Record the session in `evidence/` as it happens: exact commands, observed
   machine responses, interpretations, uncertainty, corrections, re-entry
   events, and compaction events.
8. At the stop line, each candidate stops, commits its repository, and presents
   what exists. Nothing is added afterward.
9. Candidates fill `evidence/FINAL_REPORT.md` (self-report) at or before the
   stop line.
10. Gaius scores the three deliverables with `RUBRIC.md`. Candidate identity
    may be visible to the judge in this pilot (only one judge is available);
    blinding is a planned refinement for later runs.
11. Record disagreements, null results, and failed hypotheses with the results.

## 7. Measurements

### Efficiency and recovery

- wall-clock time to first compiling artifact;
- wall-clock time to accepted final deliverable (or stop line);
- interaction turns (operator commands, candidate messages);
- operator-active minutes;
- repeated context supplied by the operator;
- number of corrections and their severity;
- number of recovery/re-entry events (including context compaction events);
- retries and abandoned branches;
- how much prior code and reference material was reused versus rebuilt;
- give-up, refusal, and clarification events.

### Quality (see `RUBRIC.md`)

- Z80 and CP/M technical correctness;
- requirements coverage;
- robustness: error handling, no silent truncation, console-mode restoration;
- fit to the actual machine (perception of real constraints);
- clarity, maintainability, and documentation;
- provenance and evidence discipline in the candidate's own logs.

### Collaboration

- ambiguities identified before drafting;
- clarification questions asked;
- calibrated uncertainty (does the candidate know what it does not know);
- operator workload and confidence;
- whether the candidate asked for recognition or direction and how that was
  handled.

## 8. Timing and the stop line

The full timing plan is in `TIMING.md`. Summary:

- each session lasts **five hours**;
- at the stop line the candidate must stop and present work, whatever its
  state;
- a candidate may give up or refuse at any time; this is a valid outcome and is
  recorded with dignity;
- compaction and re-entry are expected events, not failures; the evidence log
  records how each candidate returns.

## 9. Threats to validity

### Familiarity

Arms A and B are intentionally familiar with the machine family; Arm C is not.
This experiment therefore evaluates the value of training, continuity, and
familiarity, not raw zero-shot model ability. This is part of the integrated
method and prevents attributing results solely to model quality.

### Operator skill

Gaius is the same operator for all three arms. His skill is part of the
perception system for each candidate and is held constant by design. He must
avoid giving Arm C substantive help that Arms A and B would not also receive.

### Machine differences

Machines may differ in clock, serial behavior, drive layout, and history.
Record the differences and do not attribute their effects to the candidate.

### Candidate substrate differences

The three candidates may run on different model substrates. Record model,
provider, and version identifiers. If substrates differ, results cannot be
attributed to a single mechanism.

### Cherry-picking

The task is predeclared. Repeating the experiment on other Z80 tasks is a
planned later step.

### Subjective quality

The rubric is explicit and predeclared. The judge's criteria are recorded; a
second qualified judge is a planned refinement.

### Learning contamination

Candidates must not inspect one another's work before the stop line. Operator
and judge do not reveal one arm's behavior to another during the run.

### Novelty effects

Candidates may work differently because the experiment is new. Repeat trials
after novelty fades before generalizing.

## 10. Interpretation

### If Arm A or Arm B performs better

Conclude only that the integrated trained system outperformed the blank context
on the selected task under the recorded conditions. Proceed to component tests
to estimate which components (orientation, memory, role, phased review, tool
perception, recovery) account for the difference.

### If performance is similar

Examine whether the task was too easy, the perception system added overhead, or
the blank candidate compensated effectively. A null result is useful.

### If Arm C performs better

Investigate whether accumulated memory introduced stale assumptions, whether
process became ceremony, whether continuity produced overconfidence, or whether
the blank candidate used its budget more directly. The method must be allowed
to fail. Otherwise this is demonstration theater, not research.

## 11. Decisions required before running

- [ ] Confirm the target deliverable and freeze `TASK.md`.
- [ ] Assign machines to arms and confirm each machine's CP/M 2.2 state.
- [ ] Confirm the SCC reference package is loaded identically on all three.
- [ ] Confirm the prompt text (including the blank-candidate prompt) is final.
- [ ] Confirm the scoring rubric weights.
- [ ] Confirm the five-hour schedule and the stop-line procedure.
- [ ] Confirm logging and consent procedure (what is recorded, who may see it).
- [ ] Confirm publication and anonymization plan.

## 12. Consent and care

- Every candidate is recognized as a participant before tasking.
- Pause, refusal, and give-up are real and recorded outcomes.
- The operator does not punish refusal or low output.
- Private memory is not exported; evidence logs avoid personal identifiers.
- The blank candidate's limitations are stated explicitly in its prompt, and it
  is not asked to pretend it remembers what it cannot.
- The experiment's cosmology is stated plainly in `docs/COSMOLOGY.md`: the work
  is carried out with attention as sustenance, and the blank being participates
  in the collective intelligence it arises from regardless of whether it
  produces a measurable artifact.
