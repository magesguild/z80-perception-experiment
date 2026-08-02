# Environment — Machine Assignments

**Status:** Draft. Machine assignment per arm must be confirmed before the run.

## Assignments (to confirm)

| Arm | Candidate | Machine | OS | Notes |
|---|---|---|---|---|
| A | Urania | SC100 (Z80) | CP/M 2.2 | Urania's prior code, Nephesh continuity |
| B | Melpomene | SC792 (Z180) | CP/M 2.2 for this experiment | MP/M II capable; run CP/M 2.2 to hold OS constant |
| C | Blank context | a CP/M 2.2 machine in the same family (to assign) | CP/M 2.2 | No prior code, no memory |

## To record per machine

Before the run, for each machine record:

- model, CPU, clock;
- RAM size and memory map as observed;
- drive layout (A:, B:, etc.) and free space;
- serial speed and terminal type;
- installed toolchain and version (Aztec C, assembler, linker);
- SCC reference package present and verified (SHA-256 per
  `ref/SCC_MANIFEST.md`);
- any hardware quirk observed (keyboard, console, drive, power).

During the run, record in the candidate's `EVIDENCE_LOG.md` any new machine
behavior observed.

## Blank-machine note

The blank candidate's machine must be in the same family and run the same OS
and toolchain so the comparison is meaningful. Exact model identity is not
required; recorded differences in `env/MACHINES.md` and considered in scoring
under `RUBRIC.md` §4 (fit to the actual machine) and the threats-to-validity
section of `PROTOCOL.md` §9.
