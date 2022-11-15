# Git internals

*[:arrow_left: Go back to Git](./GIT.md)*

To understand Git is necessary to think of git in a easy way. And the most easier way to describe Git as a **key-value data store**. This is also called **Content-addressable filesystem** in git books.

This means that you can provide to Git any kind of data **(value)** and then it will **store** it and give you a way **(key)** to access it.

## Content
- [Git database](./INTERNALS.md#git-database)
- [The Repository](./INTERNALS.md#the-repository)
- [Objects](./INTERNALS.md#objects)
- [How git manage data](./INTERNALS.md#how-git-manage-data)
- [Object types](./INTERNALS.md#object-types)



## Git database

To understand git we first need to know how the information is stored and where it is stored.

The first concept to understand is the **Repository**.

### The Repository 
Is not more than a database, a structure that will contains all the information about our project. This means the data and because we are taking about a VCS, this will also contains the track information for all changes made in our project lifetime.

This also means that this repository will contains settings and git ows data to manage this database.

Basically the repository is stored inside **.git** directory inside your project.

### Objects

Now that we know that a repository is our database, the question now is. **Where git stores our data?**.

The answer is simple, our data is stored in the directory called **objects** also called **Object Store**.

This directory will contains all data and all  versions for each piece of information inside our project. That git will use to rebuild the history of your project.

### How git manage data?

Now the question is, **how git uses those objects to keep track of every change made?**.

Here is where git differences from other VCS's, because git thinks data as **Snapshots**. 

This means that every time that a change is made, git will made a copy of the newest version and stored it as a new and unique object and will keep the oldest version stored too. (Of course, this is not scalable in a long-term, so git has its own optimization system to keep track of changes in a efficient way, it you want to know more about it please read about the **pack file** in git).

## Object Types

Git has main three objects:

- Blob
- Three
- Commit
