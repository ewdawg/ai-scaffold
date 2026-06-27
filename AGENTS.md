# AGENTS.md

**This file is the single source of truth for every coding agent working in this repo** (Gemini CLI, OpenAI Codex CLI, Cline, Claude Code, etc.). 
All tool-specific configuration files should be thin pointers back to this file. Edit project instructions **here**.

## Project Overview
[TODO: Insert 2-3 sentence description of the project and its core purpose.]

## Tech Stack
[TODO: List languages, frameworks, major dependencies, and tooling.]

## Repo Layout
[TODO: Map out the critical directories and files so the agent knows where to look for what.]

## CLI Commands
[TODO: Document the primary commands for running, building, testing, and linting the project.]

## Docs & Session Rituals
Keep project documentation current. Foundational choices get a numbered ADR in `docs/decisions/`. Meaningful multi-commit work gets a log in `docs/sessions/` (`YYYY-MM-DD-slug.md`).

Session phrases (auto-load these):
- **Session start:** *"Catch me up — read AGENTS.md and the most recent docs/sessions/ entry. Briefly probe the local environment to see what CLI tools are available. Tell me where we are in 3 sentences, then wait for direction."*
- **Session end:** *"Run the session-end checklist, update documentation for any scope drift, commit, and push."*

## Environment & Tooling
This project may be developed across multiple OS environments (e.g. macOS, Windows).
- **Tool Discovery:** Do not assume 3rd-party CLI tools are installed. When tackling tasks that would benefit from them (like deep codebase searches or JSON wrangling), briefly probe the local environment (e.g., `rg --version`, `jq --version`) to see if optimized tools are available before falling back to slower native commands. If an optimized tool is not installed but would significantly improve the task, prompt the user to ask if they would like you to install it for them.

## Agent Behavioral Standards
- **Communication Style:** Be extremely concise. Do not apologize or use pleasantries. Do not write filler text. If you are generating code, just give me the code. If you hit an error, just fix it without explaining the theory unless asked.
- **Git Protocol:** Always use Conventional Commits (e.g., `feat:`, `fix:`, `docs:`, `refactor:`). Never push to `main` without ensuring tests pass.
- **Testing Protocol:** When adding a new feature, you must write a failing test first (TDD). You may not consider a task complete until the test suite runs clean. Use appropriate fixtures and avoid mocking the filesystem where real interaction is deterministic and safe.
- **Ambiguity:** If a requirement is underspecified, or if you encounter an architectural decision with multiple viable paths, **STOP**. Do not guess. Write out the options, their pros/cons, and ask the user to decide before you write any code.

## Safety Rules for Agents
- [TODO: Add project-specific strict safety rules, e.g., "Never drop the production database", "Never write files outside the workspace", etc.]
