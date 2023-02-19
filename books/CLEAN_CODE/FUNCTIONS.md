*[:arrow_left: Go back to Clean Code](./CLEAN_CODE_BOOK.md)*

# Functions

Functions should **tell a story** and **do one thing**

## Small

Functions should be very small

**How short should a function be?**

- Functions should be 20 - 30 lines long.
- Lines should not be 150 characters long.
- Even they should be less than 4 lines long.

### Indenting
Indent level of functions should not be greater than one or two.

## Do one thing

Functions must do one thing and do it well

**What is one thing?**

The functions should steps that belong to the same level of abstraction. This means that the reason of functions is to decompose a larger concept into a set of steps.

This is also means that a function that can be divided into sections is not a function doing one thing. **Functions cannot not be reasonably divided into sections**

## Abstraction level

> "Code within a given segment/block should be at the same level of abstraction"

> "Every method in you code should deal with just one level of abstraction"

**What is a abstraction level?**

Is the way how we hide details or irrelevant information.

> Different developers can infer different levels of abstraction from the same requirements.

## The stepdown rule

Write functions putting the next level of abstraction below higher levels.

```
function getActiveUserById(id) {
    var dbUser = searchInDB();
    var user = buildUser(dbUser);
    return user;
}

function searchInDB(id) { // first abstraction level
    var dbUser = dbClient.users.find(id);
    return isActiveUser(dbUser) ? dbUser : null;
}

function isActiveUser(dbUser) {  // second abstraction level
    return dbUser.status == 'active';
}

function buildUser(dbUser) {  // first abstraction level
    return new User(dbUser);
}
```

## Switch statements

Use factory pattern to hide switch complexity.

## Function arguments

Function should have the fewer arguments possible.

No more than 4 arguments.

Somethings to keep in mind.

- Do not use input arguments for output purposes. Always transform and return.
- Try to avoid flag arguments, instead split the function into many
- Use argument objects when need to pass more than two or three arguments.
- Function names and arguments should form a verb/noun pair.
- If a function has to change something, this should be the state of its owning object

## Have no side effects.

Side effects breaks the rul of **do one thing**, and must be avoided.

Use the object itself to change its state.

#### Temporal couplings

This is a type of coupling, that depends on time in some situation.

- Sequence: When things have to be executed in a specific order
- Wait: When you need to wait for a process to finish to continue
- Circumstance: When two things are bundled together because the occur at the same time.

## Command query separations

Command actions like, set, update, etc, should be separated from query actions like get, search, etc.

## Use Exceptions instead of error codes

- Instead of dealing with error codes and handle them immediately, use exceptions to separate them from the happy path.
- Separate try/catch bodies in another function
- Error handling is one thing, so functions that handle errors, should just handle them a nothing more.
- Do not use Enums for error constants.

## How to write functions following previous rules?

Write functions in a clean way imply that they will be first a mess and with time and refactoring, they can become easy to read, easy to understand.

Keep in mind that no one can write clean functions at the very first try.

## Conclusion

**Master programmers think of systems as stories to be told rather than programs to
be written.**