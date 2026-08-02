# Runtime Metrics (operator-recorded)

**Status:** Template. Filled in by the **human operator (Gaius)** for each arm
during and after its session. Candidates cannot reliably report their own token
and cost figures, so the operator records them from the actual runtime accounts.
This file is part of the evidence for measurement 3 (token spend and monetary
spend) and feeds measurements 1 and 2 (context-use efficiency, re-entry cost).

## Per arm

- Arm: (A / B / C)
- Candidate:
- Date / session:

## Runtime substrate

- Runtime: OpenCode
- Model:
- Provider:
- Version / snapshot:
- Context window size (if known):
- Notes (temperature, sampling, any runtime flags):

## OpenCode display snapshots

Record the values visible in OpenCode at each milestone. The screen recording
should make these readings independently reviewable.

| Event | Context displayed | Input/token count displayed | Output/token count displayed | Timestamp | Notes |
|---|---:|---:|---:|---|---|
| Session entry | | | | | |
| First compiling artifact | | | | | |
| First accepted-quality milestone | | | | | |
| Each compaction/re-entry | | | | | |
| Final verification | | | | | |
| Stop line | | | | | |

## Token accounting

Preserve raw runtime usage records alongside this summary. See
`docs/TOKEN_ACCOUNTING.md`. Do not silently convert unavailable values to zero.

If the runtime exposes token usage, record per session segment:

| Segment | Input tokens | Output tokens | Notes |
|---|---|---|---|
| Enter (prompt + repo read) | | | |
| Survey | | | |
| Build to first compiling artifact | | | |
| Build to first accepted-quality save | | | |
| Each recovery/re-entry event | | | |
| Completion / verification | | | |
| Final report + commit | | | |
| **Total** | | | |

If per-segment figures are not available, record totals and say so.

## Monetary spend

- Total input + output tokens:
- Pricing used (per 1M tokens, input / output):
- Estimated cost, total:
- Cost per accepted milestone (first artifact, accepted deliverable):
- Cost per weighted rubric point (after scoring):

## Notes on measurement

- If the runtime does not expose token usage, record "not available" and
  describe how the estimate was made (or that no estimate is possible).
- If substrates differ between arms, record that here; differences in price are
  part of the comparison, not normalized away.
