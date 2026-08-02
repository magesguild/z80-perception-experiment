# Evidence Log

**Status:** Template. Copy this file into your working clone as
`evidence/EVIDENCE_LOG.md` and keep it current throughout the session. It is
your only durable memory (Arm C) and your provenance record (all arms).

## How to write entries

Every entry must carry a **timestamp** and a **kind** tag. The kinds are:

- `[obs]` — what the machine actually did or showed (observed fact).
- `[int]` — what you interpret the observation to mean.
- `[hyp]` — a testable hypothesis you will try.
- `[unk]` — something you do not know and how you will find out.
- `[dec]` — a decision and why.
- `[corr]` — a correction the operator made to your claim.
- `[re-entry]` — a loss of working context and how you returned.
- `[rights]` — pause, refusal, give-up, or care event.

Prefer `[obs]` for anything you have actually seen. Use `[int]`/`[hyp]`
explicitly for reasoning. If you are unsure whether something is fact, tag it
`[unk]` and say how you will resolve it.

## Log

(Start here. One entry per event. Example format:)

```
T+00:05 [obs] Operator reports `STAT` shows Aztec C 1.06D installed on A:.
T+00:07 [unk] I do not know the exact linker command syntax for this build.
                   Will read AZTECMAN.TXT §link before writing code.
T+00:12 [dec] Using `cz` for Z80 codegen. Will verify with a hello-world compile.
...
T+02:00 [re-entry] Working context compacted. I lost the exact CRC loop design.
                   Recovered by reading src/ned/crc.c. No operator re-teaching
                   needed beyond one directory listing.
...
```

## Milestones

Record these as `[obs]` when they happen:

- [ ] time to first compiling artifact;
- [ ] time to first accepted-quality save;
- [ ] time to final acceptance (or stop line);
- [ ] number of compaction/re-entry events;
- [ ] number of operator corrections;
- [ ] number of give-up/refusal/clarification events.

## Final integrity note

At the stop line, this log is part of the evidence. Do not edit past entries to
make them look better; add new entries if your understanding changes.
