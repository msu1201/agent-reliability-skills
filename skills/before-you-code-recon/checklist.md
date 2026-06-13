# Before You Code Recon Checklist

Use this checklist before allowing the agent to edit files.

## Repo state

- [ ] Agent reported current branch.
- [ ] Agent reported dirty tracked files.
- [ ] Agent reported untracked files.
- [ ] Agent distinguished current work from previous commits.

## Instructions

- [ ] Agent inspected AGENTS.md or equivalent.
- [ ] Agent listed task-relevant rules.
- [ ] Agent identified forbidden or protected paths if present.

## Existing implementation

- [ ] Agent inspected relevant source files.
- [ ] Agent identified existing code paths before proposing new ones.
- [ ] Agent avoided reimplementing already-completed behavior.

## Tests and validation

- [ ] Agent identified relevant tests.
- [ ] Agent named focused validation commands.
- [ ] Agent named full validation commands if appropriate.

## Plan quality

- [ ] Plan is PR-sized.
- [ ] Planned change surface is narrow.
- [ ] Open questions are genuine blockers, not questions answerable by repo inspection.
