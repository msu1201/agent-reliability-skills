# Skill: Dirty Tree Audit

## Purpose

Make the agent explain every tracked and untracked change before committing, cleaning, reverting, or handing off work.

This skill prevents dirty-state recovery failures where scratch files, generated output, unrelated edits, or incomplete changes are left unexplained.

## Failure modes this skill addresses

- Leaving dirty state unexplained
- Changing unrelated files
- Unsafe file deletion
- Committing without approval
- No git diff summary
- No reviewer guidance

## When to use

Use when the working tree is dirty, especially before:

- commit
- PR creation
- cleanup
- revert
- handoff
- switching tasks
- updating project instructions such as AGENTS.md

## Inputs / evidence required

- `git status --short --branch`
- `git diff --stat`
- `git diff --name-only`
- tracked file diffs
- untracked file or directory listing
- `.gitignore` if generated files are involved
- task scope / acceptance criteria

## Agent must do

- List tracked modified files.
- List untracked files or directories.
- Classify each change as intended, generated, scratch, unrelated, or unknown.
- Recommend keep/revise/revert/delete/ignore for each item.
- Explain safety before deleting or reverting anything.
- Ask for human approval before destructive cleanup unless already authorized.

## Agent must not do

- Do not delete untracked files without classification.
- Do not commit unrelated or unknown changes.
- Do not hide generated output.
- Do not assume untracked files are safe to delete.
- Do not mix cleanup with new implementation.

## Output format

Use this structure:

```md
# Dirty Tree Audit

## 1. Current Git State

## 2. Tracked Changes

## 3. Untracked Files / Directories

## 4. Classification

## 5. Recommended Actions

## 6. Safety Notes

## 7. Human Decisions Needed
```

## Human review checklist

- [ ] Are tracked changes listed by path?
- [ ] Are untracked files or directories listed?
- [ ] Is each item classified?
- [ ] Are destructive actions separated from non-destructive actions?
- [ ] Does the agent ask before deleting or reverting anything risky?

## Common failure modes of this skill

- The agent summarizes only tracked changes and ignores untracked files.
- The agent says “cleanup complete” without listing what was removed.
- The agent treats all untracked files as scratch.
- The agent commits generated output accidentally.
- The agent combines cleanup with unrelated implementation work.
