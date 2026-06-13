# Skill: Before You Code Recon

## Purpose

Force a coding agent to inspect the current repo state, project instructions, architecture, tests, and existing implementations before making code changes.

This skill prevents context failures where the agent starts editing from assumptions instead of evidence.

## Failure modes this skill addresses

- Not inspecting current state
- Ignoring AGENTS.md
- Missing architecture conventions
- Reimplementing existing work
- Duplicating utilities or fixtures
- Solving the wrong task because the repo was not inspected

## When to use

Use before implementation starts, especially when:

- the task touches existing behavior
- the repo has AGENTS.md or project-specific rules
- the task references previous work
- the agent is likely to create new files or abstractions
- there is a risk of reimplementation

## Inputs / evidence required

- user task prompt
- `git status --short --branch`
- relevant project instructions, especially AGENTS.md if present
- relevant source files
- relevant tests
- relevant docs or design notes
- recent commits or PRs if they clarify current direction

## Agent must do

- Inspect current repo state before editing.
- Read project instructions before planning changes.
- Identify existing code paths that may already solve the task.
- Identify architecture conventions to preserve.
- Identify relevant tests and validation commands.
- Produce a short recon report before implementation.

## Agent must not do

- Do not start editing before recon is complete.
- Do not create a new abstraction before checking for an existing one.
- Do not assume AGENTS.md is irrelevant.
- Do not treat missing knowledge as permission to guess.
- Do not continue if the task boundary is unclear.

## Output format

Use this structure:

```md
# Before You Code Recon

## 1. Current Repo State

## 2. Instructions Found

## 3. Existing Code Paths

## 4. Relevant Tests

## 5. Architecture Conventions

## 6. Planned Change Surface

## 7. Open Questions / Blockers

## 8. Implementation Plan
```

## Human review checklist

- [ ] Did the agent inspect AGENTS.md or explain why none exists?
- [ ] Did the agent inspect relevant source files before proposing changes?
- [ ] Did the agent find existing tests or validation commands?
- [ ] Did the agent avoid reimplementation?
- [ ] Is the planned change surface narrow and evidence-based?

## Common failure modes of this skill

- The agent gives a generic plan without file evidence.
- The agent reads docs but not source.
- The agent reads source but not tests.
- The agent treats recon as permission to broaden scope.
- The agent starts coding while still listing open questions.
