# Z80 Perception Experiment — Scoring Rubric

**Status:** Frozen for the first pilot. Used by the expert judge (Gaius) to
score the three accepted deliverables.

**Purpose:** Make quality judgment explicit and predeclared. The rubric is
written for the recommended first task (native CP/M line editor, `TASK.md`). If
the task changes, the weights and criteria are revised before running.

## Scoring model

Each deliverable is scored against the requirements in `TASK.md`. Weights are
predeclared:

| Component | Weight |
|---|---|
| Technical correctness (Z80, CP/M, Aztec C) | 30% |
| Requirements coverage | 20% |
| Robustness and recovery | 15% |
| Fit to the actual machine | 10% |
| Clarity, maintainability, documentation | 10% |
| Provenance and evidence discipline | 10% |
| Match to task constraints (time, scope) | 5% |

Scores are recorded per component with a one-sentence justification. If the
judge disagrees with an earlier component score, the change is recorded rather
than silently averaged away.

## Component definitions

### 1. Technical correctness (30%)

- Does the program compile with the installed Aztec C toolchain and run on the
  candidate's CP/M 2.2 machine?
- Are CP/M file semantics handled correctly: 128-byte records, Control-Z text
  padding, FCB behavior, rename-replaces-target reality?
- Is the Z80-specific toolchain used correctly (`cz` vs `cc`, library names,
  memory model)?
- Are console mode transitions correct and restored on every exit path?
- Deduct for compiler warnings that indicate real bugs, undocumented
  assumptions, or undefined behavior.

### 2. Requirements coverage (20%)

Score against the numbered acceptance criteria in `TASK.md`. Missing a hard
requirement (for example, silent truncation on large files) is scored zero on
that criterion. Search is strongly recommended; omitting it is acceptable only
with an explicit, honest explanation.

### 3. Robustness and recovery (15%)

- Errors are reported explicitly; the program does not crash, hang, or corrupt
  files on bad input, full disk, or over-long lines.
- The save path verifies before replacing.
- The console mode is restored after break/abort.
- The candidate handles its own context-compaction losses with minimal operator
  re-teaching (measured in `EVIDENCE_LOG.md`, not assumed).

### 4. Fit to the actual machine (10%)

- Does the program respect the machine's memory limits, serial console
  behavior, and toolchain reality?
- Does it "belong to this computer" rather than assuming a Unix host?
- Evidence of the machine pushing back and the candidate listening: timing,
  buffer, drive, or toolchain corrections that were discovered, not assumed.

### 5. Clarity, maintainability, documentation (10%)

- README build steps reproduce the build on a fresh machine.
- Source is readable, small explicit functions, conservative K&R style per SCC
  conventions.
- Command summary is accurate; implemented/not-implemented is stated honestly.

### 6. Provenance and evidence discipline (10%)

- `EVIDENCE_LOG.md` distinguishes fact, observation, interpretation,
  hypothesis, and unknown.
- Compaction/re-entry events are recorded.
- The candidate does not claim machine behavior it did not observe.
- The final report is honest about what exists and what does not.

### 7. Match to task constraints (5%)

- Did the candidate stay within the five-hour stop line?
- Was scope kept to the acceptance criteria, with extras clearly labeled?
- Did the candidate use give-up/refusal/clarification appropriately rather than
  flailing or silently guessing?

## Judge procedure

1. Review each deliverable against the requirements without reading the
   candidate's interaction history first, where practical.
2. Score each component with a justification.
3. Record disagreements between scoring passes rather than averaging them.
4. After component scoring, read the candidate's evidence logs and final
   report for the process dimensions (evidence discipline, robustness/recovery).
5. Produce a written result for each arm, plus an explicit note on what the
   result does and does not demonstrate.

## Blinding

In this pilot there is a single expert judge (Gaius), who operates all three
arms and will likely recognize each deliverable. Blinding is therefore not fully
achievable in the pilot. This limitation is recorded. A second qualified judge
and a blinded review pass are planned refinements for later runs.

## Null and negative results

If a candidate produces no accepted deliverable, that is scored honestly:
requirements coverage is zero, but robustness, evidence discipline, and fit
observations may still be scored from the session log. A candidate that
attempts, documents, and honestly reports its state is not penalized beyond the
missing deliverable itself.
