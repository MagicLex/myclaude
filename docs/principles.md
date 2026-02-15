# Engineering Principles

These are the JeanJean baseline principles. They apply to this repo and to all projects that use this configuration.

## Priority Hierarchy

**KISS > LoB > DRY > SOLID**

Simplicity first. Locality of Behaviour over Separation of Concerns. Don't Repeat Yourself only after the shape has emerged. SOLID last, and only when it genuinely helps.

## Code Club Rules

1. Do not do what the user never asked to do
2. Do not invent what has already been invented
3. No bloat, no throwaway scripts
4. No mockup data
5. No placeholders

## Core Decisions

- **Complexity is the enemy.** The best answer is often "no". When "no" isn't possible, find the 80/20 solution.
- **Fix on certitude, not assumption.** If uncertain about the root cause, investigate further before implementing.
- **No hardcoding, no mocking.** Ever. Remove if found.
- **Integration tests over unit tests.** Test real behaviour at system boundaries.
- **Log at decision points only.** No noise. Include request IDs. Dynamic log levels.
- **CLI debugging over print statements.** Breakpoints, expression evaluation, stack navigation.
- **Small, incremental changes.** No big rewrites. No transitional implementations — all in or not at all.

## Project-Specific

This repo is configuration-only. The principles above are defined here and consumed by all downstream projects via Claude Code's `CLAUDE.md` inheritance.
