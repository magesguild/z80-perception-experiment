# Curated Reference Package

**Status:** Adopted (final list to be confirmed by Gaius, who knows the
machine). This is the **exact collection of documents given to every
participant** to understand the machine fully. Participants do **not** receive
the full SCC archive; they receive this curated set, plus the orientation doc
in this repository.

The full SCC archive remains the source corpus and is documented for
provenance in `ref/SCC_MANIFEST.md`; it is not distributed to participants.

## The curated set

| # | Document | Source | SHA-256 |
|---|---|---|---|
| 1 | CP/M 2.2 operating system manual, including BDOS, FCB, directory, and file-record reference | `docs/cpm22-user-manual.txt` | `5230d63a1c1bdf3d8646194b3ada18cbb948d15b2f9ebdcae17caee815cb8eff` |
| 2 | Aztec C II Z80 User Manual, v1.05 (Sep 1983) | `docs/aztec-c-ii-z80-user-manual-1.05.txt` | `d051e73803fb4ef76d5ac1951bdcf1e34a9ffff97ec5e9cfc9f39f176aa8a561` |
| 3 | AZTECMAN.TXT (plain-text Aztec manual) | `docs/aztecman.txt` | `b4aa14397c5504757a222257eff70c7bdb496710f3be3b1e01c72538999f5823` |
| 4 | HTCZ80.TXT (compiler notes) | `docs/htcz80.txt` | `ad520dd441dfee79ec81b5e60400f5cddc0bf2720dd756c14e4a80314264f2f1` |
| 5 | RCBus/SIO/CTC serial-console notes | `docs/scm-rcbus-readme.txt`, `docs/scc-serial-interface-guide.txt` | see `docs/SCC_TEXT_MANIFEST.sha256` |
| 6 | Comparative Z80 serial/BDOS example | `docs/xm29-serial-example.asm.txt` | `f4b3b60ccf4f7c96afaa8f68eddec718447ebc63a33bb3b628006dff941d7a77` |
| 7 | SC100 hardware reference (memory map, console, drive letters incl. H:) | to be sourced (Gaius) | — |
| 8 | `docs/ORIENTATION.md` and `docs/SCC_TEXT_INDEX.md` (this repo) | in-repository | see git |

Z80ASM and SLRNK manuals are optional background references, not required
reading or required tools for the participant task. The blank participant is
not expected to learn assembly.

## What stays on the machine but is not part of the reference set

- **Games** remain available for rest and play. They are part of the working
  environment, not reference documents.
  - The **toolchain binaries** (Aztec C `cz` and normal build tools) and the base
  CP/M 2.2 system are installed on the machine. Their manuals are in the
  curated set above.

## Explicitly not given to participants

- MP/M II bindists (Z80 and Z180) — the sessions run CP/M 2.2.
- Infocom game archives and Z-code story files, except as playable games.
- VEDIT and VEZZA binaries and source — editor/interpreter references are not
  needed for HMAN; `ED.COM` remains available as the CP/M source editor.
- SCM materials, SLR180/Z180 toolchains, `imgmrg`, `extras`, `pkgFiles`,
  `lbr` contents beyond what the toolchain needs.

## Loading procedure (operator)

1. Wipe the drive and load the clean base: CP/M 2.2, the Aztec C toolchain, the
   games.
2. Load the curated reference documents (items 1–8) where the participant can
   read them on the machine or via the operator.
3. Verify the SHA-256 checksums of the documents above against the local
   copies.
4. Record in `env/MACHINES.md` that the curated package is present and complete
   for this session.

## To confirm with Gaius

- Locate/provide the SC100 hardware reference (item 7) — memory map, console,
  drive letters, and the H: drive specifics.
