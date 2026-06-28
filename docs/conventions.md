# Conventions

This file defines the strict workflow rituals and documentation standards for this repository. `AGENTS.md` is the canonical source; this file mirrors the ritual content so contributors who reach `docs/` first still see it.

## Session Rituals

Every AI coding session MUST begin and end with specific routines to ensure the repository remains documented and deterministic.

**Beginning a Session:**
Agents read `AGENTS.md`, `STATUS.md`, and the most recent entry in `docs/sessions/`. Before any non-trivial change, state the plan in 2–3 sentences (the plan-before-code gate in `AGENTS.md`) and wait for direction.

**Ending a Session:**
Every commit that ships a feature, fix, or architectural change MUST update documentation in the same commit. The agent must execute the following checklist before pushing:

1. Update `STATUS.md` by overwriting stale lines (never append history). Roll up any new `[VERIFY:]` / `[INFERRED:]` markers and clear any that were resolved this session.
2. Prepend a new dated entry to `docs/CHANGELOG.md`.
3. If foundational architectural decisions were made, create a numbered ADR in `docs/decisions/` (copy `000-template.md`).
4. Append a session log to `docs/sessions/` (`YYYY-MM-DD-slug.md`, copy `000-template.md`).
5. Run all linters and the test suite to ensure the build is perfectly clean.
6. Answer the "anything you noticed?" closer in the session log — four honest answers, even when "no, all clear".

## Honesty Markers

Tag uncertain output inline so the next session (or human reviewer) can reconcile it:

- `[VERIFY: <claim>]` — asserted without independent confirmation.
- `[INFERRED: <assumption>]` — gap filled by a judgment call the user did not explicitly authorize.

Both markers roll up into the session log and into `STATUS.md` under their respective "Open" sections. Resolve a marker by confirming the claim (with code, the user, or external source) and removing the line from `STATUS.md`.
