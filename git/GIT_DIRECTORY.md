# Git Directory

*[:arrow_left: Go back to Git](./GIT.md)*


Git as a database to keep track of changes also have some structure to achieve its purpose.


The .git directory has the following structure and [here](https://git-scm.com/docs/gitrepository-layout) you can find the meaning of each element of its structure

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
