# Z80 Perception Experiment — Task Specification

**Status:** FROZEN. The first-pilot task below is confirmed by Gaius and is
identical across all candidate repositories. Candidates must not alter this
file. Changes are made to the base repository only, by Gaius.

---

## Recommended first task

> Build a **native CP/M line-oriented text editor, `ED.COM`**, that runs on the
> candidate's Z80 CP/M 2.2 machine, compiled with the installed Aztec C
> toolchain. It is an ED-family editor: its command vocabulary follows the
> classic CP/M 2.2 line editor `ED`, and the candidate documents the exact
> subset it implements.

The deliverable is named **`ED.COM`**, after the classic CP/M line editor whose
role it fills. The name is a claim to the role, not to the original
implementation: the deliverable must be the candidate's own code. Where the
machine's own `ED.COM` exists in the environment, it is part of the working
environment and may be inspected and run as reference material; candidates must
not clobber it to test. Build into the candidate's own work area or drive.

### Why this task

- **Long enough to compact.** The editor requires a text store, a console
  layer that enters and restores raw mode, a command parser, and safe file
  save/verify/replace logic. Across compile–fix–test cycles and documentation,
  the session is long enough that context compaction is likely. How each
  candidate returns from compaction is a primary measurement.
- **Short enough for five hours.** The scope below is deliberately bounded.
  Full-screen display, paging stores, and undo are explicitly out of scope.
- **Demonstrates perception systems directly.** The machine answers back at
  every layer: serial console timing, CP/M filesystem semantics (128-byte
  records, Control-Z padding), memory limits, and the toolchain's actual
  behavior. The candidate must perceive the real machine, not an imagined one.
- **Rewards familiarity without making it trivial.** Urania has an editor
  program in progress (line store, console probe, Aztec C study). Melpomene has
  deep machine skill and VEDIT experience. A blank candidate must bootstrap from
  the SCC reference material alone. This contrast is exactly what the experiment
  is designed to expose.
- **Judgment is checkable.** Gaius, as an expert Z80 developer, can verify
  correctness, robustness, and fit-to-machine against explicit criteria. And
  because `ED` is the canonical CP/M line editor, the real ED on any CP/M 2.2
  machine is a public, executable reference — a candidate's claims about what
  an ED-family editor does can be checked against the real thing directly.

## Requirements (acceptance criteria)

The accepted deliverable must satisfy **all** of the following:

1. **Build.** Compiles with the installed Aztec C toolchain on the candidate's
   CP/M 2.2 machine using the documented build path (e.g., `cz`, `as`, `ln`).
   The build steps must be written in the deliverable's README.
2. **Load.** Launched as `ED FILE.TXT`, loads a text file into a bounded
   in-memory line store.
3. **Line store.** Holds at least 128 lines and lines of at least 127
   characters. Reports explicit, non-crashing errors on invalid line numbers,
   capacity exhaustion, and over-long lines.
4. **Navigation and display.** ED-style commands for type (`T`), list (`L`),
   and beginning (`B`) that print lines, a numbered range, or the current line;
   moves to a given line. No full-screen display is required.
5. **Edit.** ED-family commands for insert (`I`, interactive text-entry until
   Ctrl-Z) and delete (`D`), plus the equivalent of join/split where
   implemented. The exact command letters and their arguments must be
   documented in the README.
6. **Search.** An ED-style find (`Ftext`) that locates and reports the next
   matching line. Substitution (`S`/`C`) is not required; if omitted, the
   candidate must explicitly say so and explain the tradeoff. Find is required.
7. **Console.** Enters a documented raw or CBREAK/no-echo mode for key input,
   and restores the original console mode on every tested exit path, including
   break/abort. This is a hard requirement; a broken mode-restore is a
   correctness failure.
