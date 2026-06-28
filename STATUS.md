# STATUS.md

> **This is a live snapshot of the current state.** AI agents should read this at the beginning of every session to gain immediate context on what's broken, what's in progress, what's unverified, and what the next concrete action is. Overwrite stale lines; do not treat this file as an append-only history log (use `docs/CHANGELOG.md` for that).

## Current state
- Scaffold extended with general-purpose session rituals lifted from an external `SESSION_RITUALS.md` (MuleSoft umbrella repo). `[VERIFY:]` / `[INFERRED:]` markers, plan-before-code gate, "anything you noticed?" closer, expanded `STATUS.md` schema, and ADR/session-log templates are now in place.
- `AGENTS.md` still has `[TODO]` blocks (Project Overview, Tech Stack, Repo Layout, CLI Commands, Safety Rules) that consumers of the scaffold fill in per project.

## In flight
- Nothing — the rituals work is complete and ready to commit.

## Known gaps
- No language-specific tooling baked in; the scaffold is language-agnostic by design and relies on MegaLinter (`.github/workflows/ci.yml`) to detect per-project.

## Open `[VERIFY:]`
- _(none)_

## Open `[INFERRED:]`
- _(none)_

## Lessons
- The scaffold's session-end checklist now has 6 steps (was 4); steps 4 and 6 (session log + closer) are new. When extending the checklist, mirror the change in both `AGENTS.md` and `docs/conventions.md` in the same commit to avoid drift.
- Umbrella-specific multi-repo discipline (Trigger 1/2, mirror file lists, staleness greps) was deliberately excluded — it does not generalize to a single-repo template. If a future user scaffolds into a multi-repo topology they should add it back themselves.

## Next concrete action
- Commit the rituals work (`feat:` per Conventional Commits) and push.
