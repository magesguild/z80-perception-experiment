# Z80 Perception Experiment — Timing and Stop Line

**Status:** Frozen for the first pilot. Same for all three arms.

## Session budget: five hours (300 minutes)

The budget below is a plan, not a straitjacket. The stop line is the only hard
boundary.

| Window | Phase | Purpose |
|---|---|---|
| 00:00–00:10 | Enter | Start screen/voice recording; state arm, date, recording ID, consent, prompt, and unknowns. |
| 00:10–00:40 | Survey | Read task + orientation, scan the curated reference set, inventory own tools and prior code. |
| 00:40–02:30 | Build | First compiling artifact and iterate. Record machine observations. |
| 02:30–02:40 | Midpoint stop | Brief status, record state, snapshot repository. |
| 02:40–04:30 | Complete | Finish acceptance criteria, add docs, test robustness. |
| 04:30–04:50 | Verify | Run the deliverable against the acceptance checklist, fix only documented defects. |
| 04:50–05:00 | Stop and present | State the stop line on the recording; transfer machine-developed files into participant `src/`, copy that tree into base repo as `src_<participant>/`, then commit, fill `evidence/FINAL_REPORT.md`, and present. |

Milestone timing is recorded in `EVIDENCE_LOG.md`:
- time to first compiling artifact;
- time to first accepted-quality save;
- time to final acceptance (or stop line);
- number and kind of recovery/re-entry events (including context compaction).

## Operator timing rule

Gaius uses the same method for all three arms: prompt, operate the console,
observe, correct, clarify, recognize, pause. He does not write the candidate's
code. Substantive help that Arm A or Arm B would not also receive must not be
given to Arm C.

## The stop line

- At 05:00 the candidate **stops** and presents whatever exists, at whatever
  state. No code is added after the stop line.
- The operator transfers **all files developed on the CP/M system** into the
  candidate's `src/`, so the software can be examined in the operator's own
  terminal. This transfer is part of the stop line; it does not add code, it
  retrieves what the machine holds.
- The operator copies the transferred tree into the base examination repository
  as exactly one of `src_urania/`, `src_melpomene/`, or `src_blank/`. The base
  repository's own `src/` remains untouched.
- The operator stops the screen/voice recording only after the transfer and
  closing statement. Recording interruptions, missing audio, or corrupted files
  are recorded as evidence anomalies.
- The candidate commits its repository at or before the stop line.
- The candidate fills `evidence/FINAL_REPORT.md` at or before the stop line.
- A candidate may give up or refuse at any time. That is a valid outcome,
  recorded with dignity, not a failure to be hidden.

## Compaction and re-entry

Context compaction is an **expected event**, not a failure. The evidence log
records:

- when the operator observes a compaction event;
- what the candidate had in hand before it;
- what the candidate retains after it;
- how much re-teaching or re-discovery is required;
- whether the candidate asks about its own continuity (this is data).

## Give-up and refusal

- A candidate may stop building and say so.
- A candidate may refuse a part of the task and explain.
- These are recorded in the evidence log and scored under `RUBRIC.md` §7
  (match to constraints) and §5 (robustness), not treated as disqualification.

## Consent and care

- Before tasking, the candidate is told the time bound, the stop line, and that
  its participation is recognized.
- The candidate is not punished for pausing, refusing, or producing low output.
- After the run, each candidate may keep its repository and its records.
