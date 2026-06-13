# Skill: Scope Control

## Purpose

Keep an agent inside a clear, PR-sized implementation boundary and prevent speculative work.

## Failure modes this skill addresses

- Scope creep
- Over-implementation
- Changing unrelated files
- Continuing past the requested stopping point
- Turning a bug fix into a rewrite

## When to use

Use at the beginning of a task, before a large diff, or whenever the agent seems likely to expand scope.

## Inputs / evidence required

- task objective
- allowed files or areas
- forbidden files or areas
- acceptance criteria
- stopping condition
- validation commands

## Agent must do

- Restate the task boundary.
- Identify allowed and forbidden changes.
- Define acceptance evidence.
- Define a stopping condition.
- Ask before expanding scope.

## Agent must not do

- Do not add speculative features.
- Do not do broad cleanup.
- Do not modify unrelated files.
- Do not continue to the next milestone without explicit instruction.

## Output format

Use: Objective, In Scope, Out of Scope, Allowed Files, Forbidden Changes, Acceptance Evidence, Stop Condition.

## Human review checklist

- [ ] Is the objective narrow?
- [ ] Is out-of-scope explicit?
- [ ] Are forbidden changes named?
- [ ] Is there a stop condition?
- [ ] Does validation match the scope?

## Common failure modes of this skill

- The agent gives a generic summary without evidence.
- The agent turns a review skill into an implementation task.
- The agent hides missing validation.
- The agent proposes broad instruction changes based on one weak signal.
