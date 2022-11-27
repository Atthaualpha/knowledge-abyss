# References

*[:arrow_left: Go back to Git](./GIT.md)*

**What are references?** *The short answer is, references are pointers to commits.*

**Detailed answer**: The easier way to understand what is a references is by using the SHA1 value. Remember that everything in git is addressed by a SHA1 hash value and that this value has a format that is not quite easy to remember.

So if for example you want to know which changes have a specific commit, you must use the commit SHA1 value to refer to that commit. 

Fortunately git allow us to refer to this SHA1 value with a more human readable way. This is by creating a file with a custom name and store in it the SHA1 value that you want to refer. So next time you can remember this name instead of that large value.

- [Where git store references](./REFERENCES.md#where-git-store-references)
- [Heads Refs](./REFERENCES.md#heads-refs)
- [Remotes Refs](./REFERENCES.md#remotes-refs)
- [Tags Refs](./REFERENCES.md#tags-refs)

## Where git store references?

Git stores every reference inside the **.git/refs** directory, there you will find your local refs, remote refs and tags refs too.

## Heads Refs

Inside the **.git/refs** directory you will find that there is a **heads/** directory. This directory contains all branches names with the specific commit pointer.

So you can also figure out that branches are simple references to commits.

## Remotes Refs

There is another directory calls **remotes/**. Remotes refs are "remote branches" or remote pointer for a local branch or ref and this will contain the last commit pointer which that remote ref is pointing to. Remember that if you push a local branch, it will be represented by a remote branch. Git does this for each branch.

## Tags Refs

The last ref type directory is tags, this contains the references to the **tag** object which it also points to a specific commit. 

Types of references:
- [Reflog](./REFLOG.md)
- [Ancestry References](./ANCESTRY_REFERENCES.md)
