## Prune 

*[:arrow_left: Go back to Git](./GIT.md)*

Prune command is used to remove objects that are unreachable from any branch or any kind of references that git thinks is not used anymore.

In example: If we modify a file and stage it to the index, internally this will create a blob object, but if we decide to restore the changes, this blob will become unreachable, to get rid of this blob object git allows you to remove those kind of objects.

*Prune objects manually generally it is not necessary, because git runs the `gc` command to clean unnecessary objects.*

## Check unreachable objects

You can check which objects are unreachable using `git fsck --unreachable`, this will print any blob, commit, tree objects.

## Prune unreachable objects

To prune objects you just need to use the `git prune` command.