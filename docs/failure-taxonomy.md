# Coding-Agent Failure Taxonomy

This taxonomy groups common coding-agent failures into practical categories.

## 1. Scope failures

The agent does more, less, or different work than requested.

Examples:

- scope creep
- over-implementation
- continuing past the requested stopping point
- adding speculative features
- expanding a bug fix into a refactor

Relevant skills:

- `scope-control`
- `evidence-based-closeout`
- `session-retrospective`

## 2. Evidence failures

The agent makes claims without proof.

Examples:

- saying tests pass without running them
- vague “implemented successfully” reports
- no git diff summary
- no validation logs
- hiding skipped checks

Relevant skills:

- `evidence-based-closeout`
- `session-retrospective`

## 3. Context failures

The agent fails to inspect or respect the current project state.

Examples:

- reimplementing existing work
- ignoring AGENTS.md
- missing architecture conventions
- duplicating utilities
- not reading tests before changing behavior

Relevant skills:

- `no-reimplementation-check`
- `agents-md-improvement-review`

## 4. Mutation failures

The agent changes files unsafely.

Examples:

- deleting files without approval
- editing generated files as source
- broad formatting churn
- changing unrelated modules
- modifying migrations or lockfiles unnecessarily

Relevant skills:

- `safe-mutation-gate`
- `scope-control`

## 5. Review failures

The handoff is hard for the human to review.

Examples:

- no summary by file path
- no risk list
- no rollback note
- no reviewer guidance
- no explicit incomplete work

Relevant skills:

- `evidence-based-closeout`
- `session-retrospective`

## 6. Recovery failures

The agent keeps trying without stepping back.

Examples:

- repeated failed commands
- dependency guessing
- patching around symptoms
- no rollback point
- no replan after failure

Relevant skills:

- `session-retrospective`
- future skill: `failure-loop-breaker`
