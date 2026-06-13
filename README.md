# Agent Reliability Skills

**Failure patterns and reusable skills for coding agents.**

Coding agents are powerful, but they fail in predictable ways: they drift in scope, reimplement existing work, skip validation, over-edit unrelated files, and produce handoffs that are hard for humans to review.

This repo turns those failure modes into reusable **skills**: structured prompts, checklists, and workflow contracts that help humans prevent, detect, and recover from common coding-agent failures.

> This is not a prompt collection. It is a reliability layer for coding agents.

## Core idea

Every skill follows the same reliability loop:

```text
Failure mode → Prevention → Detection → Recovery → Review evidence
```

A skill is more than a prompt. A skill defines:

- when to use it
- what evidence the agent must inspect
- what the agent must do
- what the agent must not do
- what output format is required
- what the human should review
- what common failure modes it addresses

## Failure modes this repo addresses

The repo is organized around failure categories first, then skills.

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

## Skill map

Each failure mode should map to one or more reusable skills.

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

## Who this is for

This repo is for people using coding agents such as Codex, Claude Code, Cursor agents, Devin-style agents, or custom agent runners on real engineering work.

It is especially useful if you care about:

- smaller review surfaces
- evidence-based completion reports
- safer mutation boundaries
- less scope creep
- fewer false “done” claims
- better AGENTS.md / project instruction maintenance
- repeatable agent handoff workflows

## Skills by phase

### Before implementation

| Skill | Purpose |
| --- | --- |
| [`before-you-code-recon`](skills/before-you-code-recon/SKILL.md) | Force the agent to inspect repo state, instructions, architecture, and tests before editing. |
| [`no-reimplementation-check`](skills/no-reimplementation-check/SKILL.md) | Prevent agents from rebuilding functionality that already exists. |
| [`scope-control`](skills/scope-control/SKILL.md) | Keep an agent inside a PR-sized task boundary. |
| [`safe-mutation-gate`](skills/safe-mutation-gate/SKILL.md) | Require explicit safety checks before destructive or broad changes. |

### During validation

| Skill | Purpose |
| --- | --- |
| [`test-verification-report`](skills/test-verification-report/SKILL.md) | Prevent vague validation claims by requiring exact commands, results, and missing evidence. |

### Before handoff

| Skill | Purpose |
| --- | --- |
| [`dirty-tree-audit`](skills/dirty-tree-audit/SKILL.md) | Explain tracked and untracked changes before committing, cleaning, or handing off. |
| [`evidence-based-closeout`](skills/evidence-based-closeout/SKILL.md) | Make the agent prove what changed and what was validated. |
| [`pr-handoff-summary`](skills/pr-handoff-summary/SKILL.md) | Produce a reviewer-friendly PR summary with risks, tests, and rollback notes. |
| [`session-retrospective`](skills/session-retrospective/SKILL.md) | Ask the agent to review its own session and propose instruction improvements. |

### After repeated failures

| Skill | Purpose |
| --- | --- |
| [`agents-md-improvement-review`](skills/agents-md-improvement-review/SKILL.md) | Convert repeated agent failures into reviewable AGENTS.md changes. |

## Recommended workflow

Use these skills as small workflow gates rather than one giant instruction block.

```text
1. Start task
   → scope-control
   → before-you-code-recon
   → no-reimplementation-check

2. Before risky edits
   → safe-mutation-gate

3. During validation
   → test-verification-report

4. Before handoff
   → dirty-tree-audit
   → evidence-based-closeout
   → pr-handoff-summary

5. After a meaningful session or repeated failure
   → session-retrospective
   → agents-md-improvement-review
```

## Repository structure

```text
skills/
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

  <skill-name>/
    SKILL.md        # workflow contract
    prompt.md       # copy-paste prompt
    checklist.md    # human/agent review checklist
    examples/       # good and weak outputs

templates/
  AGENTS.md
  TASK_PROMPT.md
  PR_SUMMARY.md
  SESSION_RETRO.md

docs/
  skill-format.md
  failure-taxonomy.md
  philosophy.md
```

## Install as a skills pack

For manual use, copy a skill `prompt.md` into your coding-agent session.

For autonomous use, vendor this repo into your project and copy `templates/AGENTS_RELIABILITY_PACK.md` into your `AGENTS.md`.

Start here:

- `docs/installation.md`
- `docs/skill-routing.md`
- `docs/recovery-flow.md`
- `case-studies/001-allowed-paths-are-planned-touch-areas.md`

## Design principles

1. **Evidence over vibes** — completion claims require commands, diffs, logs, or explicit missing evidence.
2. **Small review surfaces** — agents should avoid broad rewrites unless explicitly requested.
3. **No hidden uncertainty** — agents should state assumptions, missing evidence, and unresolved risks.
4. **Prevention before recovery** — the best failure mode is the one caught before mutation.
5. **Human keeps final authority** — skills propose changes; humans decide whether to merge or update instructions.

## Contributing

Contributions are welcome, especially:

- real coding-agent failure cases
- reusable prevention skills
- detection checklists
- recovery prompts
- before/after examples
- AGENTS.md instruction patterns that improved reliability

Please start with [`CONTRIBUTING.md`](CONTRIBUTING.md).

## License

MIT. See [`LICENSE`](LICENSE).
