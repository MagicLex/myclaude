---
name: jj-checkpoint
description: Session checkpoint — summarize progress, check docs, check git state
disable-model-invocation: true
allowed-tools: Bash, Read, Grep, Glob
---

Run a session checkpoint. Do the following in order:

## 1. Progress Summary

Write a concise summary (1-2 short paragraphs max):
- What has been done this session
- What remains to be done (if anything)

Be factual, no fluff. Reference files changed and decisions made.

## 2. Documentation Check

Check if project documentation (README, CLAUDE.md, any relevant docs) is still accurate given the work done. Flag anything outdated or missing. If everything is current, say so briefly.

## 3. Git State

Run `git status` and `git log origin/main..HEAD --oneline` to determine:
- Are there uncommitted changes?
- Are there unpushed commits?

Report the state clearly. If there's something to push or commit, say so. Do not push or commit automatically — just report.
