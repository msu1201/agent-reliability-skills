# Skill: PR Handoff Summary

## Purpose

Produce a reviewer-friendly handoff that explains what changed, why it changed, how it was validated, what risks remain, and how to roll back.

This skill prevents review failures where humans cannot quickly understand or safely review the agent's work.

## Failure modes this skill addresses

- No PR summary
- No risk list
- No rollback notes
- No reviewer guidance
- No file-by-file explanation
- Hiding incomplete work

## When to use

Use before opening a PR, creating a final handoff comment, or asking a human to review a coding-agent change.

Use after `evidence-based-closeout` or alongside it.

## Inputs / evidence required

- current diff summary
- changed file list
- test/validation evidence
- known risks and tradeoffs
- related issue/task/acceptance criteria
- rollback or revert considerations

## Agent must do

- Summarize the change in reviewer-oriented language.
- Group changes by file or subsystem.
- Explain validation that actually ran.
- Identify risks and unresolved questions.
- Provide reviewer guidance.
- Include rollback notes.

## Agent must not do

- Do not hide incomplete work.
- Do not claim validation that did not run.
- Do not bury risky changes in generic wording.
- Do not include unrelated marketing language.
- Do not open or merge a PR unless explicitly asked.

## Output format

Use this structure:

```md
# PR Handoff Summary

## 1. Summary

## 2. What Changed

## 3. File-by-File Notes

## 4. Validation

## 5. Risks / Tradeoffs

## 6. Reviewer Guidance

## 7. Rollback Notes

## 8. Not Included
```

## Human review checklist

- [ ] Can the reviewer understand the change in under two minutes?
- [ ] Are risky files called out?
- [ ] Is validation evidence specific?
- [ ] Are rollback notes useful?
- [ ] Are out-of-scope or unfinished items explicit?

## Common failure modes of this skill

- The agent writes a generic “implemented X” summary.
- The agent omits files that are hard to justify.
- The agent claims broad validation from narrow tests.
- The agent gives no reviewer focus areas.
- The agent confuses a handoff summary with a commit message.
