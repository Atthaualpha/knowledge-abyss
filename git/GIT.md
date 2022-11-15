# Git

*[:arrow_left: Go back to home](../README.md)*

Git is a distributed version control system, no more than that.

Git needs only local files and resources to operate
Git stores data data as snapshots over time.
Git checksum every change calculating by files or directories content before is stored, this checksum is a SHA-1 hash 

## States of git
git has three main states:
- modified (working directories)
- staged (staging area/index)
- committed (git directory)

### modified
This state means that some changes have been made but has not been committed yet to local database.

### staged
This state means that the changes has been marked to go to the next commit.

### committed
This state means that the changes have been committed to local database.

## Commands:

- [Alias](./ALIAS.md)
- [Bisect](./BISECT.md)
- [Blame](./BLAME.md)
- [Checkout](./CHECKOUT.md)
- [Clean](./CLEAN.md)
- [Commit](./COMMIT.md)
- [Commit Ranges](./COMMIT_RANGES.md)
- [Config](./CONFIG.md)
- [Customization](./CUSTOMIZATION.md)
- [Merge](./MERGE.md)
- [References](./REFERENCES.md)
- [Rerere](RERERE.md)
- [Restore](./RESTORE.md)
- [Search](./SEARCH.md)
- [Stash](./STASH.md)

## Pending topics
- Rebase
- git flow
- lib flow
- refspecs
- revert
- what is version control
