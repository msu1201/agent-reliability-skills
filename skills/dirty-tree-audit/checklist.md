# Dirty Tree Audit Checklist

Use this checklist before committing, cleaning, reverting, or handing off a dirty repo.

## Git state

- [ ] Branch is reported.
- [ ] Ahead/behind status is reported if available.
- [ ] Tracked modified files are listed.
- [ ] Untracked files/directories are listed.

## Classification

- [ ] Each tracked file is classified.
- [ ] Each untracked file/directory is classified.
- [ ] Generated output is separated from source changes.
- [ ] Scratch files are separated from project artifacts.
- [ ] Unknown items are not treated as safe.

## Safety

- [ ] Destructive cleanup requires approval.
- [ ] Reverts require approval unless explicitly authorized.
- [ ] Unrelated changes are not committed.
- [ ] Recommended next step is explicit.
