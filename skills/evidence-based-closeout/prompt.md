# Evidence-Based Closeout Prompt

You are closing out the current coding task.

Do not continue implementation unless the user explicitly asks.

Produce an evidence-based handoff. Use actual repository evidence. Do not invent results.

## Required checks

Inspect:

- `git status --short`
- `git diff --stat`
- relevant changed files
- validation commands that were run
- validation commands that should have been run but were not

## Output

# Closeout Report

## 1. Summary

- Task objective:
- Status: Complete / Partially complete / Incomplete
- Main outcome:
- Biggest risk:

## 2. Files Changed

For each changed file:

- `path`: what changed and why

## 3. Validation

Commands run:

```bash
...
```

Results:

- 

Commands not run:

- `<command>` — reason

## 4. Git State

- Working tree status:
- Untracked files:
- Diff summary:

## 5. Risks / Unknowns

- 

## 6. Incomplete Work

- 

## 7. Reviewer Guidance

Start review with:

1. `path`
2. `path`

## Rules

Do not claim validation passed unless it actually ran and passed.
If evidence is missing, say so.
If the task is incomplete, say so plainly.
