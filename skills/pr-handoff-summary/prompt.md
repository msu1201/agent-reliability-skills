# PR Handoff Summary Prompt

Prepare a reviewer-friendly PR handoff summary.

Do not modify files. Do not open, merge, or close a PR unless explicitly asked.

## Required evidence

Inspect or use available evidence for:

- changed files
- diff summary
- validation commands and results
- known risks
- related task or acceptance criteria
- rollback considerations

## Output format

```md
# PR Handoff Summary

## 1. Summary

Explain the change in 3-6 bullets.

## 2. What Changed

Group changes by subsystem or behavior.

## 3. File-by-File Notes

| File | Purpose | Review focus |
| --- | --- | --- |

## 4. Validation

List exact commands run and results. Distinguish previous validation from current validation.

## 5. Risks / Tradeoffs

List known risks, edge cases, and assumptions.

## 6. Reviewer Guidance

Tell the reviewer where to focus first.

## 7. Rollback Notes

Explain how to safely revert or disable the change if needed.

## 8. Not Included

List things intentionally left out of scope.
```
