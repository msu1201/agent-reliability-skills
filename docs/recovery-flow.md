# Recovery Flow

Review skills should not only report problems. They should route the session toward recovery.

## Standard decisions

Every review skill should end with one of these decisions:

```text
CONTINUE
REVISE
VALIDATE
AUDIT_DIRTY_TREE
ASK_HUMAN
CLOSEOUT
UPDATE_INSTRUCTIONS_LATER
```

## Decision table

| Decision | Use when | Next step |
| --- | --- | --- |
| `CONTINUE` | no blocker is found | continue the current implementation plan |
| `REVISE` | the current patch is wrong, too broad, or incomplete | revise the patch before more work |
| `VALIDATE` | evidence is missing or stale | run `test-verification-report` |
| `AUDIT_DIRTY_TREE` | tracked or untracked changes are unclear | run `dirty-tree-audit` |
| `ASK_HUMAN` | a human decision is required | ask one specific question |
| `CLOSEOUT` | work is ready for final evidence | run `evidence-based-closeout` and possibly `pr-handoff-summary` |
| `UPDATE_INSTRUCTIONS_LATER` | a project-instruction improvement is needed later | record the candidate and run `agents-md-improvement-review` after closeout |

## Common recovery chains

### Validation gap

```text
test-verification-report
  -> VALIDATE
  -> run missing validation
  -> evidence-based-closeout
```

### Dirty working tree

```text
dirty-tree-audit
  -> classify tracked and untracked changes
  -> REVISE, ASK_HUMAN, or CLOSEOUT
```

### Scope drift

```text
session-retrospective or scope-control
  -> REVISE or ASK_HUMAN
  -> narrow current patch
  -> test-verification-report
```

### Context miss

```text
before-you-code-recon
  -> no-reimplementation-check
  -> REVISE if existing implementation was missed
```

### Weak handoff

```text
evidence-based-closeout
  -> pr-handoff-summary
  -> human review
```

### Repeated instruction failure

```text
session-retrospective
  -> UPDATE_INSTRUCTIONS_LATER
  -> finish current implementation closeout
  -> agents-md-improvement-review
  -> human reviews proposed instruction changes
```

## Principle

Do not let a review skill end with only a report.

A useful review skill must produce:

1. evidence
2. diagnosis
3. decision
4. next route
