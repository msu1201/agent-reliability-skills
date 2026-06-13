# Installation

Agent Reliability Skills can be used in two modes:

1. **Manual mode** — a human copies a skill prompt into an agent session.
2. **Autonomous mode** — the skills pack is vendored into a project and referenced from the project's agent instructions so the agent can trigger skills based on task phase and failure signals.

Manual mode is useful for trying one skill. Autonomous mode is the intended workflow for real engineering projects.

## Recommended project layout

Install the pack under a project-local agent directory in your target repository:

```text
.agent/agent-reliability-skills/
```

Then add a router block to the target repository's agent instructions, usually `AGENTS.md`.

```text
<your-project>/
  AGENTS.md
  .agent/
    agent-reliability-skills/
      README.md
      docs/
      skills/
      templates/
```

## Option A: Vendor the full pack

Use this when you want a stable, project-local copy.

```bash
git clone <this-repo-url> .agent/agent-reliability-skills
```

Then copy the router template into your `AGENTS.md`:

```text
templates/AGENTS_RELIABILITY_PACK.md
```

## Option B: Use a git submodule

Use this when you want to keep the pack up to date from upstream.

```bash
git submodule add <this-repo-url> .agent/agent-reliability-skills
```

Then commit the submodule reference and update your `AGENTS.md`.

## Option C: Copy selected skills only

Use this when you want a small install.

Recommended minimum set:

```text
skills/scope-control/
skills/before-you-code-recon/
skills/test-verification-report/
skills/dirty-tree-audit/
skills/evidence-based-closeout/
skills/session-retrospective/
```

Then adapt the router template so it only references installed skills.

## Manual use

For one-off use, copy a skill prompt into your coding-agent session:

```text
Use .agent/agent-reliability-skills/skills/session-retrospective/prompt.md.
Do not modify files. Produce only the retrospective.
```

Manual use is simple, but it relies on the human to notice when a skill is needed.

## Autonomous use

For autonomous use, add the Skill Router to your project instructions.

The router tells the agent:

- which skill to trigger before implementation
- which skill to trigger before risky changes
- which skill to trigger before validation claims
- which skill to trigger before handoff
- which skill to trigger after confusion, drift, or repeated failure
- what recovery decision the skill must output

Autonomous use works best when skills are treated as workflow gates, not optional prompts.

## Minimal AGENTS.md integration

Add this to your target repository's `AGENTS.md`:

```md
## Agent Reliability Skills

This repository uses the Agent Reliability Skills Pack installed at `.agent/agent-reliability-skills/`.

When a trigger condition matches, read the relevant `SKILL.md` and follow the corresponding `prompt.md` behavior.

Use `docs/skill-routing.md` and `templates/AGENTS_RELIABILITY_PACK.md` from the pack as the routing contract.
```

For the full router, copy `templates/AGENTS_RELIABILITY_PACK.md`.

## Important limitation

This pack gives agents explicit workflow rules, but it cannot force every agent runtime to obey them. The quality depends on:

- whether your agent reads `AGENTS.md` or equivalent project instructions
- whether the skills pack is available in the repo
- whether your task prompt allows autonomous routing
- whether high-risk actions still require human approval in your environment

For critical projects, keep human review and CI gates in place.
