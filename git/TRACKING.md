# Tracking

*[:arrow_left: Go back to Git](./GIT.md)*


Tracking in git is like a shortcut to update you local and remote branches without the need to manually specify the branch you want to update.

Basically git allow us to connect a local branch to a remote one.

## Create a branch tracking a remote branch

Normally when you create a branch into your local, this won't have the tracking information. To create a branch and keep track of the changes that may happen to the branch from where you are creating it just added `--track` option.

> `git branch --track origin/feature`

This way you will create a branch with the same name as the remote one.

If you want to give it a different name just specify before the remote branch.

> `git branch --track local-feature origin/feature`

Something interesting is that if you omit the remote branch name you will track the local branch instead of the remote branch.

> `git branch --track local-feature`

## Add tracking to an existing branch

If you have a branch without tracking a remote one, you can update the branch information with the command

> `git branch -u <branch-to-track>`

Keep in mind that there is no need that the branch to track to be a remote one, it can be a local branch to.

You can also add the tracking information using the checkout command, please refer to [Tracking](./CHECKOUT.md#tracking)  in checkout section.

## Remove tracking information

You can also remove the tracking information for a specific branch using

> `git branch --unset-upstream <branch>`

## Pull changes from a tracking remote branch

Here is one of the usages of tracking, because you just need to use `git pull` to update your branch, without the tracking information you will need to specify the remote branch from where you are downloading the changes.

## Pushing changes to a tracking remote branch

The other usages is to push changes, instead of specifying the remote branch just use `git push` command.

### Pushing changes with a different tracking branch name

When the tracking branch is different from the local branch git will ask you to specify where you want to push the changes.

If you want to push changes to your remote branch just use `git push origin HEAD` command this will use the branch you HEAD is pointing to.

But if you want to push changes to your tracking branch you need to specify it

> `git push origin HEAD:<branch-name>`

## Where tracking information is stored?

To see how git manage the relation between a branch and its tracking branch, check your local config file, that is inside `.git` directory, there git store all branches with the branch that is tracking in the *merge* property.