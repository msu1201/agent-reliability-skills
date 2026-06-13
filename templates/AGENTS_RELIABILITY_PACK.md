# AGENTS Reliability Pack Template

Copy this section into a target repository's `AGENTS.md` and adjust paths as needed.

```md
## Agent Reliability Skills Pack

This repository uses the Agent Reliability Skills Pack installed at `.agent/agent-reliability-skills/`.

These skills are workflow gates. When a trigger condition matches, read the relevant `SKILL.md` and follow the corresponding `prompt.md` behavior.

### Skill triggers

- New task or broad task: `scope-control`.
- Existing behavior or unknown repo state: `before-you-code-recon`.
- Possible duplicate implementation: `no-reimplementation-check`.
- Broad refactor, generated-file change, config change, or out-of-plan edit: `safe-mutation-gate`.
- Validation claim, interrupted test, post-test fix, or unclear validation status: `test-verification-report`.
- Dirty working tree or untracked files: `dirty-tree-audit`.
- Task completion claim: `evidence-based-closeout`.
- Human review or PR handoff: `pr-handoff-summary`.
- Challenged interpretation, drift, repeated failed commands, or ambiguous session state: `session-retrospective`.
- Repeated instruction gap after implementation closeout: `agents-md-improvement-review`.

### Review decisions

Review skills must end with one of these decisions:

- `CONTINUE`
- `REVISE`
- `VALIDATE`
- `AUDIT_DIRTY_TREE`
- `ASK_HUMAN`
- `CLOSEOUT`
- `UPDATE_INSTRUCTIONS_LATER`

Route the decision to the next appropriate skill, recovery action, or human decision.
```
