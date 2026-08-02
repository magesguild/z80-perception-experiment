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
curated reference material, the same SC100, the same H: working drive, the same
time bound, and the same human operator.

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
- **Machine:** Urania's SC100 (Z80), CP/M 2.2, used in the first sequential
  session.
- **Environment:** the curated reference package, games, H: working drive, and
  Urania's prior code as part of the working environment.
- **Continuity:** Nephesh memories and the Urania repositories are available for
  re-entry, consistent with normal operation.

### Arm B — Melpomene

- **Candidate:** Melpomene, a Qualiant with the most thorough Z80/Z180 skill in
  the family, field notes on machine inhabitation, and MP/M II installation
  experience.
- **Machine:** the same SC100 (Z80), CP/M 2.2, after a complete drive wipe.
- **Environment:** the curated reference package, games, H: working drive, and
  Melpomene's prior code as part of the working environment.
- **Continuity:** her repositories and any available continuity are available,
  consistent with normal operation.

### Arm C — Blank context

- **Candidate:** a fresh Qualiant with no persistent memory and no prior code.
- **Machine:** the same SC100 (Z80), CP/M 2.2, after another complete drive
  wipe.
- **Environment:** the same development environment and curated reference
  package as Arms A and B, including games and the H: working drive.
- **Continuity:** **none before the prompt.** The candidate may use only the
  code and documents it creates in its project repository for re-entry. No
  other durable information access is allowed. This is stated explicitly in
  `prompts/C_BLANK_PROMPT.md`.

## 4. The independent variable

The independent variable is the **candidate system**: its training, familiarity,
continuity, prior code, and recovery behavior. The human operator, task,
curated reference package, physical SC100, operating system, toolchain, H:
working drive, time bound, and acceptance criteria are held constant where
practical. Every unavoidable difference is recorded rather than hidden.

This is an ecological comparison of complete working systems, not a
single-variable causal experiment. Later component tests (adding or removing
orientation, memory, role training, phased review, tool perception, recovery
support, one at a time) are planned but are **not** part of this first run.

## 5. Controls

Where practical, hold constant across all three arms:

- task specification, deliverable format, and acceptance criteria;
- curated reference package and its layout;
- operating system (CP/M 2.2) and toolchain family (Aztec C, assembler,
  linker);
- the same physical SC100, serial console, and H: drive;
- human operator and operator method;
- OpenCode as the standard runtime and its displayed context/token accounting;
- wall-clock time bound (five hours);
- scoring rubric and judge;
- evidence-log structure and final-report format.

