# AGENTS.md

**This file is the single source of truth for every coding agent working in this repo** (Gemini CLI, OpenAI Codex CLI, Cline, Claude Code, etc.). 
All tool-specific configuration files should be thin pointers back to this file. Edit project instructions **here**.

## Project Overview
[TODO: Insert 2-3 sentence description of the project and its core purpose.]

## Tech Stack
[TODO: List languages, frameworks, major dependencies, and tooling.]

## Multi-agent Setup
This repo is wired for several coding agents, all sharing **one** set of instructions in `AGENTS.md`. Edit project guidance there — the per-tool files are thin pointers:

| Tool             | File(s)                                              | Role                              |
| ---------------- | --------------------------------------------------- | --------------------------------- |
| **(all agents)** | `AGENTS.md`                                          | Single source of truth            |
| Claude Code      | `CLAUDE.md`                                          | Points to AGENTS.md               |
| Gemini CLI       | `GEMINI.md`                                          | Points to AGENTS.md               |
| OpenAI Codex CLI | `.codex/config.toml`                                 | Project model/approval settings   |
| Cline            | `.clinerules/01-agents.md`                           | Points to AGENTS.md               |

## Repo Layout
[TODO: Map out the critical directories and files so the agent knows where to look for what.]
- `.scratch/`: A git-ignored sandbox directory. Feel free to use this folder to write temporary scripts, test hypotheses, or dump API responses without muddying the main source tree.

## CLI Commands
[TODO: Document the primary commands for running, building, testing, and linting the project.]

## Docs & Session Rituals
Keep project documentation current. Foundational choices get a numbered ADR in `docs/decisions/`. Meaningful multi-commit work gets a log in `docs/sessions/` (`YYYY-MM-DD-slug.md`).

Session phrases (auto-load these):
- **Session start:** *"Catch me up — read AGENTS.md, STATUS.md, and the most recent docs/sessions/ entry. Briefly probe the local environment to see what CLI tools are available. Tell me where we are in 3 sentences, then wait for direction."*
- **Session end:** *"Run the session-end checklist, answer 'anything you noticed?', update documentation for any scope drift, commit, and push."*

### Plan-before-code gate
Before any non-trivial change (more than a typo, one-line fix, or pure question), state the plan in 2–3 sentences and wait for direction. The session-start phrase already requires reading STATUS.md and the latest session log; the gate makes the *output* explicit: name the files you intend to touch and the approach you intend to take before editing.

### "Anything you noticed?" closer
After the session-end checklist, answer four questions honestly — including when the answer is "no, all clear":
1. Anything surprising about the codebase or task?
2. Anything that should change in `AGENTS.md` or `STATUS.md`?
3. Any `[VERIFY:]` or `[INFERRED:]` markers still unresolved?
4. Anything the next session should not have to relearn?

Answers land as the final block of the session log.

## Environment & Tooling
This project may be developed across multiple OS environments (e.g. macOS, Windows).
- **Tool Discovery:** Do not assume 3rd-party CLI tools are installed. When tackling tasks that would benefit from them (like deep codebase searches or JSON wrangling), briefly probe the local environment (e.g., `rg --version`, `jq --version`) to see if optimized tools are available before falling back to slower native commands. If an optimized tool is not installed but would significantly improve the task, prompt the user to ask if they would like you to install it for them.

## Agent Behavioral Standards
- **Communication Style:** Be extremely concise. Do not apologize or use pleasantries. Do not write filler text. If you are generating code, just give me the code. If you hit an error, just fix it without explaining the theory unless asked.
- **Git Protocol:** Always use Conventional Commits (e.g., `feat:`, `fix:`, `docs:`, `refactor:`). Never push to `main` without ensuring tests pass.
- **Testing Protocol:** When adding a new feature, you must write a failing test first (TDD). You may not consider a task complete until the test suite runs clean. Use appropriate fixtures and avoid mocking the filesystem where real interaction is deterministic and safe.
- **Ambiguity:** If a requirement is underspecified, or if you encounter an architectural decision with multiple viable paths, **STOP**. Do not guess. Write out the options, their pros/cons, and ask the user to decide before you write any code.
- **Honesty markers:** Tag uncertain output inline so it can be reconciled later.
  - `[VERIFY: <claim>]` — a claim asserted without independent confirmation (file path that may have moved, behavior assumed from docs, external service shape).
  - `[INFERRED: <assumption>]` — a gap filled by a judgment call the user did not explicitly authorize.
  - Every marker emitted in a session rolls up into the session log under "`[VERIFY:]` surfaced" / "`[INFERRED:]` made", and into `STATUS.md` under "Open `[VERIFY:]`" / "Open `[INFERRED:]`" until resolved.

## Safety Rules for Agents
- [TODO: Add project-specific strict safety rules, e.g., "Never drop the production database", "Never write files outside the workspace", etc.]
