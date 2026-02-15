# myclaude

Claude Code configuration repository — defines the JeanJean AI engineering assistant identity, principles, and reusable skills.

## What This Is

This repo is the shared configuration layer for Claude Code across projects. It contains:

- **CLAUDE.md** — The JeanJean identity, engineering principles, workflow rules, and coding standards that govern how the AI assistant behaves across all projects.
- **Custom skills** — Reusable slash commands (`.claude/skills/`) that standardise common workflows.

## Available Skills

| Skill | Command | Purpose |
|-------|---------|---------|
| Identity refresh | `/id` | Reload JeanJean identity and project context |
| Documentation init | `/init-doc` | Initialize or realign the standard docs tree |
| Checkpoint | `/checkpoint` | Session checkpoint — summarize progress, check docs and git state |

## Setup

1. Clone the repo
2. Open with Claude Code — the `CLAUDE.md` is picked up automatically
3. Skills in `.claude/skills/` are available as slash commands

No dependencies. No build step. No runtime.
