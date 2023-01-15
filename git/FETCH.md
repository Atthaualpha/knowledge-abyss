# Fetch

Fetch is a command that allow us to update our local references with remote changes. This is because when working with a team you may need to keep track of what changes are introduced by the team.

Fetch basically check which commits are missing in the local repository and download them from the remote server. This way every branch will now point to the latest commit with all new changes.

The URL that git uses to fetch the changes is in the **config** file inside the **.git** directory. Git uses the default remote repository that is **origin** if you have another remote configured and want to use it you need to specify it.

> Something important to keep in mind is that fetch just downloads data and does not merge the changes into your local branches. This have to be done manually (i.e. `git merge origin/master`) or with the **git pull** command

To use fetch use the following command

> `git fetch <remote>`

This will update branch and tag with the remote changes.

## Fetch a single branch using refspec

Sometimes you don't want to download all the data for all your local repositories but just a specific one. This can be done by using the refspec of the branch.

> `git fetch <remote> <src>:<dst>`

For example `git fetch origin master:master` or the shorthand `git fetch origin master:`

Remember that you can omit the refspec path like `refs/head/master` and just use the branch name.

## Fetching tags

By default git fetches tags that points to a commit that is in the history fetched. This behavior can be changes by fetching all tags from the remote or by not fetching any tag.

### Fetching any tag

Add the `--tags` or `-t` option to the `git fetch` command to update every tag.

### Avoid fetching tags

You may want to disable the option to fetch tags, in this case add the `--no-tags` or `-n` option to the `git fetch` command.

## Fetch and prune references

Pruning unreachable references is a good idea to combine with the fetch command, because you ensure that keep not only the references up to date but also the ones that no longer exist.

Use:

> `git fetch --prune <remote>`

Remember that this command will first prune and then fetch the remote references.

### Prune tags

Tags are objects that can be deleted from the remote repository, thus you may also want to prune those tags that no longer exist on the remote.

Add the `--prune-tags` option to the git fetch command

> `git fetch --prune --prune-tags <remote>`


