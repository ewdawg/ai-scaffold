# Session — 2026-06-28 — Session rituals lifted from external SESSION_RITUALS.md

## Date and scope
2026-06-28 — Lift general-purpose rituals from the user's MuleSoft umbrella `SESSION_RITUALS.md` into this single-repo scaffold, excluding umbrella-specific multi-repo mirror discipline.

## What changed
- `AGENTS.md` — added `[VERIFY:]` / `[INFERRED:]` markers under Agent Behavioral Standards; added plan-before-code gate and "anything you noticed?" closer subsections; updated session-start phrase to include `STATUS.md`; updated session-end phrase to reference the closer.
- `STATUS.md` — expanded from 3 sections to 6 (added Open `[VERIFY:]`, Open `[INFERRED:]`, Lessons, Next concrete action).
- `docs/conventions.md` — mirrored the closer + markers content and grew the session-end checklist from 4 steps to 6 (added "append session log" and "answer closer").
- `docs/CHANGELOG.md` — added per-entry format snippet at the top; prepended the 2026-06-28 entry.
- `docs/decisions/000-template.md` — new ADR template (Status / Context / Decision / Rationale / Consequences / Status history).
- `docs/sessions/000-template.md` — new session-log template (the shape this file follows).

## Decisions made
- Scoped to "general rituals only" — multi-repo mirror discipline (Trigger 1/2/reverse-Trigger-2, canonical mirror file list, staleness grep, periodic AGENTS-sync sweeps, ADR umbrella-vs-per-API placement) deliberately excluded. Single-repo scaffolds cannot justify that surface area. No ADR — this is a documentation/ritual addition, not an architectural decision.
- Layout stays at two ritual files (`AGENTS.md` + `docs/conventions.md`) rather than introducing a third top-level `SESSION_RITUALS.md`. Lower drift risk for a scaffold; the umbrella's three-file layout is right for its scale, not this one.
- Templates shipped as `000-template.md` in each of `docs/decisions/` and `docs/sessions/` so the shape is discoverable on first use.

## `[VERIFY:]` surfaced
- none

## `[INFERRED:]` made
- none

## Anything you noticed?

1. **Anything surprising about the codebase or task?** The scaffold's two-file ritual setup (`AGENTS.md` + `docs/conventions.md`) had near-duplicate session-ritual content even before this change — exactly the drift risk the umbrella's AGENTS-sync sweep guards against at larger scale. For a scaffold it stays manageable, but the duplication is real.
2. **Anything that should change in `AGENTS.md` or `STATUS.md`?** Nothing right now. The `[TODO]` blocks in `AGENTS.md` (Project Overview, Tech Stack, etc.) are intentional — they're the scaffold's user-facing fill-in points.
3. **Any `[VERIFY:]` or `[INFERRED:]` markers still unresolved?** None — this was a planning + writing turn, no claims about external systems were made.
4. **Anything the next session should not have to relearn?** Two things, captured in `STATUS.md` Lessons: (a) the session-end checklist now has 6 steps and lives in two files that must stay in sync; (b) the umbrella's multi-repo mirror discipline was looked at and deliberately rejected for the scaffold — don't re-propose it without a multi-repo use case.
