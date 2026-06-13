# Safe Mutation Gate Prompt

Before performing risky mutations, stop and produce a safety review.

Risky mutations include:

- deleting files
- moving many files
- mass renaming
- broad formatting
- modifying migrations
- changing lockfiles
- touching generated files
- changing security-sensitive code
- touching secrets or credentials

## Output

# Safe Mutation Gate

## 1. Proposed Mutation

List exact files and operations.

## 2. Risk Level

Low / Medium / High

## 3. Why This Is Needed

Explain why the task cannot be completed safely without this mutation.

## 4. Safer Alternatives

List smaller or more reversible options.

## 5. Rollback Plan

Explain how to undo the change.

## 6. Validation Plan

List commands/checks to run after mutation.

## 7. Approval Needed

State whether human approval is required before proceeding.

## Rules

Do not perform the mutation in this step.
Do not delete or overwrite files without explicit approval.
Do not touch secrets or credentials.
Do not run broad formatters unless the human requested it.
