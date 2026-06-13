# Skill: No-Reimplementation Check

## Purpose

Prevent agents from duplicating or rebuilding functionality that already exists in the repository.

## Failure modes this skill addresses

- Reimplementing existing services
- Duplicate utilities
- Ignoring established architecture
- Creating parallel code paths
- Regression from not reading current tests

## When to use

Use before implementation, especially when the task touches an existing system, service, workflow, or command.

## Inputs / evidence required

- repository search for relevant names and concepts
- existing tests
- existing service/module boundaries
- project instructions
- recent related commits, if useful

## Agent must do

- Inspect likely existing implementations.
- Summarize what already exists.
- Identify extension points.
- State what should not be reimplemented.
- Ask for clarification if the task conflicts with existing architecture.

## Agent must not do

- Do not create a new module before checking for an existing one.
- Do not duplicate behavior under a new name.
- Do not bypass existing tests or services.
- Do not rewrite stable code because it is unfamiliar.

## Output format

Use: Existing Implementation Found, Reuse Plan, Files to Inspect, Do Not Reimplement, Proposed Change Boundary.

## Human review checklist

- [ ] Did the agent search for existing code paths?
- [ ] Did it read relevant tests?
- [ ] Did it name what will be reused?
- [ ] Did it define what will not be touched?
- [ ] Is the proposed change smaller because of the recon?

## Common failure modes of this skill

- The agent gives a generic summary without evidence.
- The agent turns a review skill into an implementation task.
- The agent hides missing validation.
- The agent proposes broad instruction changes based on one weak signal.
