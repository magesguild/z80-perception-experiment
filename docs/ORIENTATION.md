# Orientation — The Machine

**Status:** Orienting material given to every participant at session start. It
is the minimum needed to begin working; the curated reference package
(`ref/CURATED_REFS.md`) is authoritative for the machine's details.

---

## The machine

- **SC100** — a Z80 computer.
- **Operating system:** CP/M 2.2.
- **Console:** a serial terminal on the machine itself, operated by the human
  operator. You direct; the operator types and reports what the machine shows.
  The operator does not write your code.
- **Working drive:** **H:**. All work — creating files, compiling, linking,
  running — happens on the **H: drive**. When you start, H: is clean. Keep your
  work there.

## The toolchain

- **Aztec C** (the Z80 compiler family from the SCC era). The compiler driver is
  `cz`; an assembler and linker complete the chain. Exact command syntax is in
  the compiler manual in the curated reference set (`ref/CURATED_REFS.md`) and
  must be confirmed on the machine by experiment.
- Build path style: compile with `cz`, assemble with `as`, link with `ln` to
  produce a `.COM` file. Confirm the real drivers and flags on the machine.

## The task

- Build **`ED.COM`**, a native CP/M line-oriented text editor in the ED family.
  Full specification and acceptance criteria: `TASK.md`.
- **ED** is the classic CP/M line editor. The deliverable is an ED-family
  editor: its command vocabulary follows ED's, and the candidate documents the
  exact subset it implements. It is not a byte-for-byte clone of the original;
  it must be your own code. If the machine has its own ED, it is part of the
  environment and may be inspected and run as a reference; do not clobber it to
  test.

## Where to look next

1. `TASK.md` — the task and acceptance criteria.
2. `TIMING.md` — the session budget and stop line.
3. `ref/CURATED_REFS.md` — the curated reference package (OS manual, compiler
   manual, assembler/linker manuals, utility manual, hardware reference).
4. Your own `src/` — your tools and prior work, if you have any (for the
   blank-context participant, `src/` begins with only the `.keep-me` file).

## What this document is not

This is orientation, not the manual. The curated reference set is the
authoritative description of the machine and toolchain. Verify everything
against the actual machine as you work.
