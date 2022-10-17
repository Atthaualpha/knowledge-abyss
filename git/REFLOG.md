# Reflog

*[:arrow_left: Go back to Git](./GIT.md)*

Reference logs, or "reflogs", record when the tips of branches and other references were updated in the local repository.

This means that as you’re working, Git silently records what your HEAD is every time you change it. `Each time you commit or change branches, the reflog is updated`

## Show reflog history

To see the reflog history you can use the following command.

> `git reflog` 

This will use your HEAD pointer to show updates to HEAD.

Yo can also specify a specific branch just like `git reflog <branch>`

A useful way to use reflog is to see the state in a specific time using the following command:

> `git show HEAD@{1}`

This command uses `show` to display what changes and use the references of the branch or pointer in this case HEAD and is looking for the changes that was moved `1 ago`

So this is useful if is combined with `checkout`, `show` and `reset` commands.