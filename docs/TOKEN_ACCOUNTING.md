# Token and Cost Accounting

Token and monetary totals must be recorded from the actual runtime, not guessed
from message length after the fact.

## Standard runtime

OpenCode is the standard runtime for every participant. The operator records
the context and token counts displayed by OpenCode. The screen recording gives
an independent visual chronology for those readings.

## Required capture

For each participant, preserve:

- model, provider, version, and context-window configuration;
- raw runtime usage records, if the provider exposes them;
- input tokens, output tokens, cached tokens, and reasoning tokens separately
  when available;
- tool-call and retry counts;
- timestamps for session segments and re-entry events;
- pricing/rate-card version and currency;
- any unavailable fields and the estimation method, if an estimate is required.

At minimum, capture the displayed values at session entry, first compiling
artifact, first accepted-quality milestone, every compaction/re-entry, final
verification, and the stop line.

The raw usage artifact belongs with that participant's evidence. The normalized
summary belongs in `evidence/RUNTIME_METRICS.md`. Never replace an unavailable
value with zero.

## Normalized comparison

Report at least:

- total input tokens;
- total output tokens;
- total billable tokens, if supplied by the runtime;
- total monetary cost;
- cost per milestone;
- cost per weighted rubric point;
- tokens and operator minutes required for each re-entry.

If runtime substrates expose incompatible accounting, preserve each native
metric and explain the limitation rather than manufacturing a false common
unit. A small parser or collector may be added under the experiment's `src/`
tooling area once the actual runtime log format is known.
