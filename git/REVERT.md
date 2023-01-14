# Revert

Revert is a command that allows you to undo changes made in previous commits but keep track of which commits that introduced the changes. This means that revert will take the changes and create a new commit with reversal changes applied.

Use the following command

> `git revert <commit>` or `git revert <branch>`

## Revert merge commits

When you face with a commit that comes from a merge things are different when the commits has multiple parents. In this case you need to specify which parent you want to preserve by doing this you will drop the changes from the other parent.

> `git revert -m <parent-number> <commit>`

The *m* flag means the main line what you want to keep, usually is the first main line with index 1 **(parent lines starting from 1)**

If you want to know how to check the parents of a commit please refer to [ancestry references](./ANCESTRY_REFERENCES.md#view-parents-references-with-rev-list)