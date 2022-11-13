# Blame

*[:arrow_left: Go back to Git](./GIT.md)*

Blame command is useful to know what was the last commit that change a specific line and also to check who made the change and the date.

To use blame just need to use the following command and specify the file that you want to blame.

> `git blame [file] `

You can also specify the lines of file that you want to blame with `-L` flag.

> `git blame [file] -L 10,20`