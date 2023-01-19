# Amend

*[:arrow_left: Go back to Git](./GIT.md)*


Amend is not a command itself but an option of commit command. This command allows you to modify the latest commit of you current branch.

Amend a commit implies that a new commit will be created because the metadata changes, so keep in mind that the latest commit will be replaced be this new commit.

So we can make some kind of changes

## Amend commit message:

With amend it is possible to modify the commit message using

> `git commit --amend`

This will prompt an editor or you can even write the message in the command itself with the `-m` option.

> `git commit --amend -m "message"`

## Amend commit but keep same message

If you just want to make some changes but keep the message just added the `--no-edit` option

> `git commit --amend --no-edit`

## Amend commit in remote repository

It is recommended not to use amend with commit that have been already pushed to the remote repository and even more when the branch is shared between the team.

But this can be done by using the same amend commit but use a forced push

> `git push --force`

This will force the commit to modify the branch history and remove the latest one.

It is important to know that if you pull changes from the remote repository before pushing the amended commit the remote changes will be merged into the local branch, and the branch history will have the latest commit the amended commit and the merge commit.
