# Log 

*[:arrow_left: Go back to Git](./GIT.md)*

Log is a command that allow us to see our repository history and also show commits history for specific branches.

## Basic Usage

To use log in git use the command

> `git log`

This will print the commits history of your current branch.

## Logging with graph structure

You can also see the commit history in a graph structure where you can se the ramifications of every branch

> `git log --graph`

## Logging all branches history

When you use log command this will only print the commit history of your current branch and the branches that ca be reached. To show all branches use  `--all` option

> `git log --all`

## Logging commits for specific branches

You can also just select the commit history for a specific branches

> `git log <branch> <branch> ..`

## Logging only the files that changed

Log has lots of options to configure what will be displayed, but one useful option is see just the files that changed with the `--stat` option

> `git log --stat` 

## Show commit history for specific file

You can also search for the commits that made changes to a specific file.

> `git log -- <path>`

You specify the file path after the *--*, you can also use a matching path instead of writing whole path with * asterisk

> `git log -- *matching*`

## Formatting log output

You can customize the output for log command, please see the log documentation.