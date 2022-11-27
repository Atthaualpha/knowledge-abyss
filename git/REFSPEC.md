# Refspec

*[:arrow_left: Go back to Git](./GIT.md)*

Refspec in simple words are the way as git map local references with remote references.

Remember that everything in git has a reference and when you are working locally git will store those references in your repository database. 

But what happen when you want to upload your work to a remote location (server). Git needs to keep track of that remote reference and which local reference belongs to.

## Refspec format

Refspec in git follows this format: `+<src>:<dst>`.

Let's see what is the meaning of every element.

The usage depends on which operation you perform. When we are working local and remote branches we make two main operations
- fetch: Update the remote references locally in `refs/remotes` directory from remote server. 
- push: Update remote references in the remote server. 

### Refspec for fetch

Now let's see what are `+<src>:<dst>` when **fetch** is used.

An example of fetch refspec could be `+refs/heads/master:refs/remotes/origin/master`

- **+**: This is optional and tells git to update local references even if changes are not fast-forward.
- **src**: Means the reference in the remote server that will be used to download the changes. In the example the **refs/heads/master** will be read and downloaded.
- **dst**: Means the reference in your local, that will be updated with the **src** reference changes. In the example the **refs/remotes/origin/master** will be updated.

### Refspec for push

Now let's see what are `+<src>:<dst>` when **push** is used.

An example of push refspec could be `refs/heads/master:refs/remotes/origin/master`

- **+**: Here this does not have effect
- **src**: Means the local references that will be used to upload. In the example the **refs/heads/master** will be read and uploaded to remote server.
- **dst**: Means the reference in remote server, that will be updated with the **src** reference changes. In the example the **refs/heads/master** will be updated.

You may find this refspec while creating a branch in the remote server by `git push origin master`, here the master reference is just a shortcut for `master:refs/heads/master`


## Delete remote reference

To delete a remote reference using refspec notation can de done by `git push origin :master`, here we omit the **src** reference and will cause that remote reference to be deleted.