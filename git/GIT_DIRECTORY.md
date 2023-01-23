# Git Directory

*[:arrow_left: Go back to Git](./GIT.md)*


Have you ever wonder what is inside the **.git** directory and what is the meaning of each folder and file? Well here we're going to answer those questions.

The .git directory has the following structure

```
|- hooks/
|- info/
|   |- exclude
|   |- refs
|- logs/ 
|   |- refs/
|   |   |- heads/
|   |   |- remotes/
|   |   |    origin/
|   |   |      |- HEAD
|   |   |      |- [...]
|   |   |- stash
|   |- HEAD
|- objects/
|   |- info/
|   |- pack/
|   |- [...]
|- refs/
|   |- heads/
|   |- remotes/
|   |    origin/
|   |      |- HEAD
|   |      |- [...]
|   |- tags/
|   |- stash
|- COMMIT_EDITMSG
|- config
|- description
|- FETCH_HEAD
|- gitk.cache
|- HEAD
|- index
|- ORIG_HEAD
|- packed-refs
|- TAG_EDITMSG

```

Let's take a look one by one.

## Hooks

See [git layout documentation](./https://git-scm.com/docs/gitrepository-layout)