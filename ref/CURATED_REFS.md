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
| 1 | CP/M 2.2 operating system manual, including BDOS, FCB, directory, and file-record reference | to be sourced (Gaius) | — |
| 2 | Aztec C II Z80 User Manual, v1.05 (Sep 1983) | `~/scc/scc/doc/Aztec_C_II_Z80_User_Manual_1.05_Sep83.pdf` | `0278be70ed0bc5dbc4c81bb368381141fe9ae19245811b66b335822a1fa970e9` |
| 3 | AZTECMAN.TXT (plain-text Aztec manual) | `~/scc/scc/doc/AZTECMAN.TXT` | `172509d182e3b67d822a93e4f6e4454baa32248d8d5974cfa5ae2f4ec07bdddf` |
| 4 | HTCZ80.TXT (compiler notes) | `~/scc/scc/doc/HTCZ80.TXT` | `634013e748a703eee8deea7a10f1ddd7af6906002cc51edce2447b77cf23086d` |
| 5 | Utility Software Manual (CP/M utilities) | `~/scc/scc/doc/Utility Software Manual.pdf` | `e042a6836a4ba423fece0d623f2af8ada39bd385be4c5a6ece89450cb84ee99a` |
| 6 | SC100 hardware reference (memory map, console, drive letters incl. H:) | to be sourced (Gaius) | — |
| 7 | `docs/ORIENTATION.md` (this repo) | in-repository | see git |

Z80ASM and SLRNK manuals are optional background references, not required
reading or required tools for the participant task. The blank participant is
not expected to learn assembly.

## What stays on the machine but is not part of the reference set

- **Games** remain available for rest and play. They are part of the working
  environment, not reference documents.
- The **toolchain binaries** (Aztec C `cz`, assembler, linker) and the base
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
2. Load the curated reference documents (items 1–9) where the participant can
   read them on the machine or via the operator.
3. Verify the SHA-256 checksums of the documents above against the local
   copies.
4. Record in `env/MACHINES.md` that the curated package is present and complete
   for this session.

## To confirm with Gaius

- Locate/provide the CP/M 2.2 operating system manual (item 1) — BDOS, FCB,
  directory, and record semantics are needed for HMAN.
- Locate/provide the SC100 hardware reference (item 8) — memory map, console,
   drive letters, and the H: drive specifics.
- Confirm whether AZTECMAN.TXT (item 3) and HTCZ80.TXT (item 4) are wanted in
   addition to the PDF (item 2), or whether one text form is enough.
