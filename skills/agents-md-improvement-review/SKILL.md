# Skill: AGENTS.md Improvement Review

## Purpose

Convert repeated or important agent failures into concrete, reviewable AGENTS.md update proposals without directly editing AGENTS.md.

## Failure modes this skill addresses

- Overloading AGENTS.md with too many rules
- Vague project instructions
- Repeated agent mistakes never becoming reusable guidance
- One-off frustrations becoming permanent noisy rules
- Agent directly editing instructions without review

## When to use

Use after a session retrospective, repeated agent failure, or when the human asks whether project instructions should be updated.

## Inputs / evidence required

- session retrospective
- current AGENTS.md
- observed failure patterns
- task prompts that led to confusion
- examples of desired behavior

## Agent must do

- Identify only instruction changes supported by evidence.
- Separate AGENTS.md changes from task-prompt changes.
- Provide exact proposed wording.
- Explain tradeoffs.
- Recommend not updating AGENTS.md if the issue is one-off.

## Agent must not do

- Do not directly edit AGENTS.md.
- Do not add vague rules.
- Do not add rules based on weak evidence.
- Do not make AGENTS.md a dumping ground for task-specific details.

## Output format

Use: Observed Pattern, Root Cause, Belongs In, Proposed Text, Priority, Tradeoff, Recommendation.

## Human review checklist

- [ ] Is each proposal tied to a real observed pattern?
- [ ] Is exact wording provided?
- [ ] Is the target location clear: AGENTS.md, task prompt, or docs?
- [ ] Are must-have and nice-to-have changes separated?
- [ ] Does the review recommend no change where appropriate?

## Common failure modes of this skill

- The agent gives a generic summary without evidence.
- The agent turns a review skill into an implementation task.
- The agent hides missing validation.
- The agent proposes broad instruction changes based on one weak signal.
