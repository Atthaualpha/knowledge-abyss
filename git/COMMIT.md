# Commit

*[:arrow_left: Go back to Git](./GIT.md)*

A commit can be interpreted as a snapshot of the project in a specific point in time. This means that you record some changes in save them in the repository "permanently" (Of course you can remove commits).

## Creating a commit

To create a commit it is necessary to have changes staged in the index area. When the changes are staged use the command

> `git commit`

This will prompt and editor to add a message, this message can be also set using the `-m` option i.e. `git commit -m "message"`

## Stage changes using commit

Commit command also accepts an option to stage changes in a row.
Add the `-a` option to the commit command.

> `git commit -a -m "message"`

Keep in mind this will only stage changes for tracking files, un-tracking files have to be staged using `git add` command.

## Amend a commit

Amend commit allows you to change the latest commit changes or even the message.

> `git commit --amend`

Refers to [Amend section](./AMEND.md) for more details.

## Avoid hooks

If you have hooks configured such as pre-commit hook, you can skip these hooks by adding `--no-verify` or `-v` option

> `git commit -v`

## Fixup a commit

In some cases you may want to make some changes in a previous commit like changes some file or even just changes the commit message. To do so you can use the fixup option along with rebase.

Follow next steps:

1. Make the changes and move to the stage/index area
2. Commit the changes with `--fixup` option with the commit that you want to change i.e `git commit --fixup=<commit>`
3. This will create a new commit in the tip of your branch but with a prefix `!fixup`
4. Use the rebase command but wih the `--autosquash` option and with the commit ancestor i.e `git rebase --autosquash <commit>~`

With this the rebase and autosquash will rewrite the branch history automatically.

You can also changes the commit message using

> `git commit --fixup=reword:<commit>` 

To change just the message or

> `git commit --fixup=amend:<commit>` 

To changes the contents and the message

**Keep in mind that you must not change the commit message that is prefixed with fixup! or amend!, if you modify it when you run the autosquash rebase git will not know which commit you refers to**

### Useful resources
-   [Conventional commits](https://www.conventionalcommits.org/en/v1.0.0/)
-   [Gitmoji emojis to use](https://gitmoji.dev)