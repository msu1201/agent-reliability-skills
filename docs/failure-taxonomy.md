# Coding-Agent Failure Taxonomy

This taxonomy groups common coding-agent failures into practical categories. The repo is organized around these categories first, then skills.

Use the taxonomy to decide which skill should be applied before, during, or after a coding-agent session.

## Failure categories

```text
1. Scope failures
   - scope creep
   - over-implementation
   - solving the wrong task
   - continuing when it should stop

2. Evidence failures
   - claiming tests passed without running them
   - vague completion reports
   - missing git diff summary
   - no validation trail

3. Context failures
   - reimplementing existing work
   - ignoring AGENTS.md
   - missing architecture conventions
   - not inspecting current state

4. Mutation failures
   - unsafe file deletion
   - broad refactors
   - changing unrelated files
   - committing without approval

5. Review failures
   - no PR summary
   - no risk list
   - no rollback notes
   - no reviewer guidance

6. Recovery failures
   - repeated failed commands
   - no diagnosis loop
   - hiding uncertainty
   - leaving dirty state unexplained
```

## 1. Scope failures

The agent does more, less, or different work than requested.

Common symptoms:

- scope creep
- over-implementation
- solving the wrong task
- continuing when it should stop
- adding speculative features
- expanding a bug fix into a refactor

Primary skills:

- `scope-control`
- `session-retrospective`
- `evidence-based-closeout`

## 2. Evidence failures

The agent makes claims without proof.

Common symptoms:

- claiming tests passed without running them
- vague completion reports
- missing git diff summary
- no validation trail
- hiding skipped checks
- confusing previous validation with current post-change validation

Primary skills:

- `evidence-based-closeout`
- `test-verification-report`
- `session-retrospective`

## 3. Context failures

The agent fails to inspect or respect the current project state.

Common symptoms:

- reimplementing existing work
- ignoring AGENTS.md
- missing architecture conventions
- not inspecting current state
- duplicating utilities
- not reading tests before changing behavior

Primary skills:

- `before-you-code-recon`
- `no-reimplementation-check`
- `agents-md-improvement-review`

## 4. Mutation failures

The agent changes files unsafely.

Common symptoms:

- unsafe file deletion
- broad refactors
- changing unrelated files
- committing without approval
- editing generated files as source
- broad formatting churn
- modifying migrations or lockfiles unnecessarily

Primary skills:

- `safe-mutation-gate`
- `scope-control`
- `dirty-tree-audit`

## 5. Review failures

The handoff is hard for the human to review.

Common symptoms:

- no PR summary
- no risk list
- no rollback notes
- no reviewer guidance
- no summary by file path
- no explicit incomplete work

Primary skills:

- `pr-handoff-summary`
- `evidence-based-closeout`
- `dirty-tree-audit`
- `session-retrospective`

## 6. Recovery failures

The agent keeps trying without stepping back.

Common symptoms:

- repeated failed commands
- no diagnosis loop
- hiding uncertainty
- leaving dirty state unexplained
- dependency guessing
- patching around symptoms
- no rollback point
- no replan after failure

Primary skills:

- `session-retrospective`
- `dirty-tree-audit`
- `agents-md-improvement-review`

## Skill map

```text
scope-control/
session-retrospective/
evidence-based-closeout/
before-you-code-recon/
safe-mutation-gate/
no-reimplementation-check/
test-verification-report/
pr-handoff-summary/
dirty-tree-audit/
agents-md-improvement-review/
```

## How to choose a skill

- Before coding: use `scope-control`, `before-you-code-recon`, and `no-reimplementation-check`.
- Before risky edits: use `safe-mutation-gate`.
- Before saying tests passed: use `test-verification-report`.
- Before handoff or commit: use `dirty-tree-audit`, `evidence-based-closeout`, and `pr-handoff-summary`.
- After confusion, drift, or repeated failures: use `session-retrospective` and `agents-md-improvement-review`.
