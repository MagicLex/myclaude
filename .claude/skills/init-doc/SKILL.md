---
name: init-doc
description: Initialize or realign the standard documentation tree for a project
disable-model-invocation: true
allowed-tools: Bash, Read, Write, Glob, Grep
argument-hint: "[project-name]"
---

Initialize the standard documentation structure for this project. This is the enforced doc tree for all projects.

## Required Structure

```
docs/
├── README.md          # Project overview — what it is, how to run it
├── architecture.md    # System architecture — components, data flow, infra
├── principles.md      # Engineering principles specific to this project
└── features/
    └── .gitkeep       # Feature docs go here as name.md per feature
```

## Instructions

1. **Read the codebase first.** Understand what actually exists — files, structure, stack, features, config.

2. **Check if `docs/` already exists.** If it does, this is a **realignment run** — compare each doc against the current codebase and update what has drifted. If it doesn't exist, this is a fresh init.

3. **docs/README.md** — Project name ($0 if provided, otherwise infer from repo), what it does, how to set it up, how to run it. Keep it practical.

4. **docs/architecture.md** — Components, how they connect, tech stack, data flow. If the project is early stage, document what exists now and flag what's not yet decided.

5. **docs/principles.md** — Engineering principles for this specific project. Start from the JeanJean baseline (KISS > LoB > DRY > SOLID, no bloat, integration tests over unit tests) and add any project-specific decisions or conventions.

6. **docs/features/** — Create the directory with a `.gitkeep` on fresh init. Features get documented individually as `docs/features/feature-name.md` as they are built. On realignment, check existing feature docs against the code — update or flag stale ones.

## Drift Detection (on existing docs)

When docs already exist, compare each file against the codebase:

- **README.md** — Is the setup process still accurate? Are listed commands still valid? Any new dependencies missing?
- **architecture.md** — Do the described components still match reality? New services, removed modules, changed data flow?
- **principles.md** — Any new project-specific conventions that emerged from the code but aren't documented?
- **features/*.md** — Do feature docs match current implementation? Any features added/removed without doc updates?

For each drift found:
- State clearly what drifted and what reality is now
- Update the doc to match the code — code is the source of truth
- Report what was changed at the end

## Rules

- Code is truth, docs follow — never the other way around
- Write docs based on what the codebase actually contains — no fiction
- If the project is empty/new, keep docs minimal and honest ("Project is in early stage, architecture TBD")
- No placeholder text like "TODO" or "Lorem ipsum"
- Keep each file focused on its concern — that's why they're separated
