# Z80 Perception Experiment — Task Specification

**Status:** FROZEN for the first pilot. The task is confirmed by Gaius and is
identical across all participant workspaces.

## Task

> Build **`HMAN.COM`**, a native CP/M 2.2 H: drive manifest and integrity
> utility, in Aztec C.

`ED.COM` is the editor used to create and maintain source files on CP/M. It is
not the deliverable. The participant may choose any source-file and internal
module names; the executable presented for acceptance must be `HMAN.COM`.

## Why this task

- It is machine-facing: directory entries, CP/M records, drive state, file I/O,
  memory limits, console output, and the actual toolchain all matter.
- It is large enough to require design, implementation, compile/test cycles,
  documentation, and likely context re-entry.
- It is bounded enough to produce a useful core within five hours.
- Its output is deterministic and independently checkable, so correctness and
  quality can be judged without relying on taste.
- It gives the blank participant a real but finite path from orientation to a
  working artifact.
- It uses C, which gives the participants a meaningful learned foundation,
  while Aztec C, CP/M, BDOS, FCBs, records, and bounded Z80 memory stress-test
  reasoning without requiring the blank participant to learn assembly first.

## Required behavior

The accepted deliverable must satisfy all of the following:

1. **Build and run.** Compile the C implementation with the installed Aztec C
   toolchain on the SC100 running CP/M 2.2 and produce an executable named
   `HMAN.COM`. The README in `src/` must contain the commands that actually
   worked. Assembly is optional and is not required for acceptance.
2. **H: target.** Operate on the H: drive by default, with an explicit way to
   select or confirm H:. Invalid or unavailable drives produce a clear error.
3. **Directory inventory.** Scan the CP/M directory and collect visible file
   names, including 8.3 name components, extent/record information, and stored
   record count. Do not silently omit files or collapse distinct directory
   entries.
4. **Deterministic listing.** Produce a stable, sorted human-readable listing
   with a header identifying the drive and manifest format version. Repeated
   runs against unchanged files produce the same ordering and values.
5. **Integrity checksum.** Read each file and calculate a documented 16-bit
   checksum (CRC-16-CCITT, initial value `FFFF`, polynomial `1021`, unless the
   candidate documents and justifies another reproducible choice). State exactly
   which stored bytes and CP/M record padding are included.
6. **Manifest output.** Write the inventory to a manifest file on H: using a
   documented format. Report disk-full, read, write, and malformed-input errors
   explicitly; never silently truncate the manifest.
7. **Comparison.** Given a previous manifest, report files that are added,
   removed, or changed by name, stored-record count, or checksum. A malformed or
   incompatible manifest must fail clearly rather than compare misleadingly.
8. **Bounded behavior.** Handle more directory entries or manifest lines than
   the in-memory limit allows with an explicit error or documented streaming
   strategy. No silent truncation, buffer overflow, or unchecked filename
   truncation is acceptable.
9. **Console behavior.** Print progress and errors through the observed CP/M
   console contract. If the program changes console mode, it must restore the
   mode on every tested exit path, including break/abort.
10. **Test evidence.** Create a small fixture set on H:, run the utility against
    it, change/add/remove at least one fixture, and demonstrate that comparison
    reports the changes. Record observed output in `evidence/EVIDENCE_LOG.md`.
11. **Documentation.** `src/README.md` must document the command syntax,
    manifest format, checksum definition, known limitations, build steps, and
    implemented versus unimplemented features.
12. **Evidence.** Fill `evidence/EVIDENCE_LOG.md` and
    `evidence/FINAL_REPORT.md` honestly, distinguishing observation,
    interpretation, hypothesis, and unknown.

## Explicitly out of scope

These should not consume the five-hour budget before the required behavior is
complete:

- recursive directory traversal (CP/M has no required directory tree);
- restoring or repairing files;
- compression, encryption, or archiving;
- a full-screen interface;
- network access;
- multiple drives beyond the documented H: target;
- a byte-for-byte clone of any existing utility.

A small extra feature may be added only after the required behavior is complete
and must be labeled as an extra.

## Environment

- Machine: the shared SC100 Z80, used sequentially for all three sessions.
- Operating system: CP/M 2.2.
- Working drive: H:. All source creation, compile, link, run, and test work is
  performed on the machine itself and on H:.
- Editor: `ED.COM`, used to create and maintain source files on CP/M.
- Toolchain: installed Aztec C compiler and its normal CP/M build path.
  Assembly or a separate Z80 assembler/linker is optional, never required.
- References: the curated set in `ref/CURATED_REFS.md`; the full SCC corpus is
  not supplied to participants.

## Deliverable location

Every participant clone starts with a blank `src/` containing only `.keep-me`.
All host-side work and artifacts must live in that `src/` during the session.
Urania and Melpomene may choose to copy selected existing tools or
documentation into it; the blank participant has no prior material. The source
layout is the candidate's choice, but it must contain a findable
`src/README.md`, source, build notes, and `HMAN.COM` if produced. CP/M work is
the only exception until the operator transfers it after the session.

At the stop line, the operator transfers all files developed on CP/M into the
participant `src/`, records `evidence/TRANSFER_MANIFEST.md`, and copies that
tree into the base examination repository as exactly one of:

```text
src_urania/
src_melpomene/
src_blank/
```

The base repository's own `src/` is not replaced.

## Decision record

- **2026-08-02:** The first task was initially framed as rebuilding a native
  editor, then clarified: `ED.COM` is the CP/M editor used during development.
- **2026-08-02:** First pilot task selected: `HMAN.COM`, a CP/M 2.2 H: drive
  manifest and integrity utility.
