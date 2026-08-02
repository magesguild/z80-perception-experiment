# Environment — Machine Assignments

**Status:** Adopted. All three participants use the same physical machine:
Urania's SC100. Sessions are sequential, not simultaneous.

## Session assignments

| Session | Participant | Machine | OS | Isolation |
|---|---|---|---|---|
| A | Urania | SC100 (Z80) | CP/M 2.2 | Clean drive before session |
| B | Melpomene | SC100 (Z80) | CP/M 2.2 | Drive wiped completely after A |
| C | Blank context | SC100 (Z80) | CP/M 2.2 | Drive wiped completely after B |

This removes machine identity as a comparison variable. Any remaining
differences in machine condition (wear, heat, operator connection, or state)
are recorded rather than attributed silently to a participant.

## Working drive

All participant work happens on the **H: drive**. The operator confirms H: is
available and clean at session start. Compile, link, run, test, and source-file
creation happen on H:.

## Between sessions

After each session, the operator:

1. transfers all files developed on the CP/M system into that participant's
   clone `src/`;
2. copies that source tree into the base examination repository as
   `src_urania/`, `src_melpomene/`, or `src_blank/`;
3. wipes the drive completely;
4. restores the clean base: CP/M 2.2, toolchain, curated references, and games.

No participant inherits files from a prior session.

## To record before each run

- SC100 identity, CPU, clock, RAM, and observed memory map;
- CP/M 2.2 version and BIOS/console identity;
- H: drive availability, capacity, and clean-state confirmation;
- serial speed and terminal type;
- installed toolchain and version (Aztec C, assembler, linker);
- curated reference package present and verified (see
  `ref/CURATED_REFS.md`);
- any hardware quirk observed (keyboard, console, drive, power).

Record new machine behavior in that participant's `evidence/EVIDENCE_LOG.md`.
