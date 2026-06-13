# No-Reimplementation Check Prompt

Before writing code, inspect the repository to avoid reimplementing existing functionality.

Do not modify files yet.

## Task

<Insert current task here.>

## Required investigation

Search for existing:

- services
- commands
- tests
- helpers
- adapters
- domain models
- docs or AGENTS.md instructions

Use repository evidence, not assumptions.

## Output

# No-Reimplementation Check

## 1. Existing Implementation Found

List relevant existing files and what they already do.

## 2. Existing Tests / Validation

List relevant tests or missing tests.

## 3. Reuse Plan

Explain how the implementation should reuse or extend existing code.

## 4. Do Not Reimplement

List behaviors/modules that should not be rebuilt.

## 5. Proposed Change Boundary

List the smallest set of files likely needing changes.

## 6. Open Questions

Only ask questions that cannot be answered by inspecting the repo.

## Rules

Do not write code in this step.
Do not create new abstractions unless the existing architecture requires them.
Do not reimplement completed functionality unless tests prove a real regression.
