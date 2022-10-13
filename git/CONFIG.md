# Configuration 

Configurations allow us to set options for repository o global usage

*[:arrow_left: Go back to Git](./GIT.md)*


## Config files location
- System config is stored where git has been installed, generally in the path */etc/gitconfig*
- Global config file store in the user's home directory, generally with name *.gitconfig*
- Local config file store inside git repository

> Each level overrides values in the previous level

This command shows the settings and config files `git config --list --show-origin`