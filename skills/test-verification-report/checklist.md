# Test Verification Report Checklist

Use this checklist before accepting an agent's validation claim.

## Evidence

- [ ] Exact commands are listed.
- [ ] Results are listed for each command.
- [ ] The report says whether commands ran before or after the latest change.
- [ ] Interrupted commands are not counted as passing.
- [ ] Skipped commands are visible.

## Status language

- [ ] The agent does not say “passing” unless validation completed after the latest change.
- [ ] The agent does not use “should pass” as evidence.
- [ ] The agent separates confidence from proof.

## Coverage

- [ ] Focused tests are distinguished from full test suites.
- [ ] Build/lint/typecheck coverage is stated if relevant.
- [ ] CI status is included only if checked.
- [ ] Remaining validation gaps are explicit.
