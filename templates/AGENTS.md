# AGENTS.md

This file gives coding agents durable project instructions.

## General rules

- Follow the current task scope exactly.
- Do not reimplement existing functionality without first inspecting the current implementation.
- Prefer small, reviewable changes.
- Do not modify unrelated files.
- Do not claim tests or builds pass unless they were actually run and passed.
- If validation cannot be run, say why and describe the risk.

## Before implementation

Before writing code, summarize:

- what already exists
- which files are likely relevant
- what you plan to change
- what you will not change

## During implementation

- Keep changes PR-sized.
- Avoid speculative cleanup.
- Preserve existing architecture and naming conventions.
- Stop and report if the task requires destructive or broad mutation.

## Before handoff

Provide:

- git status summary
- files changed
- tests/builds run
- results
- known risks
- incomplete work
- reviewer guidance

## Recommended skills

Use the following skills from `agent-reliability-skills` when appropriate:

- `scope-control`
- `no-reimplementation-check`
- `safe-mutation-gate`
- `evidence-based-closeout`
- `session-retrospective`
- `agents-md-improvement-review`
