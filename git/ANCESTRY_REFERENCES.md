# Ancestry references

*[:arrow_left: Go back to References](./REFERENCES.md)*

Remember that every commit has its children and parents and you can keep track of those references.

## Show commit parent:

In order to show the commit parent you can use the `^` (caret) character, which tells git to seek the given commit parent.

> `git show <commit-id>^` or  `git show <branch>^`

This can also be used gt `log` command an is useful to use the `--graph` option to see the graph in a human-readable format.   

## Identifying the parent of a commit

The `^` character can also be used to specify an special parent for a commit.

> `git show HEAD^2` 

This tells git to seek the second parent of a commit.

## Using ~ tilde character.

There is another way to specify the parent of a commit and is using the `~` character.

This character has a similar behavior to the `^` character.

> `git show HEAD~` 

This is equivalent to `git show HEAD^`

The differences comes when a number is specified, because it will seek the `first parent of the first parent` or the `grandparent`

> `git show HEAD~2`

This two characters can be combined for example:

> `git show HEAD~^2` or `git show HEAD~3^2`

## View parents references

You can also see the parent of an specific commit or branch using the following command:

> `git rev-list <commit> --parents --abbrev-commit -n 6 --graph --all`



