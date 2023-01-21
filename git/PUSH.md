# Push

*[:arrow_left: Go back to Git](./GIT.md)*

Push is a command that allow us to public or upload our local changes to a remote repository.

# Pushing changes

To push your local changes use the following command:

> `git push <remote> <branch>`

This is the basic command, this will make some actions on the remote repository

1. Create a remote branch with the name that you specify
2. Upload the local changes
3. Move the remote branch to the latest commit uploaded.

## Pushing changes without specifying local branch

There is a shortcut to not write the local branch

> `git push <remote> HEAD`

Due to HEAD points to a branch reference this will replace the branch name.

## Pushing changes with tracking 

When your local branch has a tracking references, it is mucho more simple to push changes

> `git push`

We omit the remote name and the branch name, because now git uses the [tracking](./TRACKING.md) branch as reference.

## Force pushing changes or rewrite remote history

Force changes implies that you rewritten the local branch history and you want to rewrite the remote branch history too.
This means to get rid of commits and replace them with new commits.

To force changes use the `--force` or `-f` option:

> `git push --force`

Keep in mind that you may lost changes in it is recommended to

1. Use in branch that no one is working on
2. Fetch and merge remote changes into the local branch before force changes, because this way you ensure that remote changes won't be lost.

## Delete a remote branch

To delete a remote branch you need to specify the `--delete` or `-d` option to the push command

> `git push --delete <remote> <branch>`

Here the remote and branch parameters are required.

## Internals

Push command internally implies some steps:

1. Create a remote branch if remote branch does not exist.
2. Upload commit and changes to the remote branch.
3. Move the remote branch to the latest commit

The last step is a [fast-forward merge](./MERGE.md#fast-forward), even though it is described as a merge, a fast-forward does not perform a merge. Just move the pointer to a new commit
