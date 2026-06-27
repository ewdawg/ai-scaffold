# Conventions

This file defines the strict workflow rituals and documentation standards for this repository.

## Session Rituals

Every AI coding session MUST begin and end with specific routines to ensure the repository remains documented and deterministic.

**Beginning a Session:**
Agents must read `AGENTS.md`, `STATUS.md`, and the most recent entry in `docs/sessions/` to catch up on context. They should not begin coding until they have verbally confirmed their understanding of the current state.

**Ending a Session:**
Every commit that ships a feature, fix, or architectural change MUST update documentation in the same commit. The agent must execute the following checklist before pushing:
1. Update `STATUS.md` by overwriting stale lines (never append history).
2. Prepend a new dated entry to `docs/CHANGELOG.md`.
3. If foundational architectural decisions were made, create a numbered ADR in `docs/decisions/`.
4. Run all linters and the test suite to ensure the build is perfectly clean.
