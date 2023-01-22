# HEAD

*[:arrow_left: Go back to Git](./GIT.md)*


HEAD is a pointer that point generally to a specific branch. This means that HEAD allow you to know which branch you are working on.

When HEAD points to a branch means that HEAD points to the tip or the latest or recent commit on a branch.

In some cases HEAD can point to a specific commit or tag and in git this is known as detached HEAD or a [detached state](./DETACH.md).

The real value of HEAD can be seen in the `.git/HEAD` location.

## Remote HEAD

Remote HEAD or default branch is a pointer but in the remote repository, this pointer is useful in some situations:

1. When cloning a repository, the branch that is used is the default branch. By default is master branch.
2. This pointer show us the latest status of remote repository, this means that the HEAD branch and the HEAD remote branch can have differences.

The default branch is stored in the following file of your local repository

> `.git/refs/remotes/<remote>/HEAD`

## Setting default branch

If you want to set the default branch to another different of master branch use the following command:

> `git remote set-head <remote> <branch>`

Keep in mind that the new remote branch must exists.