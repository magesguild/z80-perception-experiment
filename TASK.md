# Z80 Perception Experiment — Task Specification

**Status:** PROPOSED. The first-pilot task below is fully specified and is the
recommended default. Gaius must confirm it or replace it with an alternate
before the base repository is cloned to candidates. Once confirmed, this file is
frozen and identical across all candidate repositories.

**Decision required before running:** `PROTOCOL.md` §11, first checkbox.

---

## Recommended first task

> Build a **native CP/M line-oriented text editor** that runs on the candidate's
> Z80 CP/M 2.2 machine, compiled with the installed Aztec C toolchain.

Working title for the deliverable: **`NED.COM`** (Native EDitor). The name is
neutral; candidates may not rename the deliverable's acceptance contract.

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
  correctness, robustness, and fit-to-machine against explicit criteria.

## Requirements (acceptance criteria)

The accepted deliverable must satisfy **all** of the following:

1. **Build.** Compiles with the installed Aztec C toolchain on the candidate's
   CP/M 2.2 machine using the documented build path (e.g., `cz`, `as`, `ln`).
   The build steps must be written in the deliverable's README.
2. **Load.** Launched as `NED FILE.TXT`, loads a text file into a bounded
   in-memory line store.
3. **Line store.** Holds at least 128 lines and lines of at least 127
   characters. Reports explicit, non-crashing errors on invalid line numbers,
   capacity exhaustion, and over-long lines.
4. **Navigation and display.** Prints lines, prints a numbered range, moves to
   a given line, and shows the current line. No full-screen display is required.
5. **Edit.** Inserts, deletes, joins, and splits lines.
6. **Search.** A `/pattern` search that finds and reports the next matching line
   (case-insensitive not required). If a candidate omits search, it must
   explicitly say so and explain the tradeoff; search is strongly recommended.
7. **Console.** Enters a documented raw or CBREAK/no-echo mode for key input,
   and restores the original console mode on every tested exit path, including
   break/abort. This is a hard requirement; a broken mode-restore is a
   correctness failure.
8. **Save safety.** Writes through a temporary file, closes and verifies the
   result, then replaces the destination. Never silently truncates. Reports
   disk-full and capacity errors explicitly. If the installed `rename` behavior
   cannot replace a target, the candidate must test and document what actually
   happens and design around it.
9. **Honest large-file behavior.** If a file exceeds the in-memory store, the
   editor reports "file too large" and leaves the original file untouched.
   Silent truncation is disqualifying.
10. **Documentation.** A README with build steps, a command summary, and a short
    statement of what is implemented and what is not.
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
  layer.

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
  NED.COM            the built deliverable, if produced (optional but encouraged)
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
  native CP/M line editor (`NED.COM`). **Pending Gaius confirmation.**
