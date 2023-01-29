# Show

[:arrow_left: Go back to Git](./GIT.md)


Show command shows content for different types of objects.

## Diff of commits

By default git show use the current commit to show the diff between its ancestor.

> `git show` or `git show HEAD`

## Diff for merge commits

When a commit is created from a merge this commit will at least have two parents, git show command by default this will show no differences but only if there were no merge conflicts.

Keep this in mind, if there were any conflicts, show command will show of diff generate from that conflict resolution.

### Diff for first parent

You can see the changes of first parent of the merge commit using

> `git show --first-parent`

### Diff splitting parents

If you want to see the diff but for every parent line use `-m` option:

> `git show -m`

## Diff combined parents

If you want to see the changes from all parents combined in a single output use `-c` option:

> `git show -c`