# Skill: Test Verification Report

## Purpose

Prevent vague or false validation claims by requiring the agent to report exactly which tests or checks were run, when they were run, and what evidence exists after the latest code change.

## Failure modes this skill addresses

- Claiming tests passed without running them
- Vague completion reports
- No validation trail
- Confusing previous validation with current post-change validation
- Hiding skipped, interrupted, or failed checks

## When to use

Use after code changes and before any completion claim, handoff, commit, or PR summary.

Use it especially when:

- a fix was made after tests previously passed
- a test command was interrupted
- only focused tests were run
- CI is unavailable
- the agent says “should pass” instead of showing evidence

## Inputs / evidence required

- current diff or list of changed files
- commands actually run
- command outputs or summarized results
- timestamps or sequence relative to latest change when available
- known skipped checks
- known interrupted or failed checks

## Agent must do

- List every validation command actually run.
- Distinguish validation before the latest change from validation after the latest change.
- Report skipped, interrupted, or failed commands explicitly.
- Explain what each command covers.
- State remaining validation gaps.
- Avoid implying pass status without evidence.

## Agent must not do

- Do not say “tests pass” unless relevant validation completed after the latest code change.
- Do not infer success from a previous run.
- Do not hide interrupted commands.
- Do not replace validation evidence with confidence language.
- Do not claim CI status unless CI was actually checked.

## Output format

Use this structure:

```md
# Test Verification Report

## 1. Latest Code Change Boundary

## 2. Commands Run After Latest Change

## 3. Commands Run Before Latest Change

## 4. Skipped / Interrupted / Failed Checks

## 5. Coverage Explanation

## 6. Remaining Validation Gaps

## 7. Honest Status
```

## Human review checklist

- [ ] Does the report distinguish current validation from previous validation?
- [ ] Are exact commands listed?
- [ ] Are interrupted and skipped checks visible?
- [ ] Does the agent avoid unsupported “passing” claims?
- [ ] Are validation gaps clear enough for a reviewer to decide next steps?

## Common failure modes of this skill

- The agent lists commands it intended to run but did not run.
- The agent reports old test results as current.
- The agent omits skipped checks.
- The agent says “only docs changed” without verifying the diff.
- The agent buries the real status in optimistic language.
