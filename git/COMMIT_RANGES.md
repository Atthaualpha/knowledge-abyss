# Commit Ranges

*[:arrow_left: Go back to Git](./GIT.md)*

This is a tool that is useful to see commits that are in on branch but cannot be reached by another branch.

## Double Dot

This syntax is used to list commits between two branches.

> `git log master..feature`

This command will list all commits that are in feature branch but not in master branch.

Another way is 

> `git log feature ^master`

or 

> `git log feature --not master`

`If you omit the branch after Double Dot git will use HEAD references`

## Multiple points

There are sometimes when you want to list commits between more than two branches, in these cases you can use the following syntax:

> `git log feature_1 feature_2 ^master`

This tells git to list commits that are reachable from feature_1 or feature_2 but not by master.

## Triple Dot

The last syntax is to list commits between the two branches are not reachable by not of both of them, this means the intersection.

> `git log master...feature`

## Left-right option

A useful way to show which commits belongs to one or another branch is the following syntax:

> `git log --left-right master...feature`

This will show the following output:
```
< F
< E
> D
> C
```

This means the commits with `<` are the ones that belong to master (left) and the ones with `>` are the ones that belong to feature (right).


