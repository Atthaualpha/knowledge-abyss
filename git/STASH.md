# Stashing

*[:arrow_left: Go back to Git](./GIT.md)*


Stashing is a useful tool to save your half work in a state where you can pick it up later and keep working.

To stash your work you can use the following command:

> `git stash`

This will take the changes that git can keep track and move them to a new space. 

**To add a specific message** to your stash you can add `-m` to the command:

> `git stash -m "my awesome unfinished work"`

`Remember that this will only take the changes that git can keep track, untracked files won't be stashed.

## Stash untracked files.

To also stash untracked files you can add `-u` option to previous command:

> `git stash -u`


## Apply stash changes.

In order to apply your changes to your HEAD you can use:

> `git stash apply`

This will move your stashed changes to your working tree this means that if some changes were at index will be moved to the working tree.

### Apply and move them to index.

In the case that you had changes at index state you would like to keep the changes in this state. To do so you can add `--index` and git will try to move those changes to index.

> `git stash apply --index`

## Stash but keep the changes.

Sometimes you want to stash changes but keep the changes in the index state.
To do so you can stash changes but leave intact the ones staged.

> `git stash --keep-index`

## Drop stash

To delete a stash you can just call `git stash drop stash@{n}` or `git stash drop` the last one will chose the latest stash you have.

## Apply and drop stash

To apply a stash and also delete it you can just call `git stash pop stash@{n}` or `git stash pop`  the last one will chose the latest stash you have.

## Clear stash

To delete all stash you can just call `git stash clear`

## Create a branch from a stash

Sometimes you would need to create a branch from some stashed changes you can use:

> `git stash branch <branch-name> <stash>`

The <stash> is optional if not specified will use the latest stash you have.

## Stash internals

When creating a stash git create some new objects to keep track of what has been changed. The follow references are stored inside a commit object.

1. A commit for changes in the working tree
2. A commit for changes in the index area
3. A commit for un-tracked changes (Only when stashing un-tracked files)


Somethings to keep in mind are:
- A stash could have 3 parents at most.

- Stashes are stored in the reflog history inside the `.git/logs/refs/stash` file. That's because the notation of `stash{0}`

- Git keep track of the latest stash created inside the `.git/refs/stash` file, here will be just the pointer the commit created for that stash. This can be output with the command `git rev-parse stash` to show the commit hash or `git cat-file -p stash` to show the content of that commit.

## Un-applying a stash

If in some case you need to un-applying a stash you can use the following command

> `git stash show -p | git apply -R -`

- The *-p* option output the changes in a patch format.
- The command apply with *-R* option apply a patch in reverse.