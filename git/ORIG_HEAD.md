# ORIG_HEAD

*[:arrow_left: Go back to Git](./GIT.md)*

ORIG_HEAD is a references that store an specific commit for drastic changes in order to allow you to rollback changes.

The commit recorded in ORIG_HEAD is the previous one before some operations like:
- Merge
- Reset
- Rebase
- Cherry Pick (With conflicts)
- Pull (When implies a merge or rebase)

This reference is stored in `.git/ORIG_HEAD` file in your repository.

ORIG_HEAD is useful as a shorthand to rollback to a specific commit, but you can also use the [reflog](./REFLOG.md) to achieve the same behavior.