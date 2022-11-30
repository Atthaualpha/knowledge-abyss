# Detach

[:arrow_left: Go back to Git](./GIT.md)

Normally when we checkout to the tip of a specific branch, but sometimes we want to checkout a specific commit or a reference that is not the tip of a branch.

In this case git call this state as detached state or an anonymous branch, and this means that the HEAD pointer will have the reference to that specific commit.

Keep in mind the following things:
- This state is generally used for proof of concept
- You can create commits and play around but if you quit the detach state, those changes will be unreachable.
- You can create a branch to keep track of the created commits and don't lose them.
- Quitting the detach state will not discard the changes in the working tree nor the index you have to remove them manually.


## Move to detached state

To enter the detached state you can just use the `git checkout [commit]`, `git checkout --detach [branch]`, `git checkout [tag]`

## Quit the detached state

If you want to quit the detached state you can just checkout another branch or use `git checkout -` or `git switch -` where `-` means the last branch checked out. 