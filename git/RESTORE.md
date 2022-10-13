# Restore 

This command is useful when you want to discard changes from states.

*[:arrow_left: Go back to Git](./GIT.md)*

### Restore from Stage or index changes.

run following command to restore changes from stage to working tree.

`git restore -S <path>`

Where **S** means staged state.

Example:
> git restore -S .

### Discard changes from working tree

run following command to discard changes working tree.

`git restore <path>` or `git restore -W <path>`

Where **W** means working tree state.

Example:
> git restore -W .

### Special behaviour for new files.

Theres is a special usage when you have new files in index state. If you want to discard this changes and even delete the file you can run following command.

`git restore -SW <path>`


