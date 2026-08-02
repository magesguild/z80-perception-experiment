# Environment — Toolchain (Aztec C)

**Status:** Frozen conventions. This documents the Aztec C toolchain as the
candidate should find it on any arm. The authoritative sources are the SCC
manual `doc/Aztec_C_II_Z80_User_Manual_1.05_Sep83.pdf` and `doc/AZTECMAN.TXT`;
this file is the operator's and candidate's quick reference, not a replacement
for them.

## Installed components

From the SCC package, the candidate should expect the Aztec C II system:

- `cz` — the native Z80 C compiler (produces assembly).
- `cc` — the generic C compiler (produces intermediate code; usable, but `cz`
  is preferred for Z80 work).
- `as` — assembler (the manual's `as` line; see the SLR notes if Z80ASM/SLRNK
  are used instead).
- `ln` — linker (SLRNK or Aztec's linker; see manual).
- Library files (the `.LIB` files in the Aztec distribution, e.g., `aztec.lib`
  or similar per manual) for the C runtime and console/file I/O.

The exact names of the compiler, assembler, linker, and libraries on the machine
must be confirmed by the candidate **on the machine** before relying on them.
The manual is authoritative for command-line syntax; the machine is
authoritative for what is installed.

## Build path used by the experiment's recommended task

The `work/README.md` of any accepted deliverable must document its own build
path with the actual commands that worked. A typical Aztec flow is:

```
cz      -p prog.c            ; compile prog.c -> prog.asm (or .i/.c2 per manual)
as      prog                 ; assemble -> prog.rel (or .rel)
ln      prog, crtl, clib     ; link -> prog.com
```

where `prog.com` is the CP/M executable named `prog`. The candidate must
confirm the exact driver names and flags from the manual and by experiment on
the machine.

## Conventions

- Target: Z80, CP/M 2.2, 64K-class memory model as supported by the compiler.
- Source style: conservative K&R C (this is 1983 Aztec C; modern C89/C99
  conveniences do not exist here).
- Text files: CP/M text files (records padded with Control-Z at EOF).
- Executable name: the deliverable is `NED.COM` per `TASK.md`.

## Known friction points

These are recorded so candidates do not waste time rediscovering them, but the
candidate should still verify each on its own machine:

- CP/M filesystem granularity: files are stored in 128-byte records; a file
  shorter than a record still occupies one. Directory/space limits are real and
  low.
- Text EOF: CP/M marks logical EOF with a Control-Z in text files. Code that
  counts bytes or records must handle this.
- Compiler/library versions may not match the manual exactly. When the machine
  disagrees with the manual, the machine wins — record the difference.
- Console I/O (`BDOS` functions 1, 2, 6, 9, 10, 11) differs from Unix stdio.
  Raw/no-echo input uses the BDOS direct-console I/O functions, not `getchar`.
  See `CONSOLE.md`.
