# HEAD

*[:arrow_left: Go back to Git](./GIT.md)*


HEAD is a pointer to the current branch you are working on

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