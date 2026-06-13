# Good output excerpt

## Evidence

- Ran `git status --short`: 6 modified files, no untracked files.
- Ran `pytest tests/file_manager/test_move.py`: passed, 12 tests.
- Did not run full test suite because it takes 25 minutes and was outside the requested slice.

## Candidate AGENTS.md improvement

### Proposal A: Require pre-implementation repo recon

**Priority:** Must-have

**Problem observed this session:** I initially started adding a new move helper before discovering `FileActionService.move_now` already existed.

**Recommended AGENTS.md text:**

```md
Before adding new functionality, inspect existing services and tests for equivalent behavior. Summarize what already exists before writing code.
```
