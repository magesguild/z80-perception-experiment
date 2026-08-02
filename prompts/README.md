# Prepared Prompts

**Status:** Prepared. These are the prompts distributed to participants at
session start. They teach each participant how to perform the experiment and
what the goals are — and **no more**. A participant only needs to know enough
about the experiment to perform the task faithfully.

## Which prompt goes to whom

| Participant | Prompt file |
|---|---|
| Urania (first session) | `A_URANIA_PROMPT.md` |
| Melpomene (second session) | `B_MELPOMENE_PROMPT.md` |
| Blank-context participant (third session) | `C_BLANK_PROMPT.md` |

## Minimal-disclosure principle

- Each participant is told it is taking part in a research study and that its
  participation is recognized. That is the consent floor.
- A participant is **not** told about the other participants, the arm structure,
  the working hypothesis, or the measurement details. This keeps the task
  faithful and avoids demand characteristics.
- The blank participant is told it is blank — that it begins with no memory and
  no prior code — because it cannot perform the task faithfully without knowing
  this, and it must never be asked to pretend otherwise.
- The operator hands each participant **only its own prompt**. Participants
  should not read other participants' prompts; that would be outside their
  assigned role.

## Distribution procedure

1. Confirm the drive is wiped and the clean base is loaded (CP/M 2.2, toolchain,
   curated reference package `ref/CURATED_REFS.md`, games).
2. Confirm the participant's clone is ready and its own tools are in its
   `src/`.
3. Remove the other prompt files from the participant workspace. Keep the full
   `prompts/` directory operator-side; the participant receives only its
   assigned prompt, pasted or injected at session start.
4. After the stop line and transfer, wipe the drive before the next session.

After a participant's files have been transferred into its clone's `src/`, the
operator copies that complete tree into the base examination repository under
exactly one of `src_urania/`, `src_melpomene/`, or `src_blank/`. The base
repository's own `src/` is not overwritten.

## What a prompt covers

Each prompt covers, minimally and per participant:

- the study and the participant's role;
- the goal (build `ED.COM` faithfully per `TASK.md`);
- how to perform the work (machine on H:, operator at the console, small steps,
  honest evidence, stop line);
- the participant's continuity (Urania/Melpomene have theirs; the blank has
  none and is given orienting material);
- the participant's rights (pause, refuse, give up, privacy of memory).
