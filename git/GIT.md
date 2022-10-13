# Git

*[:arrow_left: Go back to home](../README.md)*

Git needs only local files and resources to operate
Git stores data data as snapshots over time.
Git checksum every change calculating by files or directories content before is stored, this checksum is a SHA-1 hash 

## States of git
git has three main states:
- modified (working directories)
- staged (staging area/index)
- committed (git directory)

### modified
This state means that some changes have been made but has not been committed yet to local database.

### staged
This state means that the changes has been marked to go to the next commit.

### committed
This state means that the changes have been committed to local database.


## Config files location
- System config is stored where git has been installed, generally in the path */etc/gitconfig*
- Global config file store in the user's home directory, generally with name *.gitconfig*
- Local config file store inside git repository

> Each level overrides values in the previous level

This command shows the settings and config files `git config --list --show-origin`


## Commands:

- [Restore](./RESTORE.md)
- [Alias](./ALIAS.md)