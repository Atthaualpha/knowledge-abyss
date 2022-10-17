# Checkout

*[:arrow_left: Go back to Git](./GIT.md)*

This command is used to switch HEAD pointer between branches and alse to restore changes. But primarily to switch the pointer.

## Checkout to a existing branch 

To switch to a already created branch, you can use the following command.

> `git checkout my-branch`

## Checkout to a not created branch

When the branch has not been created yet, you can create it and also switch to it.

> `git checkout -b my-new-branch`

The `-b` flag tells git to create a new branch.

## Checkout to previous branch

When you want to switch to a previous branch, you can use the following command.

> `git checkout -`

The `-` flag tells git use the previous visited branch.

## Tracking

Git uses a references to validate if your branch is up to date wih the latest changes.
So when creating a new branch you can specify which references you want to use to track changes.

### Set tracking to local branch

You can set the tracking to local branch by passing just the branch name.

> `git checkout -b my-branch -t master`

Here the `-t` or `--track` tells git to set tracking to the master branch.
`Remember` that the tracking branch most already exists.

### Set tracking to current branch

An option to keep track of changes using the branch where you are pointing to before creating the new branch is just ignore the tracking branch name and use just the `-t` or `--track`	flag

> `git checkout -b my-branch -t`

### Set tracking to remote branches

The most common way to set tracking is to remote references, because those are the ones who are updated when you work with a team.

The most used way is to set the tracking to your new branch.

First checkout and create your branch using the previous command

> `git checkout -b my-new-branch`

Then you can create a remote references and add the tracking references to your new branch using the following command.

> `git push -u origin my-branch`

This will first create a references with the name `origin/my-branch` to your remote server and then add the tracking references to `my-branch`

### Set tracking to existing remote branches

There are some cases where you might want to set the tracking to an existing remote branch, for example you want to keep up to date with the branch you are pointing before creating the new one. 

So you can set the tracking with just the following commands.

> `git checkout -b my-new-branch -t origin/master`

or 

> `git checkout -b my-new-branch origin/master`

Here you specify the remote branch you want to track.

Another way is set the tracking strategy when you now that the current branch is pointing to a remote branch too.

If you are pointing to `master` and master has a tracking to `origin/master` you can inherit this tracking reference.

> `git checkout -b my-new-branch -t=inherit`

Here you tells git to use `inherit` way to set the tracking reference. The default mode is `direct` where you use the local branch references.

Another way is use the shorthand `@{u}` to set the tracking reference of existing track reference.

> `git checkout -b my-new-branch -t @{u}`

Where `u` means upstream

