# Bisect

*[:arrow_left: Go back to Git](./GIT.md)*

Bisect is a command that perform an binary search to find bugs.

To use it you just have to specify the commit that has the bug and the commit that you know the bug was not present yet.

To start bisect just type

> `git bisect start`

Then if you are already in the branch or commit that has de bug, tells git that current commit has the problem with

> `git bisect bad`

Now you just need to specify which is the commit that was working well with

> `git bisect good [commit|branch|tag]`

Now bisect will start checking out a specific commit using binary search, in order you to start testing.

The remaining actions depends on if the current commit has the bug or not. Just use the previous commands 

> `git bisect bad`

or

> `git bisect good`

The first command can be abbreviated with 

> `git bisect start [bad commit] [good commit]`

Example: 
> `git bisect start HEAD v1.0.0`


The last thing to do is just reset the state of bisecting using

> `git bisect reset`