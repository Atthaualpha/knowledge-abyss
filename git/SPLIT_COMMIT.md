# Split commits

*[:arrow_left: Go back to Git](./GIT.md)*

In some cases we have a commit with multiple changes and we want to split them into multiple commits.

One way to do this is:

1. Move the committed changes into the working tree with `git reset --mixed <branch>` where the branch is the one that you would merge these changes.
2. Stage and commit chunks of changes into multiple commits.

Another way is with rebase where you mark the commits you want with edit and after that run the command `git reset HEAD~` and stage and commit the changes