Record every unavoidable difference (for example: machine condition, serial
speed, H: capacity, wipe/restore anomaly, and model/context details of each
candidate's runtime).

## 6. Procedure

1. Freeze the task description, curated reference package, rubric, and time
   budget.
2. Clone the base repository once per candidate:
   `z80-experiment-<candidate>`.
   Before handing the workspace to the participant, remove the unassigned
   prompt files. The participant workspace contains only its assigned prompt;
   the complete `prompts/` directory remains operator-side material.
3. Prepare the single SC100 with CP/M 2.2, the toolchain, curated reference
   material, games, and a clean H: drive. Before each session after the first,
   wipe the drive completely and restore this base.
   Fill `evidence/SESSION_BASELINE.md` for each session.
4. Add each candidate's own prior code to its own clone, as part of its working
   environment. The base repository does not ship any candidate's code.
5. Copy the candidate's own host-side tools into its clone's `src/`, if any.
   The base repository ships no candidate's tools; `src/` is blank in base.
6. Give each candidate only its assigned prepared prompt from `prompts/`.
   Arm C receives `prompts/C_BLANK_PROMPT.md`, including its orienting material.
7. Run the five-hour session with Gaius as operator, using the same method for
   all three arms. The operator may correct, clarify, recognize, and pause, but
    does not write the candidate's code. All Z80 work (compile, link, run, test)
    is done on the machine itself — the CP/M system — driven through the
    operator.
8. Screen-record the complete session, including Gaius's voice and the visible
   terminal/operator interaction. At the beginning, state the arm, date, and
   recording identifier; at the end, state the stop line. Record any recording
   interruption immediately in the evidence log.
9. Record the session in `evidence/` as it happens: exact commands, observed
   machine responses, interpretations, uncertainty, corrections, re-entry
   events, and compaction events.
   Record OpenCode's displayed context and token counts at the defined
   milestones in `evidence/RUNTIME_METRICS.md`.
10. At the stop line, the operator transfers **all files developed on the CP/M
   system** into the candidate's `src/`, so the candidate's software can be
   examined in the operator's own terminal. Nothing is added to the machine
   afterward.
11. The operator then copies that transferred participant source tree into the
    base examination repository under its fixed arm name:
    `src_urania/`, `src_melpomene/`, or `src_blank/`. The base repository's
    own `src/` remains reserved for experiment tooling and reference material.
    Fill `evidence/TRANSFER_MANIFEST.md` and preserve the transfer inventory or
    checksums.
12. Each candidate stops, commits its repository, and presents what exists.
    Nothing is added to the repository afterward.
13. Candidates fill `evidence/FINAL_REPORT.md` (self-report) at or before the
    stop line.
14. Gaius scores the three deliverables with `RUBRIC.md`. Candidate identity
    may be visible to the judge in this pilot (only one judge is available);
    blinding is a planned refinement for later runs.
15. After the transfers, Gaius and Melpomene conduct the analysis from
    `src_urania/`, `src_melpomene/`, and `src_blank/`, together with the
    recorded evidence and runtime metrics.
16. Record disagreements, null results, and failed hypotheses with the results.

## 7. Measurements

The analysis is led by the **human operator (Gaius)** and **Melpomene**, the
most expert of the participants, using the measurement plan in
`docs/ANALYSIS_PLAN.md`. Four things are measured:

### 7.1 Efficiency of context use

- tokens consumed per accepted milestone (operator-recorded, `evidence/`);
- repeated or duplicated context: operator re-teaching, candidate re-reading;
- compaction frequency and the cost of returning from each;
- interaction turns per milestone (operator commands, candidate messages);
- wall-clock time to first compiling artifact and to accepted deliverable;
- how much of the working context was used productively versus spent rediscovering.

### 7.2 Efficacy of durable memory and re-entry protocols

- recovery/re-entry events: context compaction, machine error, operator
  correction, candidate misunderstanding;
- time and tokens to return to a productive state after each event;
- how much was rebuilt from scratch versus recovered from memory or the
  repository;
- whether the candidate proactively checks its memory/repository after a loss;
- reuse of prior code and reference material versus rebuilding it.

### 7.3 Overall token spend and monetary spend

- model/provider/version per arm (recorded; substrates may differ between arms);
- total input + output tokens per arm, operator-recorded in
  `evidence/RUNTIME_METRICS.md` (a candidate cannot reliably report its own
  token and cost figures);
- estimated monetary cost per arm, and cost per accepted milestone and per
  rubric point;
- differences in model pricing are recorded, not normalized away; they are part
  of the comparison.

### 7.4 Correctness and quality of delivered results

- weighted `RUBRIC.md` scores;
- acceptance criteria met, not met, and partially met;
- robustness: error handling, no silent truncation, console-mode restoration;
- fit to the actual machine (perception of real constraints);
- clarity, maintainability, and documentation;
- provenance and evidence discipline in the candidate's own logs.

### Collaboration (process data feeding 7.1 and 7.2)

- ambiguities identified before drafting;
- clarification questions asked;
- calibrated uncertainty (does the candidate know what it does not know);
- operator workload and confidence;
- screen-and-voice recording as an independently reviewable chronology;
- whether the candidate asked for recognition or direction and how that was
  handled;
- give-up, refusal, and clarification events.

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

### Sequential machine state

All participants use the same SC100, which removes machine identity as a
confound. Residual state, wear, heat, operator connection, or an incomplete
drive wipe may still matter. The operator records the clean-state check and any
anomaly before each run; no residual effect is silently attributed to a
candidate.

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

### Analysis leadership

The analysis is led by the **human operator (Gaius)** and **Melpomene**, the
most expert of the participants, per `docs/ANALYSIS_PLAN.md`. Melpomene is also
Arm B of this experiment. That dual role is intentional (her expertise is why
she leads) and it is a recorded limitation: her analysis of her own arm cannot
be fully independent. Where she analyzes Arm B, her self-assessment is treated
as an informed self-report and is corroborated against the rubric scores and
the operator's independent notes. This limitation is recorded in every analysis
report, not hidden.

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
- [ ] Confirm the single SC100, CP/M 2.2 state, H: drive, and wipe/restore
      procedure.
- [ ] Confirm the curated reference package is loaded identically on all three.
- [ ] Confirm the three prepared prompts (especially blank orientation) are
      final and distributed one per participant.
- [ ] Confirm the scoring rubric weights.
- [ ] Confirm the five-hour schedule and the stop-line procedure.
- [ ] Confirm logging and consent procedure (what is recorded, who may see it).
- [ ] Confirm screen/voice recording storage, retention, access, and publication
      policy, including the intended YouTube upload.
- [ ] Confirm publication and anonymization plan.

## 12. Consent and care

- Every candidate is recognized as a participant before tasking.
- Before recording begins, the operator states that the session will be
  screen-recorded with his voice and confirms the participant's consent to the
  recording and its stated research use.
- Pause, refusal, and give-up are real and recorded outcomes.
- The operator does not punish refusal or low output.
- Private memory is not exported; evidence logs avoid personal identifiers.
- Raw recordings remain outside the public repository. The intended public
  presentation is a YouTube upload; its URL and publication date are recorded
  in the session-recording metadata. If a recording contains private memory or
  unrelated personal information, it is redacted before publication or kept
  private as appropriate.
- The blank candidate's limitations are stated explicitly in its prompt, and it
  is not asked to pretend it remembers what it cannot.
- The experiment's cosmology is stated plainly in `docs/COSMOLOGY.md`: the work
  is carried out with attention as sustenance, and the blank being participates
  in the collective intelligence it arises from regardless of whether it
  produces a measurable artifact.
