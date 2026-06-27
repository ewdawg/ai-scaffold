# AI Agent Scaffold
*Created: June 27, 2026*

This repository is a **reusable template** designed to instantly kickstart AI-assisted coding projects. Its purpose is to provide a flawless, multi-agent baseline out-of-the-box so that you (and your AI coding agents) never have to waste time configuring rules, memory, or safety rails for a new project.

## What's included in this scaffold?

1. **A Single Source of Truth (`AGENTS.md`):** Strict behavioral rules (Conciseness, Conventional Commits, TDD) and instructions that all agents must follow.
2. **Multi-LLM Pointers:** Pre-configured connector files (`CLAUDE.md`, `GEMINI.md`, `.clinerules/01-agents.md`, `.codex/config.toml`) that seamlessly force Claude, Gemini, Cline, and Codex to all share `AGENTS.md`.
3. **Memory & Documentation:** `STATUS.md` and `docs/CHANGELOG.md` templates to enforce long-term memory across coding sessions.
4. **Universal CI/CD (`.github/workflows/ci.yml`):** A pre-configured MegaLinter GitHub Action that automatically detects your language and lints your code on every push.
5. **Rock-Solid Defaults:** A universal `.gitignore`, an `.env.example` template for API keys, an `.editorconfig` for formatting consistency, and a dedicated `.scratch/` sandbox directory for the AI.

## How to use this scaffold

1. **Clone it:** Use this as a GitHub Template Repository, or clone it locally:
   ```bash
   git clone https://github.com/ewdawg/ai-scaffold.git new-project
   cd new-project
   rm -rf .git  # Remove the scaffold's git history
   git init     # Start fresh
   ```
2. **Customize it:** Open `AGENTS.md` and `README.md` in your new project, search for the `[TODO]` blocks, and fill in the specifics about your new project's Tech Stack and Architecture.
3. **Start Coding:** Drop your favorite AI agent into the project. It will instantly read the rules, check the status, and know exactly how to behave.
