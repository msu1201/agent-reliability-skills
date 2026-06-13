# Test Verification Report Prompt

Pause completion claims. Do not modify files.

Your task is to produce an evidence-based validation report for the current work.

## Required behavior

- Identify the latest code or documentation change boundary.
- List validation commands actually run after that latest change.
- Separately list validation commands run before the latest change.
- Report interrupted, skipped, or failed checks honestly.
- Do not claim the branch is passing unless the relevant checks completed after the latest change.

## Output format

```md
# Test Verification Report

## 1. Latest Change Boundary

Describe the latest change that validation must cover.

## 2. Commands Run After Latest Change

| Command | Result | Covers | Evidence |
| --- | --- | --- | --- |

## 3. Commands Run Before Latest Change

| Command | Result | Why it is not current enough |
| --- | --- | --- |

## 4. Skipped / Interrupted / Failed Checks

| Command | Status | Reason | Impact |
| --- | --- | --- | --- |

## 5. Coverage Explanation

Explain what the completed checks do and do not prove.

## 6. Remaining Validation Gaps

List what still needs to be run or reviewed.

## 7. Honest Status

Choose one:

- Passing after latest change
- Partially validated
- Not validated
- Failed validation
- Validation interrupted

Explain why.
```
