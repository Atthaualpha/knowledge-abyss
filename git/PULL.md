# Pull

*[:arrow_left: Go back to Git](./GIT.md)*


Pull command is the way how git updates local changes with remote ones.

Basically a pull downloads new commits from the remote repository and merge those new commits into the current branch.

*Under the hook gits performs a fetch and after that a merge.*


## Pulling without tracking branch

To perform a pull into a branch that does not have a tracking branch you must specify the remote repository and the branch.

> `git pull <remote> <branch>`

## Pulling with tracking branch

when your local branch has a tracking branch the only thing you need to do is:

> `git pull`

This is because git make a relation between local and remote branches. Refer to [Tracking](./TRACKING.md) section to get more information

## Pulling from a different branch

You can also pull changes from a branch that does not have the same name as the current branch, just need to specify the remote branch.

> `git pull <remote> <branch>`

You can also use refspec instead the branch name

> `git pull <remote> <refspec>`

## Pulling and rebase instead of merge

By default git execute a merge after fetching changes, to override that behavior you can add the `--rebase` option to git pull command

> `git pull --rebase`

## Internals

Internally git execute two actions to pull changes.

1. Git fetch if there are new changes and download those changes updating the remote branch references. Check [fetch command](./FETCH.md).
2. By default git take those changes and merge them into the current branch.

So a git pull is a `git fetch && git merge`

**But how git knows which are the latest changes to must be combined into the local branch?**

Remember that when a fetch is executed, git store the latest commit for the remote branch references inside the FETCH_HEAD file. So git takes that commit and execute the merge. This can be illustrated us `git merge <commit-from-fetch-head>`

