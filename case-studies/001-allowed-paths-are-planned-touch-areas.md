# Case Study 001: Allowed Paths Are Planned Touch Areas

A coding agent in a real production repository misinterpreted a project-specific field named `allowedPaths`.

It treated the field as a hard write boundary. After the human challenged that interpretation and the agent inspected the repository policy, the agent corrected itself: in this project, `allowedPaths` meant planned touch areas, not a hard project-root write cage.

## Failure categories

- Context failure: the agent inferred policy from a field name instead of current project evidence.
- Scope failure: the agent risked shaping implementation around a misunderstood boundary.
- Evidence failure: validation status became unclear after a later change.
- Recovery failure: the working tree remained dirty and needed classification.
- Review failure: the human needed a structured report before deciding what to keep.

## What should have triggered

At task start:

```text
scope-control
before-you-code-recon
no-reimplementation-check
```

When interpreting `allowedPaths`:

```text
scope-control
safe-mutation-gate if edits move outside planned touch areas
```

When the human challenged the interpretation:

```text
pause implementation
session-retrospective or targeted evidence response
```

After a later fix:

```text
test-verification-report
```

When a dirty tree was detected:

```text
dirty-tree-audit
```

Before any project-instruction update:

```text
evidence-based-closeout
agents-md-improvement-review
```

## Extracted rules

```md
Execution contract `allowedPaths` means planned touch areas, not a hard project-root write cage.

Out-of-plan changes must be recorded as drift evidence and reviewed through the project workflow.

Protected paths remain hard blockers.
```

```md
When the user challenges an interpretation, asks why a blocker was claimed, or requests a retrospective, pause implementation.

Answer from current repo and session evidence first.
```

```md
Distinguish previous validation from validation after the latest code change.

Do not say a branch is passing unless the relevant validation completed after the latest change.
```

## Minimal recovery workflow

```text
1. Stop implementation.
2. Run dirty-tree-audit.
3. Run test-verification-report.
4. Decide whether the current slice should be committed, revised, or abandoned.
5. After implementation closeout, run agents-md-improvement-review.
6. Update project instructions only with the smallest rules that prevent repeated failure.
```

## Final lesson

Agent reliability improves when failure modes are turned into small, evidence-based workflow gates.
