# Skill: Safe Mutation Gate

## Purpose

Require explicit review before destructive, broad, or hard-to-rollback repository changes.

## Failure modes this skill addresses

- Unsafe deletions
- Broad formatting churn
- Accidental migration changes
- Lockfile churn
- Generated file edits
- Unclear rollback path

## When to use

Use before deleting files, moving files, mass-renaming, changing migrations, modifying lockfiles, broad formatting, or touching security-sensitive code.

## Inputs / evidence required

- exact files to mutate
- reason for mutation
- risk level
- rollback plan
- validation plan
- confirmation requirement

## Agent must do

- List every risky mutation.
- Explain why it is needed.
- Provide rollback instructions.
- Ask for approval when risk is high or scope is broad.
- Prefer minimal reversible changes.

## Agent must not do

- Do not delete files silently.
- Do not run broad formatters without approval.
- Do not modify generated files as source.
- Do not change lockfiles unless dependency changes require it.
- Do not touch secrets or credentials.

## Output format

Use: Proposed Mutation, Risk Level, Why Needed, Alternatives, Rollback Plan, Validation Plan, Approval Needed.

## Human review checklist

- [ ] Are risky files listed exactly?
- [ ] Is the mutation necessary?
- [ ] Is there a rollback plan?
- [ ] Is approval requested for broad/destructive changes?
- [ ] Are secrets and generated files protected?

## Common failure modes of this skill

- The agent gives a generic summary without evidence.
- The agent turns a review skill into an implementation task.
- The agent hides missing validation.
- The agent proposes broad instruction changes based on one weak signal.
