# RESET

*[:arrow_left: Go back to Git](./GIT.md)*


Reset command allow as to update changes from the three trees that git manage.

This basically means that we can move changes from one state to another. Moving the pointer and the current branch to an specific state

### --soft 
Soft flag allow as to move changes in the most safety, this means that we won't lose any changes.

The following command will move changes from HEAD to the index, this means that any changes that are in HEAD state will be moved to index and will be pending to be committed.

> `git reset --soft [branch or commit]`

### --mixed
This is default behavior, and will tells git to move the changes from HEAD to the working tree, this means that will be pending to be staged and committed.

> `git reset --mixed [branch or commit]`

or

> `git reset [branch or commit]`

### --hard
This is the most dangerous option, because will not only to remove changes from HEAD and index, but also from the working tree, this means that any changes will dropped.

> `git reset --hard [branch or commit]`

## Reset with a path
There is also a useful command to just reset and specific file and that is achieved by adding the file path that you want to reset.

> `git reset [file_path]
