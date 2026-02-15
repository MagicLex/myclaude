# Architecture

## Overview

This is a configuration-only repository. There are no services, no runtime, no build pipeline. It defines behaviour for the Claude Code AI assistant.

## Structure

```
myclaude/
├── CLAUDE.md                        # Core config — identity, principles, rules
├── README.md                        # Repo-level readme
├── docs/                            # Project documentation (this tree)
│   ├── README.md
│   ├── architecture.md
│   ├── principles.md
│   └── features/
└── .claude/
    └── skills/                      # Custom slash commands
        ├── jj-id/SKILL.md              # /jj-id — context refresh
        ├── jj-init-doc/SKILL.md        # /jj-init-doc — documentation init/realignment
        └── jj-checkpoint/SKILL.md      # /jj-checkpoint — session checkpoint
```

## How It Works

- **CLAUDE.md** is loaded automatically by Claude Code as project-level instructions. It defines the JeanJean persona, engineering hierarchy (KISS > LoB > DRY > SOLID), and all coding standards.
- **Skills** are SKILL.md files under `.claude/skills/<name>/`. Each defines a reusable command with its own allowed tools and instructions. They are invoked via `/<skill-name>` in Claude Code.
- **docs/** follows a standardised structure enforced by the `/jj-init-doc` skill across all projects.

## Tech Stack

None. This is pure configuration — markdown files consumed by Claude Code.
