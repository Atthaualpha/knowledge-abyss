# Remote 

*[:arrow_left: Go back to Git](./GIT.md)*

Remote command allow us to manage the remote repositories and remote branches.

The usage of remote command is to create a link between our local repository and the remote repository in order the make the changes available in the prefer hosting provider (GitHub,GitLab, Bitbucket, etc).

- [Link a remote repository](./REMOTE.md#link-a-remote-repository)
- [Update remote references](./REMOTE.md#update-remote-references)
- [Prune stale remote references](./REMOTE#prune-stale-remote-references)

## Link a remote repository

To add or link a remote repository to your local just use the following command:

> `git remote add <name> <url>`

This link will be added to your local config file.

## Update remote references

In order to keep your remote references up to date, you can update them using

> `git remote update [name]`

*The name is optional, by default use the default remote reference.*

This operation can be done by `git fetch` please refer to [Fetch](./FETCH.md)

## Prune stale remote references

Sometimes when a remote branch is deleted and you want to get rid of the remote references in your local, you can use the `git remote update` command to do it.

> `git remote update --prune [name]`

This operation can be done by `git fetch` please refer to [Fetch](./FETCH.md#fetch-and-prune-references)

*The name is optional.*