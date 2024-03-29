# Cherry pick

*[:arrow_left: Go back to Git](./GIT.md)*


Cherry-pick command is a way to select an specific commit and create a copy of it to later apply to another branch. This means that those changes will be added to the branch history as a new commit.

*Keep in mind that the new commit will have a different HASH Id because the commit has different metadata like the parent, the creation date, the message, etc.*

## Using cherry-pick with a single commit

In order to pick a commit and apply it to the current branch just use the command:

> `git cherry-pick <commit>`

## Using cherry-pick with multiple commits

Git also allow us to pick several commits in a single command

> `git cherry-pick <commit> <commit>`

Or with a range notation like:

> `git cherry-pick <commit>^..<commit>`

Keep in mind that each commit will be apply in the order specified and will create a new commit, this means that N commits will be added to the branch history.

When using range commits keep in mind that the first commit will not be included, that is why use the `^` symbol to refer to the parent commit.

## Apply multiple commits into a single commit

Sometimes you want to pick several commits but don't create multiple commits, instead you can group them together into a single commit.

You can tell git to do not create the commit with the option `--no-commit`or `-n`

> `git cherry-pick -n <commit>`

Then the changes will be in the index stage, so you can even changes the commit message and commit all the changes together.

You can even pick specific patches from the staged changes and drop the ones that are not longer needed.

## Apply chucks from commits

Sometimes you may want to pick chunks from a specific commit and apply them to your current branch, to do this you can use checkout to do this.

> `git checkout -p <commit>`

This command will checkout the given commit but with the `-p` option, git will prompt a editor to choose the chucks you want.

#### Chucks of specific files

Using the previous command you can also specify which file you want to use to pick the chucks.

> `git checkout -p <commit> -- <file-path>`

