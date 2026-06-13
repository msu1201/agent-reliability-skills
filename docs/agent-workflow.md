# Agent Workflow

Use the skills pack as a workflow layer:

```text
phase or signal -> skill -> decision -> next step
```

## Put the rules in AGENTS.md

Add `templates/AGENTS_RELIABILITY_PACK.md` to the target repository's `AGENTS.md`.

## Phase triggers

- Before implementation: `scope-control`, `before-you-code-recon`, `no-reimplementation-check`.
- Before broad changes: `safe-mutation-gate`.
- During validation: `test-verification-report`.
- Before handoff: `dirty-tree-audit`, `evidence-based-closeout`, `pr-handoff-summary`.
- After confusion or repeated failure: `session-retrospective`, then `agents-md-improvement-review` if instructions should be improved.

## Decision flow

Review skills should end with a decision:

```text
CONTINUE
REVISE
VALIDATE
AUDIT_DIRTY_TREE
ASK_HUMAN
CLOSEOUT
UPDATE_INSTRUCTIONS_LATER
```

The decision points to the next skill, recovery action, or human review.
