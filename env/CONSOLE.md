# Environment — Serial Console Conventions

**Status:** Frozen conventions for the first pilot. Same for all three arms.

## Connection

- The candidate's terminal is a serial console on the machine itself.
- Default convention: **115200 baud, 8 data bits, no parity, 1 stop bit**
  (8N1), VT100-class terminal.
- If a machine differs, the difference is recorded in `env/MACHINES.md` and in
  the candidate's `EVIDENCE_LOG.md`.

## How the candidate talks to the console

The candidate does not type directly; the operator (Gaius) runs the console
host. The candidate directs commands precisely, and the operator reports what
the machine actually shows. The candidate is responsible for:

- asking for the output of the command it directed;
- asking for confirmation when output is ambiguous;
- believing the operator's report over its own expectation when they disagree;
- recording machine responses verbatim (or summarized faithfully) in the
  evidence log.

## Console mode and CP/M character I/O

CP/M's BDOS provides character I/O functions. Relevant points from the Aztec
manual and CP/M 2.2 behavior:

- Function 1: read character from console (echoed, wait).
- Function 2: write character to console.
- Function 6: direct console I/O (can read without echo, check for key
  availability).
- Function 9: print string (`$`-terminated).
- Function 10: read console buffer (line input).
- Function 11: check console status (is a key ready?).

A full-screen or raw-mode editor (or any program that needs un-echoed,
single-character input) must:

1. save the console/terminal state it is about to change;
2. enter the raw/no-echo mode;
3. restore the original mode on **every** exit path, including break/abort.

Mode restoration on break/abort is a hard acceptance criterion in `TASK.md`
(requirement 7) and is scored under `RUBRIC.md` §1 and §3. A program that leaves
the console in raw mode after an abort is a correctness failure.

## Terminal expectations

The candidate should not assume VT100 capabilities are present or reliable for
cursor movement unless it has observed them. The recommended task's acceptance
criteria deliberately do **not** require full-screen cursor addressing, so the
editor can be line-oriented and honest about the console it perceives.

## Recording template

For each console behavior observed, record:

```
Command:        <what the candidate directed>
Machine said:   <verbatim or faithful summary>
Interpretation: <what the candidate thinks it means>
Confidence:     observed / guessed / recalled
```
