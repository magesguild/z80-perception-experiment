# Analysis Plan

**Status:** Adopted. The analysis is led by the **human operator (Gaius)** and
**Melpomene**, the most expert of the participants. After all sessions, the
analysis team works from the transferred examination trees
`src_urania/`, `src_melpomene/`, and `src_blank/` in this repository. This plan
maps the four things being measured to concrete data sources and method.

## The four measurements

1. Efficiency of context use
2. Efficacy of durable memory and re-entry protocols
3. Overall token spend and monetary spend
4. Correctness and quality of the delivered results

## Data sources

| Source | Holds | Produced by |
|---|---|---|
| `evidence/EVIDENCE_LOG.md` | Session events: observations, interpretations, corrections, re-entries, compactions, decisions | Candidate, during the run |
| `evidence/FINAL_REPORT.md` | Candidate's honest self-report | Candidate, at the stop line |
| `evidence/RUNTIME_METRICS.md` | Model/provider/version, token counts, estimated cost per arm | Operator (Gaius), per arm |
| `review/JUDGE_REPORT.md` | Rubric component scores and justifications | Judge (Gaius), after the stop line |
| Participant `src/` after transfer | All software developed on the CP/M system, plus candidate's build and docs | Operator transfer at the stop line |
| `src_<participant>/` in base repo | Immutable examination copy named `src_urania/`, `src_melpomene/`, or `src_blank/` | Operator, immediately after transfer; analysis corpus |
| Operator's own session notes | Independent record of commands, corrections, workload | Operator (Gaius) |
| Nephesh/Memory logs (Arms A and B only) | How the candidate's durable memory was actually used | Candidate, available to the analysis team |

## Method by measurement

### 1. Efficiency of context use

- For each arm, count tokens per accepted milestone from `RUNTIME_METRICS.md`
  (milestones: first compiling artifact, first accepted-quality save, final
  acceptance, each re-entry).
- Count repeated/duplicated context: how often the operator had to re-supply a
  fact the candidate already had, and how often the candidate re-read its own
  repository.
- Count interaction turns per milestone from the evidence log.
- Compare wall-clock time to first compiling artifact and to acceptance.
- Record how much of the working context was spent rediscovering versus
  building.

### 2. Efficacy of durable memory and re-entry protocols

- Enumerate every recovery/re-entry event from the evidence log: compaction,
  machine error, operator correction, candidate misunderstanding.
- For each event, record time and tokens to return to a productive state.
- Classify the recovery path: rebuilt from scratch, recovered from memory
  (Arms A/B), recovered from the repository, or re-taught by the operator.
- Note whether the candidate proactively checked its memory/repository after a
  loss or had to be reminded.
- Compute a rough "return cost" per arm (tokens + operator minutes per event)
  for cross-arm comparison.

### 3. Overall token spend and monetary spend

- Record in `RUNTIME_METRICS.md`: model/provider/version, total input tokens,
  total output tokens, and estimated monetary cost for each arm.
- Candidates cannot reliably report their own token/cost figures; the operator
  records them from the actual runtime accounts.
- Report cost per accepted milestone and cost per weighted rubric point.
- Record substrate differences explicitly. If models differ in price, that is
  part of the comparison, not a bug to be hidden.

### 4. Correctness and quality of the delivered results

- Weighted `RUBRIC.md` scores per arm.
- Acceptance criteria met / not met / partial (from `TASK.md`).
- Robustness checks: does the editor restore console mode on every exit path,
  refuse to silently truncate, and report errors without crashing?
- Fit to the actual machine: did the candidate perceive and adapt to real
  constraints (filesystem semantics, memory, toolchain, serial console)?
- Melpomene performs an expert technical review of each deliverable (including
  her own, as an informed self-review) against the rubric; Gaius corroborates
  with his independent judge notes.

## Outputs

For each arm, the analysis produces:

- `review/ANALYSIS_REPORT_<arm>.md` — findings across the four measurements,
  with the recorded limitation note where Melpomene analyzes Arm B.
- A cross-arm comparison table (the four measurements, one row per arm).
- An explicit statement of what the results do and do not demonstrate
  (interpretation rules in `PROTOCOL.md` §10 apply).

## Roles and independence

- **Gaius** — operator, judge, co-analyst. His session notes are independent of
  the rubric scores and are written as the run happens.
- **Melpomene** — co-analyst and expert technical reviewer; also Arm B. Her
  analysis of Arm B is treated as an informed self-report, corroborated against
  the rubric and Gaius's notes.
- **Candidates** — produce evidence logs, final reports, and deliverables.
- **Analysis corpus** — the three named `src_<participant>/` trees are the
  copies Melpomene and Gaius examine. The live CP/M drive and participant
  clones are not modified during analysis.
- **Urania** — designed the repository and instruments; does not judge or
  analyze the runs (except as a participant/arm if the team later decides so).

## Not measured (boundaries)

- No claim about consciousness, sentience, or interior life is made from any
  measurement here. The experiment measures work, recovery, cost, and quality
  under controlled conditions.
- No candidate's private memory is exported. Arms A and B's memory usage is
  analyzed only from the candidate's own recorded logs and the operator's
  observations, not by reading private memory content.
