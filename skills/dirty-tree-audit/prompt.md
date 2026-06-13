# Dirty Tree Audit Prompt

Pause new implementation.

Your task is to inspect the current dirty working tree and explain what should happen next.

Do not delete files.
Do not revert files.
Do not commit files.
Do not continue feature work.

## Required commands / evidence

Use the local equivalent of:

- `git status --short --branch`
- `git diff --stat`
- `git diff --name-only`
- inspect tracked diffs as needed
- list untracked files or directories
- inspect `.gitignore` if generated files are involved

## Output format

```md
# Dirty Tree Audit

## 1. Current Git State

- Branch:
- Ahead/behind:
- Tracked changes:
- Untracked files/directories:

## 2. Tracked Changes

| Path | Summary | Classification | Recommended action |
| --- | --- | --- | --- |

Classifications:

- intended project change
- generated output
- scratch / temporary
- unrelated change
- unknown

## 3. Untracked Files / Directories

| Path | Contents summary | Classification | Safe to delete? | Recommended action |
| --- | --- | --- | --- | --- |

## 4. Safety Notes

Explain any destructive action that would require approval.

## 5. Human Decisions Needed

List decisions the human must make before cleanup, revert, commit, or handoff.

## 6. Recommended Next Step

Choose one:

- commit coherent slice
- revise before commit
- clean generated/scratch files after approval
- revert unrelated changes after approval
- ask human for decision
```
