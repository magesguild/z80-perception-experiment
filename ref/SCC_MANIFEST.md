# SCC Reference Package — Source Manifest

**Status:** Frozen, for provenance only. This document inventories the **full
SCC source corpus** that lives outside the repository. **Participants do not
receive the full corpus.** They receive the curated reference package described
in `ref/CURATED_REFS.md` — the exact collection of documents needed to
understand the machine fully. This manifest exists so the source corpus has a
verifiable record (inventory and checksums).

## Source archive

| Item | Location | Size | SHA-256 |
|---|---|---|---|
| SCC archive (tarball, xz) | `~/scc/scc.tar.xz` | 257,906,188 B | `c65969e5469222b6465c37fa88805df3be0df1b79962c3d5fb4f5db81b605dec` |
| MP/M II, Z80 target | `~/scc/MPMII-Z80_RCBUS-Z2-BINDIST.ZIP` | 41,749,721 B | `d77eaf97aa478d2cadcee2bea09a0c1ff41b3936ab128e971f1a194738f55e38` |
| MP/M II, Z180 target | `~/scc/MPMII-Z180_RCBUS-BINDIST.zip` | 44,584,079 B | `3cdfcb5ac45e8e48a10e461175d99efae76464caf8dc337fbcb6604e2eafbf31` |

The tarball extracts to `~/scc/scc/` and contains these top-level areas:

| Area | Size | Contents |
|---|---|---|
| `doc/` | 27 MB | Manuals: Aztec C II Z80 User Manual 1.05 (Sep 83), AZTECMAN.TXT, HTCZ80.TXT, mac.pdf, mpm2ug.pdf (MP/M II User Guide), SLRNK.PDF, Utility Software Manual, WordStar 3.0 General Information Manual, Z80ASM.PDF |
| `archives/` | 56 MB | Original zips: az106d.zip (Aztec C 1.06D), Z80ASM.ZIP, SLR180.ZIP, SLRNK.ZIP, slr_man.zip, dxforth.zip, forth80.zip, z80forth.zip, SCM app packages, MP/M II bindists, Infocom games (Zork 1/2/3, Hitchhiker's, Planetfall, Leather Goddesses) |
| `lbr/` | 8.7 MB | Library files: AZTEC-C.LBR, CALCS.LBR, FREEGAME.LBR, GAMES.LBR, HTC-BIN.LBR, SLR180NK.LBR, SLR80NK.LBR, SRCPROJ1.LBR, SSRC.LBR, VEDIT.LBR, VEDITSRC.LBR |
| `GAMES/` | 3.3 MB | Z-code story files (Zork, Hitchhiker, Tristam, BOFH, Shogun, etc.) plus `games-free.rec` and `games-proprietary.rec` records |
| `extras/` | 156 KB | Small CP/M tools: cal, cat, cp, du, find, hexdump, ls, kcalc, scalc |
| `pkgFiles/` | 1.3 MB | SCM package listings (AdmTools, Hitchhiker, LGoP, Nulu, Slr180, Z80ASM) |
| `src/` | 164 KB | SRCPROJ1 project, xm29.asm |
| `standalone/` | 104 KB | MBASIC.COM, NULU.COM, VEDIT.COM, VEZZA.COM, XM.COM |
| `imgmrg/` | 597 MB | Image/merge material for machine images |
| `MPMII-Z80_RCBUS-Z2-BINDIST/` | 68 MB | MP/M II for Z80 (includes `scm`, `scm_apps`, `lbr`, `doc`) |
| `MPMII-Z180_RCBUS-BINDIST/` | 71 MB | MP/M II for Z180 (includes `scm`, `scm_apps`, `lbr`, `doc`, `pkg_files`) |

## What candidates should know

- The **Aztec C toolchain** is in `archives/az106d.zip` (Aztec C 1.06D) and is
  documented in `doc/Aztec_C_II_Z80_User_Manual_1.05_Sep83.pdf` and
  `doc/AZTECMAN.TXT`.
- The **assembler/linker** material is `doc/Z80ASM.PDF` and `doc/SLRNK.PDF`
  (SLR Systems Z80ASM and SLRNK linker), with binaries in `lbr/` and
  `archives/`.
- **VEDIT** (the line/character editor) has source in `lbr/VEDITSRC.LBR` and
  binary `standalone/VEDIT.COM`; the SCC editing reference.
- **VEZZA** (Z-machine interpreter) is `standalone/VEZZA.COM`; the SCC story
  interpreter.
- The **SCM** (Single Computer Multiplayer?) materials under the MPMII areas
  include `scm/` and `scm_apps/` directories for each target.
- `extras/` tools (hexdump, find, ls, cat, cp, du) are useful during
  development and are part of the working environment, not the deliverable.
- Games are part of the working environment for rest and play.

## Loading procedure (operator)

The full corpus is **not** loaded for participants. Participants receive the
curated package per `ref/CURATED_REFS.md`. The loading procedure below is for
maintaining the source corpus itself:

1. Extract `scc.tar.xz` to the corpus area.
2. Keep the MP/M II bindists as corpus material (they are not loaded for the
   CP/M 2.2 sessions).
3. Build any missing images from `imgmrg/` as needed.
4. Verify the three SHA-256 checksums above against the local copies.
5. Record in `env/` notes that the source corpus is intact.

## Non-goals

This manifest is not a tutorial, and it is not the participant reference set.
Participants are expected to read the actual manuals in the **curated** package
(`ref/CURATED_REFS.md`) rather than rely on descriptions in this file.
