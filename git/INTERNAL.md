# Git internals

*[:arrow_left: Go back to Git](./GIT.md)*

To understand Git is necessary to think of git in a easy way. And the most easier way to describe Git as a **key-value data store**. This is also called **Content-addressable filesystem** in git books.

This means that you can provide to Git any kind of data **(value)** and then it will **store** it and give you a way **(key)** to access it.

## Content
- [Git database](./INTERNAL.md#git-database)
- [The Repository](./INTERNAL.md#the-repository)
- [Objects](./INTERNAL.md#objects)
- [How git manage data](./INTERNAL.md#how-git-manage-data)
- [Object types](./INTERNAL.md#object-types)
- [When the magic occur](./INTERNAL.md#when-the-magic-occur)
- [Key Notes](./INTERNAL.md#key-notes)


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

### Object Types

Git has three main objects:

- Blob: Represents each version of a file.
- Three: Represents one level of directory information.
- Commit: Represent each change introduced.

### When the magic occur?

Now that we know the types of objects stored in git database is time to know when and how this objects are written.

The first step is to create the version of the file that are modifying. For this when the command  `git add` is executed, this will perform two actions:
1. Create the blob file with the current version
2. Update the index with the references to the blob file created.

But this is not enough to keep track of changes. We need to know when this change was made, who made it and what exactly changed.

To do this, when we run the command `git commit` git make several actions:
1. Create the tree object, which contains the references to the files that are in the index.
2. Create the commit object, which contains the references to the tree object, this way a commit can keep track of what changes were made.
3. And finally, git update the HEAD pointer to the new commit created. This way we are in a version up to date.

## key notes:

- Git does not track files by its names but its content, this means that if we have to files with same content this will be represented as a single blob file.
- Tree object is calculated based on index content.
- Tree object key is calculated based on the content of blob files, this means that the same tree object will be created on any computer if the content of blob files are the same (same index).
- Tree object can contain references to another trees
- Commit objects always will be different because it is calculated by the author, the date and the message of commit.