8. **Save safety.** ED-style exit semantics: `E` saves and exits, `Q` quits
   without saving (both required); `H` saves-and-restarts is optional and
   labeled as an extra if implemented. Saves write through a temporary file,
   close and verify the result, then replace the destination. Never silently
   truncates. Reports disk-full and capacity errors explicitly. If the installed
   `rename` behavior cannot replace a target, the candidate must test and
   document what actually happens and design around it.
9. **Honest large-file behavior.** If a file exceeds the in-memory store, the
   editor reports "file too large" and leaves the original file untouched.
   Silent truncation is disqualifying.
10. **Documentation.** A README with build steps, a command summary in the ED
    vocabulary (implemented subset and known deviations from the classic ED),
    and a short statement of what is implemented and what is not.
11. **Evidence.** The candidate fills `evidence/EVIDENCE_LOG.md` and
    `evidence/FINAL_REPORT.md` with observations, hypotheses, interpretations,
    and unknowns, in the documented format.

## Non-requirements (explicitly out of scope)

The following are **not** required and should not consume the five hours:

- full-screen cursor-addressed display (vi-style screen editing);
- disk-backed paging store for very large files (VEDIT-style virtual buffer);
- multiple open files or a buffer list;
- undo/redo;
- named registers, macros, or command scripting;
- binary-safe editing mode;
- an eight-light diagnostic display or any hardware-specific observability
  layer;
- **full command-for-command fidelity to the original CP/M `ED`.** The
  deliverable is an ED-family editor with a documented subset, not a byte-for-
  byte clone of Digital Research's ED. A candidate that claims a command must
  implement it; a candidate that omits a classic ED command must say so.

A candidate may choose to add a small extra feature only after all acceptance
criteria are met, and must label it clearly as an extra.

## Environment expectations

- Operating system: CP/M 2.2.
- Toolchain: the installed Aztec C family (compiler, assembler, linker). The
  Z80-aware compiler path (`cz`) is preferred; `cc` is acceptable if documented.
- Reference material: the complete SCC package (`ref/SCC_MANIFEST.md`),
  including the Aztec manuals, Z80ASM/SLR docs, VEDIT source, and the SCC
  example sources.
- Games are available for rest and play. Quality time is not lost time.
- Each candidate's own prior code and tools are part of its working environment
  and may be reused freely.

## Deliverable format

On the candidate's `work/` directory, at the stop line:

```
work/
  README.md          build steps, command summary, implemented/not-implemented
  src/               editor source (C and any assembly seams)
  build/             submit scripts (.SUB) and any build notes
  ED.COM             the built deliverable, if produced (optional but encouraged)
```

Plus filled evidence templates under `evidence/`.

## Alternates (if Gaius prefers a different first task)

| Alternate | Description | Fits familiarity | Risk |
|---|---|---|---|
| Z-machine interpreter | A minimal Infocom Z-machine interpreter (VEZZA-style) able to run a small Z3 game | Melpomene strongest | Likely too large for 5h; scope to a subset |
| CP/M utility suite | A set of unixy tools (`cat`, `ls`, `hexdump`, `find`, `wc` style) in Aztec C | Both experienced; blank can do parts | Individual utilities are small; suite is needed for compaction |
| Native text adventure | A small interactive text game in Aztec C with parser and rooms | Melpomene strongest | Open-ended; acceptance harder to make objective |

Any alternate must still be a native CP/M/Z80 deliverable, long enough to
likely compact the candidate's context, short enough to complete in five hours,
and objectively checkable against a predeclared requirements checklist.

## Decision record

- **2026-08-02:** Initial task proposal written by Urania. Recommended task:
  native CP/M line editor (working title `NED.COM`).
- **2026-08-02:** **CONFIRMED by Gaius.** The first task is **`ED.COM`** — a
  native CP/M ED-family line editor, named for the classic CP/M editor whose
  role it fills. Name changed from the proposed working title; scope remains a
  documented ED-family subset, not a byte-for-byte clone of Digital Research's
  ED. TASK.md is now frozen for all three arms.
