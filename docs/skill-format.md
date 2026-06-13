# Skill Format

Each skill should be a small workflow contract.

## Required files

```text
skills/<skill-name>/
  SKILL.md
  prompt.md
  checklist.md
```

## Recommended files

```text
skills/<skill-name>/examples/good-output.md
skills/<skill-name>/examples/weak-output.md
```

## SKILL.md template

```md
# Skill: <Name>

## Purpose

## Failure modes this skill addresses

## When to use

## Inputs / evidence required

## Agent must do

## Agent must not do

## Output format

## Human review checklist

## Common failure modes
```

## Prompt design rules

Prompts should be:

- direct
- bounded
- evidence-seeking
- explicit about forbidden actions
- clear about output format
- reusable across coding agents

Prompts should not:

- ask the agent to “be careful” without saying how
- combine too many unrelated workflows
- allow broad mutation by default
- let the agent mark work complete without validation evidence
