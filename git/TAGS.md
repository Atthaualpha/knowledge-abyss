# Tags

*[:arrow_left: Go back to Git](./GIT.md)*


Tags are pointers to a specific commits that help us to bookmark our development to an specific time, this way is much easier to know what was introduced in a specific version. Basically tags allow us to create versions.

## Creating

Before creating a tag is important to know that there are two main types of tags. 

- Lightweight 

- Annotated

Is preferred to use the annotated tag because it provides us with much more information about when it was created, the intention of the tag and more details.

All tag objects are stored in `refs/tags` directory. Does not matter which type of tag you create.

### Lightweight tags

This type of tag is just a pointer to a specific commit, just like a branch. To create a lightweight tag just need to specify the tag name.

> `git tag v1 <tag_name> <commit>`

*The commit option is optional, provide it if you want to create a tag from a commit different from which your HEAD is pointing to.*

### Annotated tags

This type of tag behaves similarly to a commit, because contains information such as, message, creation date, the person who created the tag and also a reference to the commit.

Annotated tags differs from lightweight tags in that they also have a object that contains all this metadata. Lightweight tags just has a reference to the commit.

To create a annotated tag you need to use the `-a` option or provide a message with `-m` option.

> `git tag -m "message" <tag_name> <commit>`

*The commit option is optional, provide it if you want to create a tag from a commit different from which your HEAD is pointing to.*

## Listing

To list tags just need to use the `git tag` command but you can also provide a prefix to search for i.e `git tag --list v-*`.

You can also provide the `--merge` option to list the tags that can be reached for an specific commit. i.e `git tag --merge <commit>`

### Listing remote tags

To list tags that are in the remote repository you can use the `git ls-remote --tags` command.

### List only annotated tags

To list just annotated tags use 

> `git describe`

This command can also search a specific tag adding it after the command. 

## List only lightweight tags

To list only lightweight tags use

> `git describe --tags`

## Pushing tags to the remote

To push tags you need to use the `push` command. There are some ways to do this.

### Pushing specific tags

You can push just the tags that you want specifying it with `git push <tag_name>` such a normal branch.

### Pushing all tags

If you want to push all tags just add the `--tags` option to the `git push` command. i.e `git push --tags`

Keep in mind that this will push all tags but if you want to push just your annotated tags use `--follow-tags` option instead. i.e `git push --follow-tags`

## Update tag pointer

In some cases you want to change where the tag is pointing to and use another commit reference, to update the tag pointer use the `git tag -f <commit>` command.

It is recommended to use it just in tags that are not in the remote yet, but if it is already in the remote you can also update it with the `git push --tags --force` command.

## Deleting

To delete a tag keep in mind that if the tag is already in the remote you must delete it from there to

To delete a tag locally use the `-d` option. i.e. `git tag -d <tag_name>`

To delete a tag from the remote use the `git push <remote> --delete <tag_name` command.

**In this case the remote name is mandatory.**