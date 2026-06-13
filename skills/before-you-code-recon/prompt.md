# Before You Code Recon Prompt

Pause implementation. Do not modify files yet.

Your task is to inspect the current repository state and produce a short recon report before coding.

## Required evidence

Inspect:

- `git status --short --branch`
- project instructions such as `AGENTS.md`, `CLAUDE.md`, or equivalent if present
- relevant source files
- relevant tests
- relevant docs or design notes
- recent commits if they clarify current direction

## Rules

- Do not edit files.
- Do not create new abstractions yet.
- Do not assume existing behavior is missing until you inspect the repo.
- If the task boundary is unclear, stop and ask.
- If evidence is missing, say exactly what is missing.

## Output format

```md
# Before You Code Recon

## 1. Current Repo State

- Branch:
- Dirty files:
- Untracked files:
- Relevant recent commits:

## 2. Instructions Found

List project instructions inspected and the rules that matter for this task.

## 3. Existing Code Paths

List source files/functions/classes that already relate to the task.

## 4. Relevant Tests

List tests that cover or should cover this behavior.

## 5. Architecture Conventions

List naming, layering, persistence, CLI, API, or UI conventions that must be preserved.

## 6. Planned Change Surface

List files likely to be touched and why.

## 7. Open Questions / Blockers

List only questions that cannot be answered by inspecting the repo.

## 8. Implementation Plan

Give a small, PR-sized plan with validation commands.
```
