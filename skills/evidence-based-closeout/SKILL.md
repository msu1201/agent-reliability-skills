# Skill: Evidence-Based Closeout

## Purpose

Force a coding agent to end a task with concrete evidence: changed files, commands run, validation results, known risks, and reviewer guidance.

## Failure modes this skill addresses

- False completion claims
- Missing test evidence
- Vague handoff summaries
- Hidden dirty working tree
- Human cannot review what changed

## When to use

Use before the agent stops, opens a PR, or claims a task is complete.

## Inputs / evidence required

- `git status --short`
- `git diff --stat`
- relevant test/build/lint/typecheck commands
- known task acceptance criteria
- changed file paths

## Agent must do

- Report files changed and why.
- List commands actually run.
- Include pass/fail/skipped status.
- Identify risks and incomplete work.
- Keep claims proportional to evidence.

## Agent must not do

- Do not say “tests pass” without command output.
- Do not omit skipped validation.
- Do not hide untracked or dirty files.
- Do not mark incomplete work as complete.

## Output format

Use: Summary, Files Changed, Validation, Risks, Incomplete Work, Reviewer Guidance, Suggested Next Step.

## Human review checklist

- [ ] Does it include `git status` or explain why not?
- [ ] Does it include a diff summary?
- [ ] Are validation commands named exactly?
- [ ] Are skipped checks explicit?
- [ ] Are risks and incomplete work visible?
- [ ] Can a reviewer decide what to inspect first?

## Common failure modes of this skill

- The agent gives a generic summary without evidence.
- The agent turns a review skill into an implementation task.
- The agent hides missing validation.
- The agent proposes broad instruction changes based on one weak signal.
