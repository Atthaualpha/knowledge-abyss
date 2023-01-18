# Cherry

*[:arrow_left: Go back to Git](./GIT.md)*


Cherry command is different from cherry-pick, this command just output differences between branches.

Using this command you can list which commits have been merged or not into an specific branch.

## Listing commits 

To list if a commit is already merged into a branch use:

> `git cherry -v <upstream> <head>`

Where *upstream* is the branch you want to check if has the commits and *head* is the working branch.

The option `-v` means `--verbose` to list also the commit messages.

This will also display every commit with a `-` or `+` symbol. The  `-` means that the commit has been merged and `+` means that the commit is still pending to be merged.