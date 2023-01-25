# Worktree

*[:arrow_left: Go back to Git](./GIT.md)*

In git normally you use just one working directory but git allow us to use multiple.

This is by creating a clone of your repository but most of the git refs will be in the main repository and will be shared between all working trees, this way all changes made on any working tree will be visible to all.

This is a useful feature that allows you to working in another area without bothering to squash, commit or reset your current changes.

Notes:
- When working with multiple working trees you will have to open new IDEs editors
- You can only checkout a single branch or commit at a time across the working trees.
- Use working tree in situations like, a important bug fix, or experimental tests, it is a bad practice to have multiple working trees.

## Adding a working tree

To add a new working tree use the command

> `git worktree add <path>`

The path variable will be the location where your repository will be clone, and it is **recommended to choose a location outside of main repository**. 

> `git worktree add ../new-worktree`

This way git will create a folder outside of the main repository called `new-worktree` and will create a branch with the same name.

## Adding a working tree with custom name

If you want to add a worktree but with a branch name different from the worktree directory use the `-b` option

> `git worktree add -b <branch> <path>`

## Listing working trees

To list which worktrees you have use the command

> `git worktree list`

This will show
- The path to the working tree directory
- The commit that you is checked out
- The branch that is checked out

## Removing working trees

To remove a working tree use:

> `git worktree remove <path>`

Keep in mind that this will only remove the working tree directory but not the branch this have to be deleted manually. If you have uncleaned working trees add the `--force` option.